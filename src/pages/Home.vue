<template>
  <h1>Welcome To The Forums</h1>
  <div class="col-full" v-for="category in categories" :key="category.id">
    <CategoryListItem :category="category"/>
  </div>
</template>

<script>
import sourceData from '@/data.json'
import CategoryListItem from '../components/CategoryListItem.vue'
export default {
  components: {
    CategoryListItem
  },
  data () {
    return {
      categories: sourceData.categories,
      forums: sourceData.forums
    }
  }
}
</script>
