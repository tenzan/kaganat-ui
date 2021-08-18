<template>
  <div class="container">
    <div v-if="error">
      {{ error }}
    </div>
    <ul v-else>
      <li v-for="post in posts" :key="post.id">
        {{ post.title }} | {{ post.created_at }} <br />
        {{ post.body }}
        <br />
        {{ post.subcategory.name }}
        <br />
        <br />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      posts: [],
      error: null,
    }
  },
  async mounted() {
    try {
      const response = await this.$axios.get('/posts')
      this.posts = response.data
    } catch (error) {
      this.error = error
    }
  },
}
</script>
