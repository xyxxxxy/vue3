<template>
  <div class="app">
    <h1>Hello!</h1>
    <Person></Person>
  </div>
</template>
<script lang="ts">
import Person from './components/Person.vue'
export default {
  name: 'App',
  components: { Person }
}
</script>
