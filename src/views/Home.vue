<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>search term - {{ search }}</p>

    <div v-for="element in matchingSearch" :key="element">
      <p>{{ element }}</p>
    </div>
    
     <button @click="handleClick">stop watching</button>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from '@vue/runtime-core'

export default {
  name: 'Home',
  setup() {
    const search = ref('');
    const names = ref(['mario', 'yoshi', 'luigi', 'toad', 'bowser', 'koopa', 'peach'])
    
    const stopWatch = watch(search, () => {
      console.log('watch function run');
    })
    const stopWatchEffec= watchEffect( ()=> {
      console.log('watchEffect function run', search.value);
    })

    const matchingSearch =  computed( () => {
      return names.value.filter((element) => element.includes(search.value));
    })

    const handleClick = () => {
      stopWatch();
      stopWatchEffec()
    }

     return { names, search, matchingSearch, handleClick }
  }
 
}
</script>
