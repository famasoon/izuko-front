<template>
  <section class="section">
    <div class="columns is-mobile" />
    <hero />
    <input-domain-form />
    <description />
  </section>
</template>

<script>
import Hero from '~/components/Hero.vue'
import InputDomainForm from '~/components/InputDomainForm.vue'
import Description from '~/components/Description.vue'

export default {
  components: {
    Hero,
    InputDomainForm,
    Description
  }
}
</script>
