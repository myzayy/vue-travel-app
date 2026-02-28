<template>
  <header>
    <TheNavigation />
  </header>

  <div class="container">
    <RouterView :key="$route.fullPath" />
  </div>
</template>

<script>

import TheNavigation from './components/TheNavigation.vue'
import { RouterView } from 'vue-router'

export default {
  components: {
    TheNavigation,
    RouterView
  }
}
</script>