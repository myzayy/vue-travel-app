<template>
  <div v-if="experience" class="experience-details">
    <h2>{{ experience.name }}</h2>
    <img :src="`/images/${experience.image}`" :alt="experience.name" />
    <p>{{ experience.description }}</p>
  </div>
</template>

<script>
import sourceData from '../data.json'

export default {
  computed: {
    destination() {
      const slug = this.$route.params.slug
      return sourceData.destinations.find(
        (dest) => dest.slug === slug
      )
    },
    experience() {
      if (!this.destination) return null
      
      const experienceSlug = this.$route.params.experienceSlug
      return this.destination.experiences.find(
        (exp) => exp.slug === experienceSlug
      )
    }
  }
}
</script>