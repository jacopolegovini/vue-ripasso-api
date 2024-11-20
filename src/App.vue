<script>
import axios from 'axios';

export default {
  data() {
    return {
      api: 'http://127.0.0.1:8000/api/posts',
      postLists: [],
    }
  },
  methods: {
    getApi(api) {
      axios.get(api)
        .then((response) => {
          // handle success
          console.log(response.data.data);
          this.postLists = response.data.data
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
    <section>
      <ul>
        <li v-for="post in postLists" :key="post.id">
          {{ post.title }}
        </li>
      </ul>
    </section>
  </main>
</template>

<style scoped></style>
