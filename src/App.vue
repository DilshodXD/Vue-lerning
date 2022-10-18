<template>
  <navbar :showModal="showModal"/>
  <div class="all">
    <my-modal v-model:show="modalVisible">
      <comment-form @addComment="createComment" />
    </my-modal>
    <comment-list :comments="comments" @remove="removeComent" />
  </div>
</template> 

<script>
import CommentForm from "./components/CommentForm.vue";
import CommentList from "./components/CommentList.vue";
import Navbar from "./components/Navbar.vue";

export default {
  components: {
    CommentForm,
    CommentList,
    Navbar,
  },
  data() {
    return {
      comments: [
        {id: 1, name: "Dilshod", mail: "Dilshodxdxd@gmail.com", info: "Dilshod"},
        {id: 2, name: "Abduvoris", mail: "Abduvoris@gmail.com", info: "Abduvoris"},
        {id: 3, name: "Temur", mail: "Temur@gmail.com", info: "Temur"},
        {id: 4, name: "Mahmudjon", mail: "Mahmudjon@gmail.com", info: "Mahmudjon"},
        {id: 5, name: "Muhammadamin", mail: "Muhammadamin@gmail.com", info: "Muhammadamin"},
      ],
      modalVisible: false,
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