<template>
  <div class="results-item">
    <span class="results-item__number">{{ result }}</span
    >{{ text }}
  </div>
</template>

<script>
export default {
  name: 'ResultsItem',
  props: {
    text: {
      type: String,
      required: true
    },
    result: {
      type: String,
      required: true
    }
  }
}
</script>
