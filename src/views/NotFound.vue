<template>
  <div>
    <h1>404 - Page Not Found</h1>
    <p>Oops, we couldn't find that page. Try going 
      <RouterLink to="/">home</RouterLink>.
    </p>
  </div>
</template>

<script>
import { RouterLink } from 'vue-router'
export default {
  components: {
    RouterLink
  }
}
</script>