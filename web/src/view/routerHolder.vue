<!-- 此路由可作为父类路由通用路由页面使用 如需自定义父类路由页面 请参考 @/view/superAdmin/index.vue -->
<template>
  <div>
    <router-view v-if="$route.meta.keepAlive" v-slot="{ Component }">
      <transition mode="out-in" name="el-fade-in-linear">
        <keep-alive>
          <component :is="Component" />
        </keep-alive>
      </transition>
    </router-view>
    <router-view v-if="!$route.meta.keepAlive" v-slot="{ Component }">
      <transition mode="out-in" name="el-fade-in-linear">
        <component :is="Component" />
      </transition>
    </router-view>
  </div>
</template>

<script>
export default {
  name: 'RouterHolder'
}
</script>
