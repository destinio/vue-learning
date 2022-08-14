<script lang="ts">
import { defineComponent } from 'vue'
import Button from './Button.vue'

export default defineComponent({
  data() {
    return {
      count: 0,
    }
  },
  methods: {
    inc(_name: string) {
      this.count++
    },
    dec() {
      this.count--
    },
  },
  components: { Button },
})
</script>

<template>
  <div class="main">
    <button @click="inc('joe')">+</button>
    <span>{{ count }}</span>
    <button @click="dec">-</button>
    <Button text="Click Mee" />
  </div>
</template>

<style scoped lang="scss">
.main {
  background-color: #333;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 2rem;
  height: 100vh;
}

span {
  font-size: 2rem;
  display: inline-block;
  width: 2rem;
  text-align: center;
}

button {
  display: block;
  height: 4rem;
  width: 4rem;
  background-color: none;
  font-size: 2rem;
  border: 2px solid blue;
  border-radius: 50%;
  display: grid;
  place-items: center;
  transition: transform 150ms ease-in-out;
  cursor: pointer;

  &:hover {
    transform: scale(1.2);
  }
}
</style>
