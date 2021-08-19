<template>
  <div class="container">
    <div v-if="error">
      {{ error }}
    </div>
    <ul v-else>
      <li v-for="post in posts" :key="post.id">
        <div class="box">
          <p>{{ $moment(post.created_at).format('LLLL') }}</p>
          <h1 class="title">{{ post.title }}</h1>
          <h2 class="subtitle">
            {{ post.body }}
          </h2>
        </div>
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
