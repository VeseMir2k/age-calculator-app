<template>
  <div class="results-item"><span class="results-item__number">--</span>{{ text }}</div>
</template>

<script>
export default {
  name: 'ResultsItem',
  props: {
    text: {
      type: String,
      required: true
    }
  }
}
</script>
