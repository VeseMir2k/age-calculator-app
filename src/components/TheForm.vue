<template>
  <form class="form" @submit.prevent="calculateAgeFunction">
    <FormGroup v-model="day" name="day" labelText="DAY" placeholder="DD" :errors="errors" />
    <FormGroup v-model="month" name="month" labelText="MONTH" placeholder="MM" :errors="errors" />
    <FormGroup v-model="year" name="year" labelText="YEAR" placeholder="YYYY" :errors="errors" />
    <FormError v-if="errors.date" className="form-error" :error="errors.date" />
    <FormLine />
    <FormButton />
  </form>
</template>

<script>
import { ref, toRefs } from 'vue'
import FormGroup from './FormGroup.vue'
import FormLine from './FormLine.vue'
import FormButton from './FormButton.vue'
import FormError from './FormError.vue'

export default {
  name: 'TheForm',
  components: { FormGroup, FormError, FormLine, FormButton },
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
    const errors = ref({ day: '', month: '', year: '', date: '' })

    const validateInput = (value, type) => {
      errors.value[type] = ''

      const num = parseInt(value, 10)
      const currentDate = new Date()

      const birthDate = new Date(year.value, month.value - 1, day.value)
      // console.log('BIRTH ' + birthDate)
      // console.log('CURRENT ' + currentDate)

      if (!value) {
        errors.value[type] = 'Field is empty'
      } else if (isNaN(num)) {
        errors.value[type] = `Invalid ${type}`
      } else if (type === 'day' && (num < 1 || num > 31)) {
        errors.value[type] = 'Invalid day'
      } else if (type === 'month' && (num < 1 || num > 12)) {
        errors.value[type] = 'Invalid month'
      } else if (currentDate < birthDate) {
        errors.value[type] = 'Future date'
      }
    }

    const validateDate = () => {
      errors.value.date = 'Error test'
    }

    const calculateAgeFunction = () => {
      validateInput(day.value, 'day')
      validateInput(month.value, 'month')
      validateInput(year.value, 'year')

      if (!errors.value.day && !errors.value.month && !errors.value.year) {
        validateDate()
      }

      if (!errors.value.day && !errors.value.month && !errors.value.year && !errors.value.date) {
        const birthDate = new Date(year.value, month.value - 1, day.value)
        calculateAge.value(birthDate)
      }
    }

    return { day, month, year, errors, calculateAgeFunction }
  }
}
</script>
