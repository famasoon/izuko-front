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
          Whois
        </p>
        <a href="#" class="card-header-icon" aria-label="more options">
          <span class="icon">
            <i class="fas fa-angle-down" aria-hidden="true" />
          </span>
        </a>
      </header>
      <div class="card-content">
        <div class="content">
          <pre>{{ resp.WhoisResult }}</pre>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  async asyncData(context) {
    const DOMAIN_NAME = context.params.domain
    const { data } = await axios.get(
      'http://izuko.ch/api/whois/' + DOMAIN_NAME
    )
    return { resp: data }
  }
}
</script>
