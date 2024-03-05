<template>
  <h1>{{ detail.title }}</h1>
  <img :src="detail.img" alt="" />
</template>

<script setup>
  let { data: videoList } = await useFetch("/api/videoList");

  let { params } = useRoute();

  let detail = videoList.value.find(i => i.id == params.id);

  useSeoMeta({
    title: detail.title //标题
  });
</script>

<style lang="scss" scoped></style>
