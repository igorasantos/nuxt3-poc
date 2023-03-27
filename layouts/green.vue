<template>
  <div>
    <Nav/>
    <slot />
  </div>
</template>

<script lang="ts" setup>
import Nav from '../components/Nav.vue'
</script>

<style scoped>
div {
  background-color: lightgreen;
}
</style>