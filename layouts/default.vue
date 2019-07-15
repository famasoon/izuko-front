<template>
  <div>
    <nav-bar />
    <div class="container column is-10">
      <nuxt />
    </div>
    <footer-bar />
  </div>
</template>

<script>
import NavBar from '~/components/NavBar'
import FooterBar from '~/components/FooterBar'

export default {
  components: {
    NavBar,
    FooterBar
  }
}
</script>
