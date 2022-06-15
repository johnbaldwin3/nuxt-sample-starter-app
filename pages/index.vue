<script setup lang="ts">
import { useSampleComposable } from '~~/composables/useSampleComposable';

const newText = ref('ref based on sample composable')
const inputText = ref('')
function handleButtonClick(text: string) {
  newText.value = useSampleComposable(text)
}
</script>

<template>
  <div class="home-page">
    <NuxtLayout name="sample-layout">
      <h2>Index Page (Home)</h2>
      <div class="sample-wrapper">
        <label class="sample-input-label" for="sample-input">text to add: </label>
        <input class="sample-input" type="text" label="sample-input" v-model="inputText"/>
        <button class="sample-input-button" @click="handleButtonClick(inputText)">Add Text</button>
      </div>
      <div><h3>newText: {{ newText }}</h3></div>
    </NuxtLayout>
  </div>
</template>

<style scoped>
.sample-wrapper {
  line-height: 25px;
  height: 25px;
}
.sample-wrapper * {
  vertical-align: middle;
}
.sample-input {
  box-sizing: border-box;
  width: 200px;
  height: 100%;
}
.sample-input-label {
  font-size: 20px;
}

.sample-input-button {
  display: inline-block;
  box-sizing: border-box;
  padding: 0 1rem;
  background-color: #57A3E7;
  color: white;
  font-size: 18px;
}
</style>