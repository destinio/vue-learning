<script lang="ts">
import { reactive, ref } from 'vue'

interface State {
  count: number
}

export default {
  setup() {
    // const state: State = reactive({ count: 0 })
    const { value: state } = ref<State>({ count: 0 })

    function inc() {
      state.count++
    }

    return {
      state,
      inc,
    }
  },
}
</script>

<template>
  <div @click="inc">{{ state.count }}</div>
</template>

<style></style>
