<template>
  <div class="comment">
    <div>
      <h1 class="name"><b>Ism: </b>{{ comment.name }}</h1>
      <p class="mail"><b>Mail: </b>{{ comment.mail }}</p>
      <p class="info"><b>info: </b>{{ comment.info }}</p>
    </div>
    <button class="btn-danger">Delete</button>
  </div>
</template>

<script>
export default {
  props: {
    comments: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.name{
  color:#fff;
}
.mail,.info{
  color:#fff;
}
</style>