<template>
  <!-- This is the template section of the component -->
  <section id="programs" class="container py-20 border-t  border-secondary">
    <!-- This section contains the list of programs -->
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16">
      <!-- This is the header of the section, which displays the title of the section -->
      <h1 class="text-3xl text-center font-extrabold text-gray-900">SPONSOR PROGRAM</h1>
      <!-- This is the grid layout that displays the programs -->
      <div class="mt-12 grid gap-5 md:grid-cols-2 lg:grid-cols-3">
        <!-- This is a loop that creates a div for each program -->
        <div v-for="item in programs" :key="item.id" class="bg-accent shadow-lg rounded-lg overflow-hidden">
          <!-- This is the image of the program -->
          <img class="h-48 w-full object-cover" :src="item.src" :alt="program" />
          <!-- This is the name, type, and description of the program -->
          <div class="p-6">
            <h2 class="text-xl font-semibold text-gray-900">{{ item.name }}</h2>
            <p class="mt-2 text-green-600">{{ item.type }} </p>
            <p class="text-lg leading-relaxed truncate-overflow" v-html="item.description" ref="bio"></p>
            <!-- This is the link to read more about the program -->
            <a href="#" class="text-green-500" @click.prevent="showModal(item)">Read more</a>
          </div>
        </div>
      </div>
    </div>
    <!-- This is the modal that displays more information about the program -->
    <div v-if="selectedProgram" class="fixed inset-0 bg-gray-700 bg-opacity-50 flex justify-center items-center">
      <div class="bg-white max-w-md mx-auto rounded-lg overflow-hidden">
        <div class="p-6">
          <!-- This is the name, type, and full description of the program -->
          <h2 class="text-2xl font-bold mb-2">{{ selectedProgram.name }}</h2>
          <p class="text-green-600 mb-4">{{ selectedProgram.type }}</p>
          <p class="text-base  text-lg leading-relaxed" v-html="selectedProgram.description"></p>
          <!-- This is the button to close the modal and the PayPal donate button -->
          <div class="flex justify-between mt-8">
            <button class="px-4 py-2 bg-blue-500 text-white font-semibold rounded-lg"
              @click="selectedProgram = null">Close</button>
            <div id="donate-button-container">
              <div id="donate-button"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
// This is the script section of the component
// import { loadScript } from 'vue-plugin-load-script';

export default {
  data() {
    // Data for the list of programs
    return {
      programs: [
          {
            id: 1,
            name: 'Chess Club',
            type: 'Sport',
            description: 'Our chess club provides a space for students to develop their critical thinking and problem-solving skills through playing chess.',
            src: '/images/gallery/chess.jpg',
          },
          {
            id: 2,
            name: 'Construction Club',
            type: 'Building',
            description: 'In our construction club, students learn the basics of woodworking and construction by building projects like birdhouses and picture frames.',
            src: '/images/gallery/construction.jpg',
          },
          {
            id: 3,
            name: 'Field Trip Fund',
            type: 'Experiences',
            description: 'Our field trip fund helps provide students with opportunities to learn outside the classroom by funding trips to museums, historical sites, and other educational locations.',
            src: '/images/gallery/field-trip.jpg',
          },
          {
            id: 4,
            name: 'Extra-Curricular Activities',
            type: 'Enrichment',
            description: 'Our extra-curricular activities include a range of options like art club, cooking club, and drama club, providing students with opportunities to explore their interests and talents outside the classroom.',
            src: '/images/gallery/extra-curricular.jpg',
          },
        ],
   
      // Data for the currently selected program
      selectedProgram: null,
    };
  },
  methods: {
    // Method for displaying the details of a program in a modal dialog
    showModal(program) {
      this.selectedProgram = program;
      this.$nextTick(() => {
        this.$refs.bio[0].classList.remove('truncate-overflow');
      });
    },
  },
  
  // Commented-out section for loading the PayPal donation SDK
//   mounted() {
//   loadScript('https://www.paypalobjects.com/donate/sdk/donate-sdk.js').then(() => {
//   if (typeof PayPal !== 'undefined') {
//     PayPal.Donation.Button({
//       env: 'sandbox',
//       hosted_button_id: 'WMBKQ9WVGWCXL',
//       image: {
//         src: 'https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif',
//         alt: 'Donate with PayPal button',
//         title: 'PayPal - The safer, easier way to pay online!',
//       },
//     }).render('#donate-button', function() {
//       console.log('Donate button rendered successfully!');
//     });
//   }
// });

    
// },


};
</script>
<style scoped>

.truncate-overflow {
  display: -webkit-box;
  -webkit-line-clamp: 3;
  -webkit-box-orient: vertical;
  overflow: hidden;
  text-overflow: ellipsis;
}
</style>
         
  
       