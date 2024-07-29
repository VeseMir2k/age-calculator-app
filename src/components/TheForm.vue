<template>
  <form class="form" @submit.prevent="dataShow">
    <FormGroup v-model="day" name="day" labelText="DAY" placeholder="DD" />
    <FormGroup v-model="month" name="month" labelText="MONTH" placeholder="MM" />
    <FormGroup v-model="year" name="year" labelText="YEAR" placeholder="YYYY" />
    <FormLine />
    <FormButton />
  </form>
</template>

<script>
import { ref } from 'vue'
import FormGroup from './FormGroup.vue'
import FormLine from './FormLine.vue'
import FormButton from './FormButton.vue'

export default {
  name: 'TheForm',
  components: { FormGroup, FormLine, FormButton },
  setup() {
    const day = ref('')
    const month = ref('')
    const year = ref('')

    const dataShow = () => {
      console.log(day.value, month.value, year.value)
    }

    return { day, month, year, dataShow }
  }
}
</script>
