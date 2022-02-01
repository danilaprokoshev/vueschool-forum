<template>
  <div v-if="thread" class="col-large push-top">
    <h1>{{ thread.title }}</h1>

    <post-list :posts="threadPosts" />
    <post-editor @save="addPost"/>
  </div>
  <div v-else>
    <h1>Not Found</h1>
    <router-link :to="{ name: 'Home' }">Read some cool threads</router-link>
  </div>
</template>

<script>

import PostList from '@/components/PostList'
import PostEditor from '@/components/PostEditor'
export default {
  components: {
    PostList,
    PostEditor
  },
  props: {
    id: {
      type: String,
      required: true
    }
  },
  computed: {
    threads () {
      return this.$store.state.threads
    },
    posts () {
      return this.$store.state.posts
    },
    thread () {
      return this.threads.find(thread => thread.id === this.id)
    },
    threadPosts () {
      return this.posts.filter(post => post.threadId === this.id)
    }
  },
  methods: {
    addPost (eventData) {
      const post = {
        ...eventData.post,
        threadId: this.id
      }
      this.$store.dispatch('createPost', post)
    }
  }
}
</script>
