<template>
  <h1 class="push-top">Welcome To The Forums</h1>
  <CategoryList :categories="categories" />
</template>

<script>
import CategoryList from '../components/CategoryList.vue'
export default {
  components: {
    CategoryList
  },
  computed: {
    categories () {
      return this.$store.state.categories
    }
  }
}
</script>
