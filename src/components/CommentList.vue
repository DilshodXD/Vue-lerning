<template>
  <div>
    <div class="comment" v-for="comment in comments" :key="comment.id">
      <comment-item :comment="comment"/>
    </div>
  </div>
</template>

<script>
import CommentItem from "./CommentItem.vue"

export default {
  components: {
    CommentItem,
  },
  props: {
    comments: {
      type: Array,
      required: true,
    },
  },
};
</script>

<style scoped>
.comment {
  margin: 20px 0;
  background-color: #2a2a2a;
  border-radius: 10px;
  padding: 20px 25px;
}
</style>