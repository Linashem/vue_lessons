<script setup lang="ts">
import PageHeader from '@/components/PageHeader.vue';
import PageContent from '@/components/PageContent.vue';
import PageFooter from './components/PageFooter.vue';
import { ref } from 'vue';
interface IUser {
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
</script>

<template>
  <div class="wrapper">
    <PageHeader nameComponent="Header props" />
    <PageContent>
      <p>{{ user.name + ' - users name' }}</p>
      <p @click="ageIncrem">{{ user.age + ' -users age' }}</p>

      <template #bottomSlot>
        <p>Bottom Slot</p>
      </template>
    </PageContent>
    <PageFooter />
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
