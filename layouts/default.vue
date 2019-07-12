<template>
  <div>
    <nav-bar />
    <div class="container column is-10">
      <nuxt />
    </div>
  </div>
</template>

<script>
import NavBar from '~/components/NavBar'

export default {
  components: {
    NavBar
  }
}
</script>
