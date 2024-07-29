<template>
  <div class="form-group">
    <label class="form-group__label" :for="name">{{ labelText }}</label>
    <input
      :id="name"
      class="form-group__input"
      type="text"
      :name="name"
      :placeholder="placeholder"
    />
  </div>
</template>

<script>
export default {
  name: 'AppFormGroup',
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
