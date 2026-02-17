<script setup lang="ts">
import { ref, watch } from 'vue'

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
  
 
</template>

<style scoped>
.invisibleBody {
  width: none;
}
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
