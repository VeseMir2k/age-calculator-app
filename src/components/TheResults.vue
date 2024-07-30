<template>
  <div class="results">
    <ResultsItem :result="yearsAge" text="years" />
    <ResultsItem :result="monthsAge" text="months" />
    <ResultsItem :result="daysAge" text="days" />
  </div>
</template>

<script>
import ResultsItem from './ResultsItem.vue'

export default {
  name: 'AppResults',
  components: { ResultsItem },
  props: {
    daysAge: {
      type: Number,
      required: true
    },
    monthsAge: {
      type: Number,
      required: true
    },
    yearsAge: {
      type: Number,
      required: true
    }
  }
}
</script>
