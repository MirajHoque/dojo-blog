<template>
  <div class="home">
    home
    <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">Click Me</button>
  </div>
</template>

<script>

export default {
  name: 'Home',
  setup() {
    console.log('setup')

    let name = 'mario';
    let age = 30;

     const handleClick= ()=> {
      console.log('you clicked me');
    } 

    //return { name: name, age: age};
    //if name of key and name of the variable assigning that  are same we shorthand this
    //return { name, age}

    return{ name, age, handleClick}

   
  },

}
</script>
