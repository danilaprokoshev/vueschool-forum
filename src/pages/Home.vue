<template>
  <h1>Welcome To The Forums</h1>
  <ForumList :forums="forums"/>
</template>

<script>
import sourceData from '@/data.json'
import ForumList from '../components/ForumList.vue'
export default {
  components: {
    ForumList
  },
  data () {
    return {
      forums: sourceData.forums
    }
  }
}
</script>
