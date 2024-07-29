<template>
  <form class="form" @submit.prevent="console.log('click')">
    <AppFormGroup name="day" labelText="DAY" placeholder="DD" />
    <AppFormGroup name="month" labelText="MONTH" placeholder="MM" />
    <AppFormGroup name="year" labelText="YEAR" placeholder="YYYY" />
    <AppFormLine />
    <AppFormButton />
  </form>
</template>

<script>
import AppFormGroup from './AppFormGroup.vue'
import AppFormLine from './AppFormLine.vue'
import AppFormButton from './AppFormButton.vue'

export default {
  name: 'AppForm',
  components: { AppFormGroup, AppFormLine, AppFormButton }
}
</script>
