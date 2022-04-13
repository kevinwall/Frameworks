<script setup lang="ts">
    export interface TabProps {
    tabNum: number  // enunciado da questão
    tabText: string  // opções da questão
  }

  // Eventos do componente.
  export interface TabEvents {
    (e: 'onClick', val: string): void // quando o usuário selecionar uma opção, passa seu índice
  }

  // define as propriedades e os eventos
  defineProps<TabProps>()
  defineEmits<TabEvents>()
</script>

<template>
  <button @click="$emit('onClick', tabText)">Tab {{ tabNum }}</button> 
</template>

<style scoped>
  h2 {
    font-weight: normal;
    font-size: 20pt;
    margin-top: 0;
  }

  button {
    margin-right: 10px;
    background-color: #ccc;
    border: 1px solid rgb(118, 118, 118);
    border-radius: 3px;
    padding: 2px 5px;
  }

  .selected {
    font-weight: bold;
    background-color: #aaa;
  }
</style>