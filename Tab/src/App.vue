<template>
  <div v-for="(obj, index) in tabs" :key="index">
    <Tab v-bind="obj"
      @onClick="updateText"
    />
  </div>
  <div>
      {{pageText}}
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import Tab, { type TabProps } from './components/Tab.vue'

const pageText = ref('default!!!')

const tabs: TabProps[] = [
  {
    tabNum: 1,
    tabText: 'Texto da tab 1'
  },
  {
    tabNum: 2,
    tabText: 'Texto da tab 2'
  },
  {
    tabNum: 3,
    tabText: 'Texto da tab 3'
  },
  {
    tabNum: 4,
    tabText: 'Texto da tab 4'
  },
]

function updateText(text: string) {
  pageText.value = text
}

</script>

<style>
@import './assets/base.css';
</style>
