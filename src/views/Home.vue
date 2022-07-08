<template>
  <div class="home">
    <h1>Home</h1>
    <p>My name is {{name}} ,and I am {{age}} years old.</p>
    <button @click="handleClick">Click me</button>
    <button @click="age++">add age to 1</button>
    <input type="text" v-model="name">
  </div>
</template>

<script>
import {ref} from 'vue'

export default {
  name: 'Home',
  setup(){
    const name = ref('Dogogo')
    const age = ref(28)

    const handleClick = ()=>{
      console.log('you click me');
      name.value = 'Mario'
      age.value = 35
    }
    return {name, age, handleClick}
  }
}
</script>
