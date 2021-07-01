<template>
  <div class="card text-center m-3">
    <h5 class="card-header">POST Request with Set Headers</h5>
    <div class="card-body">Returned Id: {{articleId}}</div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "post-request-set-headers",
  data() {
    return {
      articleId: null
    };
  },
  created() {
    // POST request using axios with set headers
    const article = { title: "Vue POST Request Example" };
    const headers = { 
      "Authorization": "Bearer my-token",
      "My-Custom-Header": "foobar"
    };
    axios.post("https://reqres.in/api/articles", article, { headers })
      .then(response => this.articleId = response.data.id);
  }
};
</script>
