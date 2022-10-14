<template>
  <div class="all">
    <comment-form @addComment="createComment" />
    <comment-list :comments="comments" />
  </div>
</template> 

<script>
import CommentForm from "./components/CommentForm";
import CommentList from "./components/CommentList";

export default {
  components: {
    CommentForm,
    CommentList,
  },
  data() {
    return {
      comments: [
        {id: 1,name: "Dilshod",mail: "Dilshodxdxd@gmail.com",info: "Dilshod",},
        {id: 2,name: "Abduvoris",mail: "Abduvoris@gmail.com",info: "Abduvoris",},
        {id: 3,name: "Temur",mail: "Temur@gmail.com",info: "Temur" },
        {id: 4,name: "Mahmudjon",mail: "Mahmudjon@gmail.com",info: "Mahmudjon",},
        {id: 5,name: "Muhammadamin",mail: "Muhammadamin@gmail.com",info: "Muhammadamin",},
      ],
    };
  },
  methods: { 
    createComment(comments) {
      this.comments.push(comments);
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