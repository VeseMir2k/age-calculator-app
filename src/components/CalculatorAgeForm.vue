<template>
  <form class="form" @submit.prevent="console.log('click')">
    <CalculatorAgeFormInput name="day" labelText="DAY" placeholder="DD" />
    <CalculatorAgeFormInput name="month" labelText="MONTH" placeholder="MM" />
    <CalculatorAgeFormInput name="year" labelText="YEAR" placeholder="YYYY" />
    <button class="form__button button">
      <img class="form__button__icon" src="../assets/images/icon-arrow.svg" alt="" />
    </button>
    <span></span>
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
