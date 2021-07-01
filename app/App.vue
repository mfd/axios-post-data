<template>
  <div>
    <h3 class="p-3 text-center">Vue HTTP POST Requests with Axios</h3>
    <!-- <post-request/> -->
    <PostGform />
    <!-- <post-request-async-await/>
    <post-request-error-handling/>
    <post-request-set-headers/> -->
  </div>
</template>

<script>
import PostRequest from "./PostRequest";
import PostGform from "./PostGform";
import PostRequestAsyncAwait from "./PostRequestAsyncAwait";
import PostRequestErrorHandling from "./PostRequestErrorHandling";
import PostRequestSetHeaders from "./PostRequestSetHeaders";

export default {
  name: "app",
  components: {
    PostGform,
    PostRequest,
    PostRequestAsyncAwait,
    PostRequestErrorHandling,
    PostRequestSetHeaders,
  },
};
</script>
