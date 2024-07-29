<template>
  <form class="form" @submit.prevent="console.log('click')">
    <CalculatorAgeFormGroup name="day" labelText="DAY" placeholder="DD" />
    <CalculatorAgeFormGroup name="month" labelText="MONTH" placeholder="MM" />
    <CalculatorAgeFormGroup name="year" labelText="YEAR" placeholder="YYYY" />
    <button class="form__button button">
      <img class="form__button__icon" src="../assets/images/icon-arrow.svg" alt="" />
    </button>
    <span></span>
  </form>
</template>

<script>
import CalculatorAgeFormGroup from './CalculatorAgeFormGroup.vue'

export default {
  name: 'CalculatorAgeForm',
  components: { CalculatorAgeFormGroup },
  setup() {
    return {}
  }
}
</script>
