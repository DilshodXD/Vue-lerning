<template>
  <navbar :showModal="showModal" />
  <div class="all">
    <my-modal v-model:show="modalVisible">
      <comment-form @addComment="createComment" />
    </my-modal>
    <comment-list
      :comments="comments"
      @remove="removeComent"
      v-if="!isLoading"
    />
    <div v-else>
      <div class="d-flex justify-content-center">
        <div class="spinner-border" role="status">
          <span class="sr-only"></span>
        </div>
      </div>
    </div>
  </div>
</template> 

<script>
import CommentForm from "./components/CommentForm.vue";
import CommentList from "./components/CommentList.vue";
import Navbar from "./components/Navbar.vue";
import axios from "axios";

export default {
  components: {
    CommentForm,
    CommentList,
    Navbar,
  },
  data() {
    return {
      comments: [],
      modalVisible: false,
      isLoading: false,
    };
  },
  methods: {
    createComment(comments) {
      this.comments.push(comments);
      this.modalVisible = false;
    },
    removeComent(comment) {
      this.comments = this.comments.filter((c) => c.id !== comment.id);
    },
    showModal(modal) {
      this.modalVisible = true;
    },
    async fetchComment() {
      try {
        this.isLoading = true;
        const response = await axios.get(
          "https://jsonplaceholder.typicode.com/comments?_limit=10"
        );
        this.comments = response.data;
        this.isLoading = false;
      } catch (e) {
        console.log(e);
      }finally{
        this.isLoading = false;
      }
    },
  },
  mounted() {
    this.fetchComment();
  },
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.all {
  max-width: 1200px;
  width: 100%;
  padding: 15px;
  margin: 0 auto;
}
</style>