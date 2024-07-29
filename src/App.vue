<template>
  <div class="App">
    <TheForm />
    <TheResults :daysAge="daysAge" :monthsAge="monthsAge" :yearsAge="yearsAge" />
  </div>
</template>

<script>
import { ref } from 'vue'
import TheForm from './components/TheForm.vue'
import TheResults from './components/TheResults.vue'
export default {
  name: 'App',
  components: { TheForm, TheResults },
  setup() {
    const daysAge = ref('--')
    const monthsAge = ref('--')
    const yearsAge = ref('--')

    return { daysAge, monthsAge, yearsAge }
  }
}
</script>
