<template>

  <div class="container" id="app">
    <h3>Employee Logins</h3>
    <br>
    <br>
    <div
      class="columns medium-4"
      v-for="(item, index) in data"
      v-bind:key="index"
    >
      <div class="card">
        <div class="card-section">
          <p>{{ item.name }}</p>
        </div>
        <div class="card-divider">
          <p>{{ item.username }}</p>
        </div>
        <div class="card-divider">
          <p>{{ item.email }}</p>
        </div>
        <div class="card-divider">
          <p>{{ item.id }}</p>
        </div>
      </div>
    </div>
       <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/foundation/6.3.1/css/foundation.min.css"
    />
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Details',
  components: {

  },
  data () {
    return {
      data: {}
    }
  },
  methods: {
    async fetch () {
      const varData = await axios
        .get('https://jsonplaceholder.typicode.com/users')
        .then(function (response) {
          if (response.status !== 200 && response.status !== 201) {
            console.log('Error' + response.status)
            return
          }
          return response
        })
        .catch((e) => {
          console.log('Error: ', e)
        })
      return varData
    },
    loadDetails () {
      this.fetch().then((response) => {
        this.data = response.data
      })
    }
  },
  mounted () {
    this.loadDetails()
  }
}
</script>

<style scoped>
.card  {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2) ;
  transition: 0.3s;
  width: 70%;
}

.card:hover {
  box-shadow: 0 8px 16px 0 rgb(243, 3, 3);
}
</style>
