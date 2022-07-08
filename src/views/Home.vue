<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>Search term - {{search}}</p>
    <div v-for="name in matchNames" :key="name">
      {{name}}      
    </div>
  </div>
</template>

<script>
import {computed, ref} from 'vue'

export default {
  name: 'Home',
  setup(){
    const search = ref('')
    const names = ref(['mario', 'sandy', 'cindy', 'angela', 'john', 'zootopia'])

    const matchNames = computed(()=>{
      return names.value.filter((name)=>{
        return name.includes(search.value)
      })
    })

    return {search, names, matchNames}
  }
}
</script>
