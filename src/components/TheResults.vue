<template>
  <div class="results">
    <ResultsItem text="years" />
    <ResultsItem text="months" />
    <ResultsItem text="days" />
  </div>
</template>

<script>
import ResultsItem from './ResultsItem.vue'

export default {
  name: 'AppResults',
  components: { ResultsItem }
}
</script>
