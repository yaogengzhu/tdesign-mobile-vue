<template>
  <div class="step-demo" horizontal="vertical">
    <t-steps v-model="current" :readonly="false">
      <t-step-item key="1" title="步骤描述" content="辅助信息" />
      <t-step-item key="2" title="步骤描述" content="辅助信息" />
    </t-steps>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const current = ref(0);

const stepData = ref([
  {
    title: '步骤描述',
    content: '辅助信息文字最多两行',
  },
  {
    title: '步骤描述',
    content: '辅助信息文字最多两行',
  },
  {
    title: '步骤描述',
    content: '辅助信息文字最多两行',
  },
  {
    title: '步骤描述',
    content: '辅助信息文字最多两行',
  },
]);
</script>
