<template>
  <ul>
    <!-- <li v-for="item in items" @click="onClick">{{ item }}</li> -->
    <li
      v-for="item in items"
      @click="onClick2(item)"
      :class="{'is-clickable': clickable}"
    >{{ item }}</li>
  </ul>
</template>

<script>

export default {
  name: 'TList',
  props: {
    items: {
      type: Array
    },
    clickable: {
      type: Boolean,
      default: false
    }
  },
  methods: {
    onClick(e) {
      if (this.clickable) {
        this.$emit('clicked', e.target.textContent)
      }
    },
    onClick2(par) {
      if (this.clickable) {
        this.$emit('clicked', par)
      }

    }
  }
}

</script>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  border: 1px solid #cdcdcd;
  border-radius: 5px;
  width: 300px;
}

li {
  padding: .3em .7em;
  font-size: 1rem;
}

.is-clickable {
  cursor: pointer;
}
</style>