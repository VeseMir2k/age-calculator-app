<template>
  <div class="App">
    <TheForm :calculateAge="calculateAge" />
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

    const calculateAge = (birthDate) => {
      const currentDate = new Date()
      let years = currentDate.getFullYear() - birthDate.getFullYear()
      let months = currentDate.getMonth() - birthDate.getMonth()
      let days = currentDate.getDate() - birthDate.getDate()

      if (days < 0) {
        months--
        days += new Date(currentDate.getFullYear(), currentDate.getMonth(), 0).getDate()
      }

      if (months < 0) {
        years--
        months += 12
      }

      daysAge.value = days
      monthsAge.value = months
      yearsAge.value = years
    }

    return { daysAge, monthsAge, yearsAge, calculateAge }
  }
}
</script>
