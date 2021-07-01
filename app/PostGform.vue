<template>
  <div class="card text-center m-3">
    <h5 class="card-header">Simple POST Request</h5>
    <form ref="formElement" @submit.prevent="response">
      <fieldset>
        <h5>Your favorite song</h5>
        <input
          type="radio"
          checked
          name="entry.1281131735"
          value="HELLO"
          required
        />
        HELLO
        <input type="radio" name="entry.1281131735" value="Maps" required />
        Maps
      </fieldset>
      <button>Send</button>
    </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "post-gform",
  data() {
    return {
      articleId: null,
    };
  },
  created() {
    // Simple POST request with a JSON body using axios
    // const article = { title: "Vue POST Request Example" };
    // axios
    //   .post("https://reqres.in/api/articles", article)
    //   .then((response) => (this.articleId = response.data.id));
  },
  methods: {
    response() {
      let vm = this;
      let formElement = vm.$refs.formElement;
      let formData = new FormData(formElement);
      const id = "1FAIpQLSfZJZwKDh9KtwZzeO8g1xmEA49Z3z0BKj8tLM9QeUWjM2tvKg";
      var url = `https://docs.google.com/forms/d/e/${id}/formResponse`;
      console.log(url);
      axios.post(url, formData).then(function (response) {
        console.log(response);
      });
    },
  },
};
</script>
