<template>
  <header class="header">
    Header
    <button @click="increment">+</button>
    <div>{{ count }}</div>
  </header>
  <div @click="console.log('divClick')" >DIV
  <button @click.stop="console.log('btnClick')" >BUTTON</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
    }
  }
});
</script>

<style lang="scss" scoped>
.header {
  height: 150px;
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #ffe4c4;
  color: black;
  font-size: 32px;
}
</style>
