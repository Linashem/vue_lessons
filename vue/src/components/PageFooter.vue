<template>
  <footer class="footer">
    Footer
    <div>{{ props.user.name }}</div>
  </footer>
</template>

<script setup lang="ts">
import { IUser } from '@/App.vue';
interface IUserProps {
  user: IUser;
}

const props = defineProps<IUserProps>();
console.log(props.user);

</script>

<style lang="scss" scoped>
.footer {
  width: 100%;
  height: 150px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: #8fbc8f;
  color: black;
  font-size: 32px;
}
</style>
