<template>
  <div>
    <label :for="control">{{ label }}</label>
    <input
      :id="control"
      :autocomplete="hasAutocomplete"
      :type="inputType"
      :placeholder="hasPlaceholder"
      :disabled="isDisabled"
      :readonly="isReadonly"
      :autofocus="hasAutofocus"
      v-model="myValue"
      @input="onInput"
    >
  </div>

</template>

<script>

export default {
  name: 'TInput',
  props: {
    label: String,
    control: String,
    hasAutocomplete: {
      type: String,
      default: 'off'
    },
    inputType: {
      type: String,
      default: 'text'
    },
    hasPlaceholder: {
      type: String,
      default: ''
    },
    isDisabled: {
      type: Boolean,
      default: false
    },
    isReadonly: {
      type: Boolean,
      default: false
    },
    hasAutofocus: {
      type: Boolean,
      default: false
    }
  },
  data () {
    return {
      myValue: ''
    }
  },
  methods: {
    onInput(e) {
      this.$emit('has-input', { control: this.control, value:  e.target.value })
    }
  }
}

</script>

<style scoped>
  div {
    display: flex;
    flex-direction: column;
  }
  input {
    font-size: 1.2rem;
    padding: .3em .6em;
  }
</style>