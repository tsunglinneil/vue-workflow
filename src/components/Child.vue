<template>
  <div class="col-xs-12 col-sm-6">
    <li>Child - {{movie.title}}</li>
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: ["movie"]
};
</script>

<style>
</style>