<script>
import axios from 'axios';

export default {
  data() {
    return {
      api: 'http://127.0.0.1:8000/api/posts'
    }
  },
  methods: {
    getApi(api) {
      axios.get(api)
        .then(function (response) {
          // handle success
          console.log(response.data.data);
        })
        .catch(function (error) {
          // handle error
          console.log(error);
        })
    }
  },
  mounted() {
    this.getApi(this.api)
  }
}


</script>

<template>
  <header>
    <h1>Social API</h1>
  </header>

  <main>
    <section>Vari dati</section>
  </main>
</template>

<style scoped></style>
