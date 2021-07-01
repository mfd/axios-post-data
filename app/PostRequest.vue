<template>
  <div class="card text-center m-3">
    <h5 class="card-header">Simple POST Request</h5>
    <div class="card-body">Returned Id: {{articleId}}</div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "post-request",
  data() {
    return {
      articleId: null
    };
  },
  created() {
    // Simple POST request with a JSON body using axios
    const article = { title: "Vue POST Request Example" };
    axios.post("https://reqres.in/api/articles", article)
      .then(response => this.articleId = response.data.id);
  }
};
</script>
