<script lang="ts">
import { defineComponent, computed } from 'vue'

export default defineComponent({
  props: {
    color: String,
    text: String,
  },
  clicked() {
    this.$emit('callback')
  },
  computed: {
    style() {
      return {
        'background-color': this.color,
      }
    },
  },
})
</script>
<template>
  <button @click="" :style="style">{{ text }}</button>
</template>

<style scoped>
button {
  padding: 1rem 2rem;
  font-size: 2rem;
}
</style>
