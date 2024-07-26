<template>
  <form class="form">
    <div class="form__group">
      <label class="form__label" for="day">DAY</label>
      <input class="form__input" id="day" type="text" name="day" placeholder="DD" />
    </div>

    <div class="form__group">
      <label class="form__label" for="month">MONTH</label>
      <input class="form__input" id="month" type="text" name="month" placeholder="MM" />
    </div>

    <div class="form__group">
      <label class="form__label" for="year">YEAR</label>
      <input class="form__input" id="year" type="text" name="year" placeholder="YYYY" />
    </div>
  </form>
</template>

<script>
export default {
  name: 'CalculatorAgeForm',
  setup() {
    return {}
  }
}
</script>
