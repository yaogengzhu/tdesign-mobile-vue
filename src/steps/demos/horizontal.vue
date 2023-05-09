<template>
  <div>
    <div class="summary">水平带序号步骤条</div>
    <div class="steps-demo-block">
      <t-steps :current="options.first" @change="onFirstChange">
        <t-step-item v-for="(_, index) in list" :key="index" :title="getTitle('first', index)" content="辅助信息" />
      </t-steps>
    </div>
    <div class="summary">水平带图标步骤条</div>
    <div class="steps-demo-block">
      <t-steps :current="options.secode" @change="onSecondChange">
        <t-step-item v-for="(_, index) in list" :key="index" :title="getTitle('second', index)" content="辅助信息">
          <template #icon>
            <CartIcon size="20px" />
          </template>
        </t-step-item>
      </t-steps>
    </div>
    <div class="summary">水平简略步骤条</div>
    <div class="steps-demo-block" @change="onThridChange">
      <t-steps :current="options.third" theme="dot">
        <t-step-item v-for="(_, index) in list" :key="index" :title="getTitle('third', index)" content="辅助信息" />
      </t-steps>
    </div>
  </div>
</template>
<script lang="ts" setup>
import { computed, reactive, ref } from 'vue';
import { CartIcon } from 'tdesign-icons-vue-next';

const options = reactive({
  first: 1,
  second: 1,
  third: 1,
});
const list = ref([1, 2, 3, 4]);
const onFirstChange = (current: number) => {
  options.first = current;
};
const onSecondChange = (current: number) => {
  options.second = current;
};
const onThridChange = (current: number) => {
  options.third = current;
};

const getTitle = (type: 'first' | 'second' | 'third', index: number) => {
  if (index === options[type]) {
    return '当前步骤';
  }
  if (index < options[type]) {
    return '已完成';
  }
  if (index > options[type]) {
    return '未完成';
  }
};
</script>
