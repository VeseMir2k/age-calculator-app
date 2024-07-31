<template>
  <div class="form-group">
    <label
      class="form-group__label"
      :for="name"
      :class="{ 'form-group__label--error': errors[name] || errors.date }"
      >{{ labelText }}</label
    >
    <input
      :id="name"
      class="form-group__input"
      type="text"
      :name="name"
      :placeholder="placeholder"
      :class="{ 'form-group__input--error': errors[name] || errors.date }"
      @input="(e) => $emit('update:modelValue', e.target.value)"
    />
    <FormError v-if="errors[name]" :error="errors[name]" className="form-group-error" />
  </div>
</template>

<script>
import FormError from './FormError.vue'

export default {
  name: 'FormGroup',
  components: { FormError },
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
    },
    errors: {
      type: Object
    }
  }
}
</script>
