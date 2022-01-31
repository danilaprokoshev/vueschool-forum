<template>
  <h1>{{ category.name }}</h1>
  <ForumList
    :title="category.name"
    :forums="getForumsForCategory(category)"
  />
</template>

<script>
import ForumList from '../components/ForumList.vue'
import sourceData from '@/data.json'

export default {
  name: 'Category',
  components: {
    ForumList
  },
  props: {
    id: {
      type: String,
      required: true
    }
  },
  data () {
    return {
      categories: sourceData.categories
    }
  },
  computed: {
    category () {
      return this.categories.find(({ id }) => id === this.id)
    }
  },
  methods: {
    getForumsForCategory (category) {
      return sourceData.forums.filter(({ categoryId }) => categoryId === category.id)
    }
  }
}
</script>
