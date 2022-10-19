<template>
  <div class="home">
    home
    <p ref="p">My name is {{ name }} and age is {{ age }}</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'HomeView',
  setup() {
    const p = ref(null)

    const name = ref('mario') //refrence object is constant but the value can change
    const age = ref(30) //the ref makes this a reactive value

    name.value//gets the value of the ref

    const handleClick = () => {
      name.value = 'luigi'
      age.value = 35
    }

    return { name: name, age: age, handleClick, p } //when we return a reactive value, we don't have to call .value in the template
  }
}
</script>
