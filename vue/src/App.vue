<script setup lang="ts">
import PageHeader from '@/components/PageHeader.vue';
import PageContent from '@/components/PageContent.vue';
import PageFooter from './components/PageFooter.vue';
import { computed, ref, watch } from 'vue';

export interface IUser {
  name: string;
  age: number;
}

//реактивные переменные
const user = ref<IUser>({
  name: 'Lina',
  age: 26
});

//методы
const ageIncrem = () => {
  user.value.age++;
};

// computed
const dobleAge = computed(() => {
  return user.value.age * 2;
});

//watch
watch(
  user,
  (newU, oldU) => {
    console.log(newU, ' newU');
    console.log(oldU, ' oldU');
  },
  { deep: true }
);
</script>

<template>
  <div class="wrapper">
    <PageHeader nameComponent="Header props" />
    <PageContent>
      <p>{{ user.name + ' - users name' }}</p>
      <p @click="ageIncrem">{{ user.age + ' -users age' }}</p>
      <p>{{ dobleAge }}</p>

      <template #bottomSlot>
        <p>Bottom Slot</p>
      </template>
    </PageContent>
    <PageFooter @footer-emet="(value)=>console.log('footerEmet', value)" :user="user" />
  </div>
</template>

<style lang="scss" scoped>
.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100vh;
}
</style>
