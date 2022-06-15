<script lang="ts" setup>
import { onMounted } from 'vue';
// script using Vue Composition API with setup and TypeScript

const sampleNumber = ref(0);
function handleSampleButtonClick() {
  return sampleNumber.value ++;
}
onMounted(() => {
  alert(`Mounted lifecycle with sample number: ${sampleNumber.value}`)
}) 
</script>

<template>
  <div class="sample-component-div">
    <div class="column">
      <button
        class="sample-button"
        @click="handleSampleButtonClick"
      >
        Sample Increment Button
      </button>
      <div>
        <h3> Click the button to watch me change a ref item: {{ sampleNumber }}</h3>
      </div>
    </div>
  </div>
</template>

<style scoped>
/* scoped style prevents css 'leaking' */
.sample-component-div {
  display: flex;
  flex-direction: row;
  /* justify-content: space-between; */
}

.column {
  flex-direction: column;
}

.sample-button {
  padding: 5px;
  font-size: 18px;
  border-radius: 6px;
}
</style>