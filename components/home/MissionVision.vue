<template>
  <!-- Mission and vision section -->
  <section id="mission-vision" class="container py-20  border-t  border-secondary">
    <!-- Flexbox container for items -->
    <div class="md:flex justify-around md:py-8">
      <!-- Loop through each item -->
      <div v-for="(item, index) in items" :key="index" class="md:w-1/3 text-center">
        <!-- Item title -->
        <div class="py-10 text-xl font-semibold text-primary text-wider">{{ item.title }}</div>

        <!-- Item text -->
        <div class="leading-loose py-4 bg-red-500 text-xl" v-if="index === 0">{{ item.text }}</div>
        <div class="leading-loose py-4 bg-green-500 text-xl" v-else>{{ item.text }}</div>
      </div>
    </div>
  </section>
</template>

<script lang="ts">
export default {
  // Data object
  data() {
    return {
      // Array of items
      items: [
        {
          // Item 1 - Mission statement
          title: 'MISSION STATEMENT',
          text:
            'Our mission is to provide access to quality education to children in Kajiado, Kenya, with the aim of empowering them to break the cycle of poverty and improve their lives and those of their families. We strive to create a learning environment that is supportive, inclusive, and empowering, valuing diversity and embracing the unique cultural heritage of our community.',
        },
        {
          // Item 2 - Vision statement
          title: 'VISION STATEMENT',
          text:
            'Our vision is a world where every child has access to quality education and the opportunity to reach their full potential. We believe that education is a fundamental human right and that it is essential for creating a more just and equitable society. At our center, we believe in fostering a culture of curiosity, creativity, and critical thinking, while also imparting life skills and values such as hard work, honesty, and respect for diversity. Our vision is to inspire and empower the next generation of global citizens who will make a positive impact on the world.',
        },
      ],
    }
  },
}
</script>
