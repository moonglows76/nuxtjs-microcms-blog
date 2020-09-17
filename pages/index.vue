<template>
  <ul>
    <li v-for="content in contents" :key="content.id">
      <nuxt-link :to="`/${content.id}`">{{ content.title }}</nuxt-link>
    </li>
  </ul>
</template>
<script>
import axios from "axios";
export default {
  async asyncData() {
    const { data } = await axios.get(
      // your-service-id部分は⾃分のサービスidに置き換えてください
      "https://curry-kagoshima.microcms.io/api/v1/shop",
      {
        // your-api-key部分は⾃分のapi-keyに置き換えてください
        headers: { "X-API-KEY": "2c5e9fb9-aa22-416a-b60a-e8ad44313dbf" },
      }
    );
    return data;
  },
};
</script>
