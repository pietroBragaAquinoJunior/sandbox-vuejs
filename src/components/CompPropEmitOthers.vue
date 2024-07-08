<script setup lang="ts">
import { ref, reactive, defineProps, defineEmits, computed } from 'vue'

const minhaRef = ref('Minha ref!')

const meuReactive = reactive({
  message: 'Meu Reactive!'
})

const minhaProp = defineProps({
  message: {
    type: String,
    default: ''
  }
})

const minhaComputed = computed(() => {
  return minhaRef.value + meuReactive.message
})

const meusEmits = defineEmits(['alerta'])
</script>

<template>
  <div>
    <p>{{ minhaRef }}</p>
    <p>{{ meuReactive.message }}</p>
    <p>{{ minhaProp.message }}</p>
    <p>Minha computed: {{ minhaComputed }}</p>
    <button @click="$emit('alerta')">Emitir emit</button>
  </div>
</template>
