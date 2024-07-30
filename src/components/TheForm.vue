<template>
  <form class="form" @submit.prevent="calculateAgeFunction">
    <FormGroup v-model="day" name="day" labelText="DAY" placeholder="DD" :error="errors.day" />
    <FormGroup v-model="month" name="month" labelText="MONTH" placeholder="MM" />
    <FormGroup v-model="year" name="year" labelText="YEAR" placeholder="YYYY" />
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

      if (!value) {
        errors.value[type] = 'Field is empty.'
      }
    }

    const calculateAgeFunction = () => {
      validateInput(day.value, 'day')

      const birthDate = new Date(year.value, month.value - 1, day.value)
      calculateAge.value(birthDate)
    }

    return { day, month, year, calculateAgeFunction, errors }
  }
}
</script>
