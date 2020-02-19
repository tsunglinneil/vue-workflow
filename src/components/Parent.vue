<template>
  <div>
    <h1>Parent</h1>
    <ul>
      <child v-for="(movie, index) in movies" :key="index" :movie="movie">
          <button @click="selected(movie)">select</button>
      </child>
    </ul>
  </div>
</template>

<script>
import Child from "./Child.vue";

export default {
  data() {
    return {
      movies: [
        {
          title: "Interstellar",
          year: "2014",
          star: "5"
        },
        {
          title: "Ad Astra",
          year: "2019",
          star: "3"
        }
      ]
    };
  },
  components: {
    Child
  },
  methods: {
      selected(movie) {
          this.$emit('movieSelected', movie);
      }
  }
};
</script>

<style>
</style>
