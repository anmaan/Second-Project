<template>
  <div class="admin-new-post-page">
    <section class="new-post-form">
      <AdminPostForm @submit="onSubmitted"/>
    </section>
  </div>
</template>

<script>
  import axios from 'axios'
  import AdminPostForm from '@/components/Admin/AdminPostForm'


  export default {
    layout: 'admin',
    components: {
      AdminPostForm
    },
    methods: {
      onSubmitted(postData) {
        axios.post('https://e0adff32-e836-415b-b99f-8afcf7b46da6.mock.pstmn.io/posts', postData)
          .then(result => console.log(result))
          .catch(e => console.log(e))
      }
    }
  };
</script>


<style scoped>
  .new-post-form {
    width: 90%;
    margin: 20px auto;
  }

  @media (min-width: 768px) {
    .new-post-form {
      width: 500px;
    }
  }
</style>
