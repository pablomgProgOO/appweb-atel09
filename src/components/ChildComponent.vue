<script setup lang="ts">
import { watch } from 'vue'

const props = defineProps<{ textValue: string; selectedValue: string }>()
const emit = defineEmits<{
  (e: 'update:textValue', v: string): void
  (e: 'update:selectedValue', v: string): void
}>()
watch(() => props.textValue, (newValue) => {
    console.log('Nouvelle valeur du champ texte :', newValue)
})

watch(() => props.selectedValue, (newValue) => {
    console.log('Nouvelle valeur sélectionnée :', newValue)
})
</script>
<template>
 <div>
    <input 
      type="text" 
      :value="textValue" 
      @input="emit('update:textValue', ($event.target as HTMLInputElement).value)"
    />

    <select :value="selectedValue" @change="emit('update:selectedValue', ($event.target as HTMLSelectElement).value)">
      <option value="option1">Option 1</option>
      <option value="option2">Option 2</option>
      <option value="option3">Option 3</option>
    </select>
  </div>
</template>
<style scoped>

</style>