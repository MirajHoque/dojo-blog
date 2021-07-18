<template>
  <div class="home">
    <h1>Home</h1>

    <div v-if="error"> {{ error }}</div>

    <div v-if="posts.length">
      <PostLists :posts="posts" />
    </div>

    <div v-else>Loading....</div>
  </div>
</template>

<script>
import PostLists from '../components/PostLists.vue'
import { ref } from 'vue'

export default {
  name: 'Home',
  components: {PostLists},
  setup() {
    const posts= ref([])
    const error = ref(null)
    const load = async () => {
      try {
        let data = await fetch(' http://localhost:3000/posts')
        if(!data.ok) {
          throw Error('no data availabe')
        }
        posts.value = await data.json()
      }
      catch(err) {
        error.value = err.message;
        console.log(error.value);
      }

    }
    load()

     return { posts, error }
     
  }
 
}
</script>
