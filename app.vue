<template>
  <!-- 相当于vue的routerview -->
  <!-- keepalive缓存10级页面 -->
  <NuxtPage :keepalive="{ max: 10 }" />
</template>
<script setup lang="ts">
  useSeoMeta({
    title: "视频标题", //标题
    description: "国内知名网站", //描述
    keywords: "视频" //搜索关键字
  });
</script>
