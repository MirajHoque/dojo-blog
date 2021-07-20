<template>
  <div class="post">
    <router-link :to="{ name: 'Details', params: { id: post.id}}">
      <h3>{{ post.title }}</h3>
    </router-link>
    <h3>{{ snippet }}</h3>
    <span v-for="element in post.tags" :key="element">
      #{{ element }}
    </span>
  </div>
</template>

<script>
import { computed } from '@vue/runtime-core'
export default {
  name: 'SinglePost',
  props: ['post'],
  setup(props) {
    const snippet= computed( () => {
      return props.post.body.substring(0,100) + '...';
    })

    return { snippet }
  }

}
</script>

<style>

</style>