<template>
  <div class="forum-list">
  <h2 class="list-title">
    <router-link v-if="category" :to="{ name: 'Category', params: { id: this.category.id } }">
      {{ category.name }}
    </router-link>
    <span v-else>Forums</span>
  </h2>
    <ForumList :forums="categoryForums" />
  </div>
</template>

<script>
import ForumList from './ForumList'
import sourceData from '@/data.json'

export default {
  name: 'CategoryListItem',
  components: { ForumList },
  props: {
    category: {
      type: Object,
      required: false
    }
  },
  computed: {
    categoryForums () {
      return this.forums.filter(({ categoryId }) => categoryId === this.category.id)
    }
  },
  data () {
    return {
      // categories: sourceData.categories,
      forums: sourceData.forums
    }
  }
}
</script>
