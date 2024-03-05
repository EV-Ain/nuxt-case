<template>
  <div class="title">
    <span v-for="(item, index) in titleList" :key="index" :class="{ active: index === current }" @click="current = index">{{ item.title }}</span>
  </div>

  <div class="videoList">
    <Nuxt-link :to="`/video/${item.id}`" v-for="(item, index) in videoList" :key="index">
      <img :src="item.img" alt="" />
    </Nuxt-link>
  </div>
</template>

<script setup>
  import { ref } from "vue";
  let current = ref(0);

  let { data: titleList } = await useFetch("/api/title");
  let { data: videoList } = await useFetch("/api/videoList");



</script>

<style lang="css" scoped>
  .title {
    display: flex;
    justify-content: center;
  }
  .title > span {
    margin-right: 20px;
    color: brown;
  }
  .active {
    border-bottom: 2px solid;
  }
  .videoList {
    display: flex;
    justify-content: center;
    margin: 40px 100px;
  }
  img {
    width: 200px;
    margin-right: 30px;
    /* height: 200px; */
  }
</style>
