<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">
        {{ content.title }}
      </nuxt-link>
    </li>
  </ul>
</template>
<script>
import axios from "axios";
export default {
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は⾃分のサービスidに置き換えてください
      "https://myblog71.microcms.io/api/v1/blog",
      {
        // your-api-key部分は⾃分のapi-keyに置き換えてください
        headers: { "X-API-KEY": "dc8f4186-b016-4f21-8821-e23329b5ef47" },
      }
    );
    return data;
  },
};
</script>
