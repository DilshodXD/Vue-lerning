<template>
  <div>
    <div>
      <h1 class="title">Add comments</h1>
      <form @submit.prevent class="input-all">
        <input
          v-model="comments.name"
          type="text"
          class="input"
          placeholder="Enter you name"
        />
        <input
          v-model="comments.mail"
          type="email"
          class="input"
          placeholder="Enter you mail"
        />
        <input
          v-model="comments.info"
          type="text"
          class="input"
          placeholder="Enter you comment"
        />
        <button @click="createComment" class="btn">add comments</button>
      </form>
    </div>
  </div>
</template>

<script>
import { addComment } from '@babel/types';

export default {
  data() {
    return {
      comments: {
        name: "",
        mail: "",
        info: "",
      },
    };
  },
  methods: {
    createComment() {
      this.comments.id = Date.now();
        this.$emit('addComment', this.comments);
        this.comments = {
            name: "",
            mail: "",
            info: "",
        }
    },
  },
};
</script>

<style scoped>
.title {
  font-size: 24px;
}
.input-all {
  display: flex;
  flex-direction: column;
  gap: 6px;
}
.input {
  width: 400px;
  outline: none;
  border: 1px solid black;
  border-radius: 8px;
  padding: 5px 16px;
}
.btn {
  width: max-content;
  border-radius: 8px;
  background-color: #2a2a2a;
  color: #fff;
  font-size: 18px;
  font-weight: 500;
  border: 1px solid #2a2a2a;
}
.btn:hover {
  background-color: #fff;
  color: #2a2a2a;
  border: 1px solid #2a2a2a;
}
</style>