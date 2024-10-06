<template>
  <div class="home">
    <h1>DropZone</h1>
    <DropZone @drop.prevent="drop" @change="selectedFile" />
    <span class="file-info">File : {{ localFile.name }} </span>
  </div>
 
</template>

<script setup>

import { ref } from 'vue';
import DropZone from './components/DropZone.vue'

let localFile = ref("")

const drop = (e) => {
  localFile.value = e.dataTransfer.files[0]
}

const selectedFile = () => {
  localFile.value = document.querySelector('.localFile').files[0]
}

</script>

<style scoped>
.home{
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #f1f1f1;

  h1{
    font-size: 40px;
    margin-bottom: 32px;
  }

  .file-info{
    margin-top: 32px;
  }
}


</style>
