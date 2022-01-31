<template>
  <h1>Welcome To The Forums</h1>
  <CategoryList :categories="categories" />
</template>

<script>
import sourceData from '@/data.json'
import CategoryList from '../components/CategoryList.vue'
export default {
  components: {
    CategoryList
  },
  data () {
    return {
      categories: sourceData.categories,
      forums: sourceData.forums
    }
  }
}
</script>
