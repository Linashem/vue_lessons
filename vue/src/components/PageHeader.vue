<template>
  <header :style="{ backgroundColor: isRed ? 'red' : '#ffe4c4' }" class="header">
    Header
    <button class="btn" @click="increment">+</button>
    <div>{{ count }}</div>
  </header>

  <div @click="console.log('divClick')">
    DIV
    <button @click.stop="console.log('btnClick')">BUTTON</button>
  </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  data() {
    return {
      count: 0,
      isRed: false
    };
  },
  methods: {
    increment() {
      this.count++;
    }
  },
  watch: {
    count(newCount, oldCount) {
      console.log('new ', newCount);
      console.log('old ', oldCount);
      this.isRed=!this.isRed
    },
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
  .btn {
    margin-right: 20px;
    margin-left: 20px;
    padding: 5px;
    border-radius: 5px;
  }
}
</style>
