<template>
  <div v-show="comments.length > 0">
    <h3 class="text-center mt-5 mb-4 text-primary">Comments</h3>
    <div
      class="comment"
      v-for="comment in comments"
      :key="comment.id"
      @remove="$emit('remove', comment)"
    >
      <comment-item :comment="comment" @remove="$emit('remove', comment)" />
    </div>
  </div>
  <div v-show="comments.length == 0">
    <h2 class="text-center text-danger">we can not found ary comments</h2>
  </div>
</template>

<script>
import CommentItem from "./CommentItem.vue";

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