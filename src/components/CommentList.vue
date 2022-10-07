<template>
  <div>
    <div class="comment" v-for="comment in comments" v-bind:key="comment.id">
      <h1><b>Ism: </b>{{ comment.name }}</h1>
      <p><b>Mail: </b>{{ comment.mail }}</p>
      <p><b>info: </b>{{ comment.info }}</p>
    </div>
  </div>
</template>

<script>
export default {
    props:{
        comments:{
            type: Array,
            required: true,
        }
    }
};
</script>

<style scoped>
.comment {
  margin: 20px 0;
  background-color: #2a2a2a;
  border-radius: 10px;
  padding: 20px 25px;
}
.comment > h1 {
  color: #fff;
}
.comment > p {
  color: #fff;
}
</style>