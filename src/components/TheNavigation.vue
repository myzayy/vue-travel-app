<template>
  <nav id="nav">
    <RouterLink to="/">Home</RouterLink>
    <RouterLink
      v-for="destination in destinations"
      :key="destination.id"
      :to="{ name: 'destination', params: { slug: destination.slug } }"
    >
      {{ destination.name }}
    </RouterLink>
  </nav>
</template>

<script>
import sourceData from '../data.json'
import { RouterLink } from 'vue-router'

export default {
  components: {
    RouterLink 
  },
  
  // 'data()' - function that return object
  // with data of component
  data() {
    return {
      destinations: sourceData.destinations //reactive
    }
  }
}
</script>