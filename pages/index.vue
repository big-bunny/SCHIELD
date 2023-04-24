<template>
  <main>
    <partials-header />
    <home-about-school />
    <home-news />
    <home-child />
    <home-programs />
    <home-mission-vision />
    <home-our-staff />
    <home-gallery />
    <home-contact-card />
    <partials-footer />
  </main>
</template>

<script lang="ts">
import HomeAboutSchool from '~/components/home/AboutSchool.vue'
import HomeNews from '~/components/home/News.vue'
import HomeChild from '~/components/home/SupportChild.vue'
import HomePrograms from '~/components/home/SupportProgram.vue'
import HomeMissionVision from '~/components/home/MissionVision.vue'
import HomeOurStaff from '~/components/home/OurStaff.vue'
import HomeGallery from '~/components/home/Gallery.vue'
import HomeContactCard from '~/components/home/ContactCard.vue'
import PartialsHeader from '~/components/partials/Header.vue'
import PartialsFooter from '~/components/partials/Footer.vue'

export default {
  components: {
    HomeAboutSchool,
    HomeNews,
    HomeChild,
    HomePrograms,
    HomeMissionVision,
    HomeOurStaff,
    HomeGallery,
    HomeContactCard,
    PartialsHeader,
    PartialsFooter
  }
}
</script>




