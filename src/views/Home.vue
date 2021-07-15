<template>
  <div class="home">
    home
    <p ref="p">My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity';

export default {
  name: 'Home',
  setup() {
    console.log(this)

    const p= ref('hello');
    console.log(p);

    let name = 'mario';
    let age = 30;

     const handleClick= ()=> {
      console.log(p, p.value);
      p.value.classList.add("test");
      p.value.textContent = 'Hello, ninjas'
    } 

    //return { name: name, age: age};
    //if name of key and name of the variable assigning that  are same we shorthand this
    //return { name, age}

    return{ name, age, handleClick,p}

   
  },

}
</script>
