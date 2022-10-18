<template>
  <div class="comment-inn">
    <div>
      <h3 class="name"><b>Ism: </b>{{ comment.name }}</h3>
      <p class="mail"><b>Mail: </b>{{ comment.mail }}</p>
      <p class="info"><b>info: </b>{{ comment.info }}</p>
    </div>
    <my-button class="btn-danger" @click="$emit('remove', comment)">Delete</my-button>
  </div>
</template>

<script>
export default {
  props: {
    comment: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.comment-inn{
  display: flex;
  justify-content: space-between;
}
.name{
  color:#fff;
  margin-bottom: 10px;
}
.mail,.info{
  color:#fff;
  margin-bottom: 10px;
}
.btn-danger{
  height: min-content;
  border: none;
  padding: 5px 18px;
  border-radius: 5px;
  color: #fff;
  font-weight: 500;
  font-size: 15px;
  background-color: rgb(235, 31, 31);
  transition: .2s;
}
.btn-danger:hover{
  background-color: rgb(235, 31, 31, 0.6);
}
</style>