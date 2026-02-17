<script setup lang="ts">
import HelloWorld from './components/HelloWorld.vue'
import { ref, watch } from 'vue'
import ChildComponent from './components/ChildComponent.vue'

const textValue = ref('')
const selectedValue = ref('option1')
watch(textValue, (newValue, oldValue) => {
    console.log(`Le texte est passé de ${oldValue} à ${newValue}`)
})

watch(selectedValue, (newValue, oldValue) => {
    console.log(`L'option sélectionnée est passée de ${oldValue} à ${newValue}`)
})
</script>

<template>
  
  <HelloWorld msg="Vite + Vue" />
  <div class="container">
    <h2>Communication Parent-Enfant avec v-model</h2>
    <p>Texte dans le parent: {{ textValue }}</p>
    <p>Option sélectionnée dans le parent: {{ selectedValue }}</p>
    <ChildComponent v-model:textValue="textValue" v-model:selectedValue="selectedValue" />
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
