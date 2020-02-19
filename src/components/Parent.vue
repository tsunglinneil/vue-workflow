<template>
  <div>
    <h1>Parent</h1>
    <ul>
      <child1 v-for="(movie, index) in movies" :key="index" :movie="movie">
          <button @click="selected(movie)">select</button>
      </child1>
    </ul>
    <ul>
      <child2 v-for="(movie, index) in movies" :key="index" :movie="movie">
      </child2>
    </ul>
  </div>
</template>

<script>
import child1 from "./child1.vue";
import child2 from "./child2.vue";

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
    child1,
    child2
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
