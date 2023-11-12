<script setup lang="ts">
import PageHeader from '@/components/PageHeader.vue';
import PageContent from '@/components/PageContent.vue';
import PageFooter from './components/PageFooter.vue';
</script>

<template>
  <div class="wrapper">
    <PageHeader />
    <PageContent />
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
