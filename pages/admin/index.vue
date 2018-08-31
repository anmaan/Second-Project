<template>
  <div class="admin-page">
    <section class="newpost">
      <AppButton @click="$router.push('/admin/newpost')">Create Post</AppButton>
    </section>
      <section class="existing-posts">
      <h1>Existing Posts</h1>
      <PostList isAdmin />
      </section>
  </div>
</template>


<script>
  import PostList from '@/components/posts/PostList'
  import AppButton from '@/components/UI/AppButton'

  export default {
    layout: 'admin',
    components: {
      PostList,
      AppButton
    }
  }
</script>

<style scoped>
  .admin-page {
    padding: 20px;
  }

  .newpost {
    text-align: center;
    border-bottom: 2px solid #ccc;
    padding-bottom: 10px;
  }

  .existing-posts h1 {
    text-align: center;
  }
</style>
