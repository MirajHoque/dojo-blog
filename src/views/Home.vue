<template>
  <div class="home">
    home
    <p >My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
    <input type="text" v-model="name">
    <button v-on:click="age++">add 1 to age</button>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';

export default {
  name: 'Home',
  setup() {
  
    //const p= ref('hello');

    let name = ref('mario');
    let age = ref(30);

     const handleClick= ()=> {
       name.value = 'luigi';
       age.value = 35;
    } 

    //return { name: name, age: age};
    //if name of key and name of the variable assigning that  are same we shorthand this
    //return { name, age}

    return{ name, age, handleClick,}

   
  },

}
</script>
