<template>
  <div v-if="destination">
    
    <button @click="goBack" class="go-back">Go Back</button>

    <h1>{{ destination.name }}</h1>

    <div class="destination-details">
      <p>{{ destination.description }}</p>
      <img :src="`/images/${destination.image}`" :alt="destination.name" />
    </div>
    <section class="experiences">
      <h2>Top Experiences in {{ destination.name }}</h2>
      <div class="cards">
        <RouterLink
          v-for="experience in destination.experiences"
          :key="experience.slug"
          :to="{ name: 'experience', params: { experienceSlug: experience.slug } }"
        >
          <ExperienceCard :experience="experience" />
        </RouterLink>
      </div>
      <RouterView />
    </section>

  </div>
</template>

<script>
import sourceData from '../data.json'
import { RouterLink, RouterView } from 'vue-router'
import ExperienceCard from '../components/ExperienceCard.vue'

export default {
  components: {
    RouterLink,
    RouterView,
    ExperienceCard
  },
  computed: {
    destination() {
      const slug = this.$route.params.slug
      return sourceData.destinations.find(
        (dest) => dest.slug === slug
      )
    }
  },
  // back button
  methods: {
    goBack() {
      this.$router.back()
    }
  }
}
</script>