<template>
  <button
    @click="onClick"
    :class="{
      'btn-small': size === 'small',
      'btn-medium': size === 'medium',
      'btn-large': size === 'large'
    }"
  >{{ label }}</button>
</template>

<script>

export default {
  name: 'TButton',
  props: {
    label: {
      type: String,
      required: true
    },
    size: {
      type: String,
      default: 'medium'
    }
  },
  methods: {
    onClick() {
      this.$emit('clicked')
    }
  }
}


</script>

<style scoped>
  button {
    display: block;
    border: 1px solid #787878;
    background: white;
    color: #222222;
    padding: .3em .7em;
    border-radius: 5px;
  }
  .btn-small {
    font-size: 1rem;
  }
  .btn-medium {
    font-size: 1.4rem;
  }
  .btn-large {
    font-size: 2rem;
  }
</style>