<template>
  <div>
    <h1 class="title">
      {{ $route.params.domain }}
    </h1>
    <h2 class="subtitle">
      Related information
    </h2>
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          Whois Result
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true" />
          </span>
        </a>
      </header>
      <div class="card-content">
        <div class="content">
          <template>
            <pre>{{ whoisResp.result }}</pre>
          </template>
        </div>
      </div>
    </div>
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">
          Name Servers
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true" />
          </span>
        </a>
      </header>
      <div class="card-content">
        <div class="content">
          <template v-if="nameServers">
            <ul id="servers">
              <li v-for="(server, index) in nameServers.Servers" :key="index">
                {{ index }} - {{ server }}
              </li>
            </ul>
          </template>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  data() {
    return {
      whoisResp: {
        domain: '',
        result: ''
      },
      nameServers: ''
    }
  },

  asyncData(context) {
    const DOMAIN_NAME = context.params.domain
    const { data, ns } = Promise.all([
      axios.get('http://127.0.0.1:8080/api/whois/' + DOMAIN_NAME),
      axios.get('http://127.0.0.1:8080/api/enumns/' + DOMAIN_NAME)
    ])

    return {
      whoisResp: data,
      nameServers: ns
    }
  }
}
</script>
