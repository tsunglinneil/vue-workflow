<template>
  <div class="container">
    <app-header></app-header>
    <hr />
    <p>Movie Selected: {{showSelected}}</p>
    <parent @movieSelected="showMovie"></parent>
    <hr />
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header from "./components/common/Header.vue";
import Footer from "./components/common/Footer.vue";
import Parent from "./components/Parent.vue";

export default {
  data() {
    return {
      showSelected: ''
    }
  },
  components: {
    appHeader: Header,
    Parent,
    "app-footer": Footer
  },
  methods: {
    showMovie(movie) {
      this.showSelected = movie.title;
    }
  }
};
</script>

</script>

<style lang="scss">
</style>
