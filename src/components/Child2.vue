<template>
  <div class="col-xs-12 col-sm-6">
    <li>Child2 - {{movie.title}}</li>
    <button @click="movieSelected">SelectedBus took movie to child1</button>
  </div>
</template>

<script>
import { selectedBus } from '../main';

export default {
  props: ["movie"],
  methods: {
    movieSelected() {
      selectedBus.$emit('movieSelectedToChild1', this.movie);
    }
  }
};
</script>

<style>
</style>