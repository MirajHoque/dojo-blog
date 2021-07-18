<template>
  <div class="home">
    <h1>Home</h1>
    <PostLists v-if="showPosts" :posts="posts" />
    <button @click=" showPosts=!showPosts">show posts</button>
    <button @click="posts.pop()">delete a post</button>
  </div>
</template>

<script>
import PostLists from '../components/PostLists.vue'
import { ref } from 'vue'

export default {
  name: 'Home',
  components: {PostLists},
  setup() {
    const posts= ref([
      {title: 'welcome to the blog', body: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Deserunt ad sed veniam possimus quo harum soluta at vero! Ducimus reiciendis ea nostrum quos minus quas dicta laudantium sint, enim laborum recusandae eveniet cumque quasi perspiciatis voluptates vero iure molestias mollitia aperiam, harum explicabo sit repellendus repellat itaque? Doloremque deleniti adipisci odio voluptatibus vel! Obcaecati, dolorem optio inventore aperiam doloremque cupiditate vitae debitis alias consectetur accusamus placeat eos porro voluptatibus dolorum incidunt fugiat eveniet illum voluptatum autem in asperiores? Quasi tempore officia enim iusto saepe quam, tenetur possimus, dolores ipsam qui magnam. Quidem, quos maiores adipisci non fugit blanditiis veniam soluta! Recusandae minima amet magni? Harum vel, eveniet nam ducimus possimus quis in fuga ab dolores perspiciatis suscipit delectus ipsum quisquam quidem similique necessitatibus at incidunt vitae porro quo unde odit. Saepe nihil velit dolorum iure, quos neque animi ipsa nam aliquam, aperiam autem. Voluptatem repellendus iure in quidem, omnis officia!', id: 1},
      {title: 'top 5 css tips', body: 'lorem ipsum', id: 2}
    ])
    const showPosts = ref(true)

     return { posts, showPosts }
     
  }
 
}
</script>
