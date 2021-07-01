<template>
  <div class="card text-center m-3">
    <h5 class="card-header">POST Request with Error Handling</h5>
    <div class="card-body">Error message: {{errorMessage}}</div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "post-request-error-handling",
  data() {
    return {
      articleId: null,
      errorMessage: null
    };
  },
  created() {
    // POST request using axios with error handling
    const article = { title: "Vue POST Request Example" };
    axios.post("https://reqres.in/invalid-url", article)
      .then(response => this.articleId = response.data.id)
      .catch(error => {
        this.errorMessage = error.message;
        console.error("There was an error!", error);
      });
  }
};
</script>
