<template>
  <div class="form-group">
    <label class="form-group__label" :for="name">{{ labelText }}</label>
    <input
      class="form-group__input"
      :id="name"
      type="text"
      :name="name"
      :placeholder="placeholder"
    />
  </div>
</template>

<script>
export default {
  name: 'CalculatorAgeFormInput',
  props: {
    name: {
      type: String,
      required: true
    },
    placeholder: {
      type: String,
      required: true
    },
    labelText: {
      type: String,
      required: true
    }
  }
}
</script>
