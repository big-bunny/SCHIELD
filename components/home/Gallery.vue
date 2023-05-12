  <!-- eslint-disable no-undef -->
<template>
  <!-- Section for photo gallery -->
  <section id="gallery" class="container border-t border-secondary py-20 md:py-12 bg-green-500">
    <!-- Title of the section -->
    <h2 class="text-3xl text-center font-semibold py-20">PHOTO GALLERY</h2>
    <!-- Navigation bar for photo gallery -->
    <nav class="py-4">
      <!-- Displaying the current photo -->
      <div class="flex justify-center">
        <img
          :src="photos[currentPhoto]"
          class="rounded shadow border-2 border-red-500"
          style="max-height: 420px"
        />
      </div>
  <!-- Thumbnail images for navigation -->
  <div class="flex flex-wrap justify-center p-2">
    <img
      v-for="(photo, i) in photos"
      :key="photo"
      :src="photo"
      class="rounded-full hover:shadow-md cursor-pointer m-1 border-2 border-red-500"
      style="max-width: 64px"
      @click="changePhoto(i)"
    />
  </div>
</nav>

<!-- YouTube playlist -->
<div class="mt-12 flex flex-col items-center">
  <h3 class="text-xl font-semibold mb-4">Check out my YouTube playlist:</h3>
  <div class="grid grid-cols-2 gap-4">
    <iframe
      v-for="(video, i) in videos"
      :key="i"
      :src="video"
      frameborder="0"
      allowfullscreen
    ></iframe>
  </div>
</div>

  </section>
</template>
<script lang="ts">
export default {
  data() { // define data properties
    return {
      currentPhoto: 0, // initialize current photo index to 0
      photos: [], // initialize photos array to empty
      videos: [ // array of YouTube video links
        "https://www.youtube.com/embed/videoseries?list=PLU_mcNMHvxilz_9XO9xIZ9CHRAej-JPZr",
        "https://www.youtube.com/embed/videoseries?list=PLU_mcNMHvxilz_9XO9xIZ9CHRAej-JPZr",
        "https://www.youtube.com/embed/videoseries?list=PLU_mcNMHvxilz_9XO9xIZ9CHRAej-JPZr",
        "https://www.youtube.com/embed/videoseries?list=PLU_mcNMHvxilz_9XO9xIZ9CHRAej-JPZr"
      ]
    }
  },
  created() { // lifecycle hook that runs when component is created
    this.loadImages() // load images
  },
  methods: { // define component methods
    importAll(r) { // helper function to import all images
      return r.keys().map(r)
    },
    async loadImages() { // asynchronous function to load images
      const images = await this.importAll(
        // use require.context to import all images in directory
        // eslint-disable-next-line no-undef
        require.context('@/static/images/gallery', false, /\.(png|jpe?g|svg)$/)
      )
      this.photos = images // set photos array to imported images
    },
    changePhoto(index) { // function to change current photo index
      this.currentPhoto = index
    },
  },
}
</script>

<style scoped>
iframe {
  width: 100%;
  height: 100%;
}
</style>
