<template>
  <section class="container">
    <to-do />
  </section>
</template>

<script>
import ToDo from '~/components/ToDo.vue'

export default {
  components: {
    ToDo
  }
}
</script>

<style>
.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
