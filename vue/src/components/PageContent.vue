<template>
  <div class="content">
    Content 
    <slot></slot>
    <slot name="bottomSlot"></slot>

  </div>
</template>

<script setup lang="ts"></script>

<style lang="scss" scoped>
.content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  background-color: #800000;
  color: white;
  font-size: 32px;
}
</style>
