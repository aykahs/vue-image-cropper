<!--
 * @Author: Marvin 454846659@qq.com
 * @Date: 2023-10-19 17:42:53
 * @LastEditors: Marvin 454846659@qq.com
 * @LastEditTime: 2023-12-26 18:10:59
 * @FilePath: /vue-image-cropper/src/App.vue
 * @Description: 
 * 
 * Copyright (c) 2023 by Marvin, All Rights Reserved. 
-->
<template>
  <image-cropper @confirm="confirm" @real-time="realTime">
    <!-- <template #open></template> -->
    <template v-slot:title>
    Image Crop
    </template>
    <template v-slot:width>
      width
    </template>
    <template v-slot:high>
      high
    </template>

  </image-cropper>
  <img style="width: 200px;" :src="imgUrl" :alt="imgUrl">
</template>

<script lang="ts" setup>
import { ref } from 'vue';

const imgUrl = ref('')
const confirm = (data: any) => {
  imgUrl.value = data.dataURL
}
const realTime = (data: any) => {
  imgUrl.value = data.dataURL
}
</script>