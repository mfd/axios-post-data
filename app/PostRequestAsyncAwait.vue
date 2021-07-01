<template>
  <div class="card text-center m-3">
    <h5 class="card-header">POST Request with Async/Await</h5>
    <div class="card-body">Returned Id: {{articleId}}</div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "post-request-async-await",
  data() {
    return {
      articleId: null
    };
  },
  async created() {
    // POST request using axios with async/await
    const article = { title: "Vue POST Request Example" };
    const response = await axios.post("https://reqres.in/api/articles", article);
    this.articleId = response.data.id;
  }
};
</script>
