<template>
  <form class="form" @submit.prevent="calculateAgeFunction">
    <FormGroup v-model="day" name="day" labelText="DAY" placeholder="DD" :error="errors.day" />
    <FormGroup
      v-model="month"
      name="month"
      labelText="MONTH"
      placeholder="MM"
      :error="errors.month"
    />
    <FormGroup
      v-model="year"
      name="year"
      labelText="YEAR"
      placeholder="YYYY"
      :error="errors.year"
    />
    <FormLine />
    <FormButton />
  </form>
</template>

<script>
import { ref, toRefs } from 'vue'
import FormGroup from './FormGroup.vue'
import FormLine from './FormLine.vue'
import FormButton from './FormButton.vue'

export default {
  name: 'TheForm',
  components: { FormGroup, FormLine, FormButton },
  props: {
    calculateAge: {
      type: Function,
      required: true
    }
  },
  setup(props) {
    const { calculateAge } = toRefs(props)

    const day = ref('')
    const month = ref('')
    const year = ref('')
    const errors = ref({ day: '', month: '', year: '' })

    const validateInput = (value, type) => {
      errors.value[type] = ''

      const num = parseInt(value, 10)

      if (!value) {
        errors.value[type] = 'Field is empty.'
      } else if (isNaN(num)) {
        errors.value[type] = `Invalid ${type}`
      }
    }

    const calculateAgeFunction = () => {
      validateInput(day.value, 'day')
      validateInput(month.value, 'month')
      validateInput(year.value, 'year')

      if (!errors.value.day && !errors.value.month && !errors.value.year) {
        const birthDate = new Date(year.value, month.value - 1, day.value)
        calculateAge.value(birthDate)
      }
    }

    return { day, month, year, errors, calculateAgeFunction }
  }
}
</script>
