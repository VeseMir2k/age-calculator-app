<template>
  <div class="App">
    <TheForm />
    <TheResults />
  </div>
</template>

<script>
import TheForm from './components/TheForm.vue'
import TheResults from './components/TheResults.vue'
export default {
  name: 'App',
  components: { TheForm, TheResults }
}
</script>
