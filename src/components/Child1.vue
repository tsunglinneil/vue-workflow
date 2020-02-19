<template>
  <div class="col-xs-12 col-sm-6">
    <li v-if="!selectedMovie">Child1 - {{movie.title}}</li>
    <li v-else>Child1 - {{movie.title}} | from child1: {{selectedMovie.title}}</li>
    <slot></slot>
  </div>
</template>

<script>
import { selectedBus } from "../main";

export default {
  data() {
    return {
      selectedMovie: null
    };
  },
  props: ["movie"],
  created() {
    selectedBus.$on("movieSelectedToChild1", movie => {
      this.selectedMovie = movie;
    });
  }
};
</script>

<style>
</style>