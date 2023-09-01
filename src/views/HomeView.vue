<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <div class="wrap">
    這是wrap
    <RouterLink to="rateSwitcher">
      <el-button type="primary">台幣兌外幣</el-button>
    </RouterLink>
  </div>
  測試
  <RouterView />
</template>
<style lang="scss" scoped>
.wrap {
  display: flex;
  padding: 16px;
  margin: 16px;
  justify-content: center;
  align-items: center;
}
</style>