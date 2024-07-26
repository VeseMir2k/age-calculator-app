<template>
  <form class="form">
    <CalculatorAgeFormInput name="day" labelText="DAY" placeholder="DD" />
    <CalculatorAgeFormInput name="month" labelText="MONTH" placeholder="MM" />
    <CalculatorAgeFormInput name="year" labelText="YEAR" placeholder="YYYY" />
  </form>
</template>

<script>
import CalculatorAgeFormInput from './CalculatorAgeFormInput.vue'

export default {
  name: 'CalculatorAgeForm',
  components: { CalculatorAgeFormInput },
  setup() {
    return {}
  }
}
</script>
