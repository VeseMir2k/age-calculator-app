<template>
  <span :class="className">{{ error }} </span>
</template>

<script>
export default {
  name: 'FormError',
  props: {
    error: {
      type: String
    },
    className: {
      type: String,
      required: true
    }
  }
}
</script>
