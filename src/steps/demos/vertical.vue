<template>
  <div>
    <div class="summary">水平简略步骤条</div>
    <t-steps :current="first" theme="dot">
      <t-step-item v-for="(_, index) in list" :key="index" :title="getTitle(index)" content="辅助信息" />
    </t-steps>
  </div>
</template>
<script lang="ts" setup>
import { computed, ref } from 'vue';

const first = ref(1);
const list = ref([1, 2, 3, 4]);

const getTitle = (index: number) => {
  if (index === first.value) {
    return '当前步骤';
  }
  if (index < first.value) {
    return '已完成';
  }
  if (index > first.value) {
    return '未完成';
  }
};
</script>
