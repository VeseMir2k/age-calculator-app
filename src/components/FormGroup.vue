<template>
  <div class="form-group">
    <label class="form-group__label" :for="name" :class="{ 'form-group__label--error': error }">{{
      labelText
    }}</label>
    <input
      :id="name"
      class="form-group__input"
      type="text"
      :name="name"
      :placeholder="placeholder"
      :class="{ 'form-group__input--error': error }"
      @input="(e) => $emit('update:modelValue', e.target.value)"
    />
    <FormError v-if="error" :error="error" className="form-group-error" />
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
    error: {
      type: String
    }
  }
}
</script>
