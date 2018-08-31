<template>
  <div>
    <section class="intro">
      <h1>Get the latest Smol news</h1>
    </section>
    <section class="posts">
      <PostPreview
        v-for="post in posts"
        :key="post.id"
        :pid="post.id"
        :is-admin="isAdmin"
        :thumbnail="post.thumbnail"
        :title="post.title"
        :previewText="post.previewText"/>
    </section>
  </div>
</template>

<script>
  import PostPreview from '@/components/posts/PostPreview'

  export default{
    components: {
      PostPreview
    },
    props: {
      isAdmin: {
        type: Boolean,
        default: false
      },
      posts: {
        type: Array,
        required: true
      }
    }
  }
</script>

<style scoped>

  .posts {
    display: flex;
    padding: 20px;
    box-sizing: border-box;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
  }
</style>
