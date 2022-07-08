<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>Search term - {{search}}</p>
    <div v-for="name in matchNames" :key="name">
      {{name}}      
    </div>
    <button @click="handleClick">Stop Watching</button>
  </div>
</template>

<script>
import {computed, ref, watch, watchEffect} from 'vue'

export default {
  name: 'Home',
  setup(){
    const search = ref('')
    const names = ref(['mario', 'sandy', 'cindy', 'angela', 'john', 'zootopia'])

    const stopWatch = watch(search, ()=>{
      console.log('watch func run');
    })
    const stopEffect = watchEffect(()=>{
      console.log('watchEffect func run', search.value);
    })

    const handleClick = () => {
      stopWatch();
      stopEffect();
    }

    const matchNames = computed(()=>{
      return names.value.filter((name)=>{
        return name.includes(search.value)
      })
    })

    return {search, names, matchNames, handleClick}
  }
}
</script>
