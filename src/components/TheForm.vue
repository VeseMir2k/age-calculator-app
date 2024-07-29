<template>
  <form class="form" @submit.prevent="console.log('click')">
    <FormGroup name="day" labelText="DAY" placeholder="DD" />
    <FormGroup name="month" labelText="MONTH" placeholder="MM" />
    <FormGroup name="year" labelText="YEAR" placeholder="YYYY" />
    <FormLine />
    <FormButton />
  </form>
</template>

<script>
import FormGroup from './FormGroup.vue'
import FormLine from './FormLine.vue'
import FormButton from './FormButton.vue'

export default {
  name: 'TheForm',
  components: { FormGroup, FormLine, FormButton }
}
</script>
