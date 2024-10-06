<template>
  <div 
    @dragenter.prevent="toggleActive" 
    @dragleave.prevent="toggleActive" 
    @dragover.prevent
    @drop.prevent="toggleActive"
    :class="{'active-dropzone': active}"
    class="dropzone"
  >
    <span>Drag or drop files</span>
    <span>OR</span>
    <label for="localFile">Select file</label>
    <input type="file" id="localFile" class="localFile" />
  </div>
</template>

<script setup>

  import { ref } from 'vue';

  const active = ref(false);

  const toggleActive = () => {
    active.value = !active.value;
    console.log(active.value)
  };

</script>


<style scoped>
.dropzone {
  width: 400px;
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  row-gap: 16px;
  border: 2px dashed #41b883;
  background-color: #fff;
  transition: 0.3s ease all;

  label{
    padding: 8px 12px;
    color: #fff;
    background-color: #41b883;
    transition: 0.3s ease all;
  }

  input{
    display: none;
  }
}

.active-dropzone{
  color: #fff;
  border-color: #fff;
  background-color: #41b883;

  label{
    background-color: #fff;
    color: #41b883;
  }
}

</style>
