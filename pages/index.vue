<template>
  <section class="section">
    <div class="columns is-mobile" />
    <hero />
    <div id="inputfield">
      <b-field position="is-centered">
        <b-input v-model="domain" placeholder="Input Domain or IP address..." type="search" icon="magnify" />
        <nuxt-link :to="{ name: 'whois-domain', params: { domain: domain }}">
          <p class="control">
            <button class="button is-info">
              Lookup
            </button>
          </p>
        </nuxt-link>
      </b-field>
    </div>
    <description />
  </section>
</template>

<script>
import Hero from '~/components/Hero.vue'
import Description from '~/components/Description.vue'

export default {
  components: {
    Hero,
    Description
  },

  data() {
    return {
      domain: ''
    }
  }
}
</script>

<style>
#inputfield {
  margin: 40px;
}
</style>
