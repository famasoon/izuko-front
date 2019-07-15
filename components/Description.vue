<template>
  <div class="media">
    <div class="media-content">
      <p class="content">
        <strong>IZUKO</strong> show the following information
      </p>
      <b-table :data="data" :columns="columns" />
    </div>
  </div>
</template>


<script>
export default {
  data() {
    return {
      data: [
        { id: 1, information: 'Whois' },
        { id: 2, information: 'IP Address' },
        { id: 3, information: 'Name Servers' },
        { id: 4, information: 'MX Records' }
      ],
      columns: [
        {
          field: 'id',
          label: '*',
          width: '40',
          numeric: true
        },
        {
          field: 'information',
          label: 'Information'
        }
      ]
    }
  }
}
</script>
