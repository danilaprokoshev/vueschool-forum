<template>
  <h1>{{ category.name }}</h1>
  <div class="col-full">
    <CategoryListItem :category="category" />
  </div>
</template>

<script>
import CategoryListItem from '../components/CategoryListItem'
import sourceData from '@/data.json'
export default {
  name: 'Category',
  components: {
    CategoryListItem
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
  }
}
</script>
