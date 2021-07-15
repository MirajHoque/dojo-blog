<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search">
    <p>search term - {{ search }}</p>
    <div v-for="element in matchingSearch" :key="element">
      <p>{{ element }}</p>
    </div>
  </div>
</template>

<script>
import { computed, ref } from '@vue/runtime-core'

export default {
  name: 'Home',
  setup() {
    const search = ref('');
    const names = ref(['mario', 'yoshi', 'luigi', 'toad', 'bowser', 'koopa', 'peach'])

    const matchingSearch =  computed( () => {
      return names.value.filter((element) => element.includes(search.value));
    })

     return { names, search, matchingSearch }
  }
 
}
</script>
