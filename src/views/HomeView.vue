<template>
  <div class="home">
    <h1>All Destinations</h1>
    <div class="destinations">
      <RouterLink
        v-for="destination in destinations"
        :key="destination.id"
        :to="{ name: 'destination', params: { slug: destination.slug } }"
      >
        <h2>{{ destination.name }}</h2>
        <img :src="`/images/${destination.image}`" :alt="destination.name" />
      </RouterLink>
    </div>
  </div>
</template>

<script>
import sourceData from '../data.json'
import { RouterLink } from 'vue-router'

export default {
  components: {
    RouterLink
  },
  data() {
    return {
      destinations: sourceData.destinations
    }
  }
}
</script>