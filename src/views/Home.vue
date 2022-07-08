<template>
  <div class="home">
    <h1>Home</h1>
    <p ref="p">My name is {{name}} ,and I am {{age}} years old.</p>
    <button @click="handleClick">Click me</button>
  </div>
</template>

<script>
import {ref} from 'vue'

export default {
  name: 'Home',
  setup(){
    const name = 'Dogogo'
    const age = 28

    const p = ref(null)
    console.log(p, p.value);

    const handleClick = ()=>{
      console.log('you click me');
      console.log(p, p.value);
      p.value.classList.add('test')
    }
    return {name, age, handleClick, p}
  }
}
</script>
