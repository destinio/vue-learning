<script setup lang="ts">
import { ref, onMounted } from 'vue'
import Button from './Button.vue'

const count = ref(0)

function inc() {
  count.value++
}

function dec() {
  count.value--
}

function handleClick() {
  console.log('I have been clicked')
}

onMounted(() => {
  console.log(`The initial count is ${count.value}.`)
})
</script>

<template>
  <div class="main">
    <div class="button" @click="inc">+</div>
    <span>{{ count }}</span>
    <div class="button" @click="dec">-</div>
    <Button text="Click Mee" color="red" @created="handleClick" />
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

.button {
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
