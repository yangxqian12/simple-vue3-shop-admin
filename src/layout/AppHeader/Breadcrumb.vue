<template>
  <el-breadcrumb separator="/">
    <!-- <el-breadcrumb-item :to="{ path: '/' }">
      homepage
    </el-breadcrumb-item>
    <el-breadcrumb-item>
      <a href="/">promotion management</a>
    </el-breadcrumb-item>
    <el-breadcrumb-item>promotion list</el-breadcrumb-item> -->
    <el-breadcrumb-item
      v-for="item in routes"
      :key="item.path"
    >
      {{ item.meta.title }}
    </el-breadcrumb-item>
  </el-breadcrumb>
</template>

<script lang="ts" setup>
import { computed } from 'vue'
import { useRouter } from 'vue-router'
const router = useRouter()
console.log(111, router)

const routes = computed(() => {
  return router.currentRoute.value.matched.filter(item => item.meta.title)
})
</script>

<style lang="scss" scoped>

</style>
