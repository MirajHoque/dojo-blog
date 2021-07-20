<template>
  <div class="post-lists">
    <div v-for="element in posts" :key="element.id">
      <SinglePost :post="element" />
    </div>
  </div>
</template>
 
<script>
import { onMounted, onUnmounted, onUpdated } from '@vue/runtime-core'
import SinglePost from '../components/SinglePost.vue'

export default {
  name: 'PostLists',
  components: { SinglePost },
  props: ['posts'],

  //using props inside setup function
  setup(props){
    onMounted( () => console.log('component mounted'));
    onUnmounted( () => console.log('component unmounted'));
    onUpdated( () => console.log('component updated'));

  }
}
</script>

<style>

</style>