<template>
  <section class="section">
    <div class="columns is-mobile" />
    <hero />
    <input-domain-form />
  </section>
</template>

<script>
import Hero from '~/components/Hero.vue'
import InputDomainForm from '~/components/InputDomainForm.vue'
export default {
  components: {
    Hero,
    InputDomainForm
  }
}
</script>
