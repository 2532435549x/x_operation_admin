<!--
 * @Description: In User Settings Edit
 * @Author: wangyun
 * @Date: 2019-09-18 15:31:22
 * @LastEditors: wangyun
 * @LastEditTime: 2019-09-26 16:42:56
 -->

<template>
  <el-scrollbar wrap-class="scrollbar-wrapper">
    <el-menu
      :show-timeout="200"
      :default-active="$route.path"
      :collapse="isCollapse"
      mode="vertical"
      background-color="#304156"
      text-color="#bfcbd9"
      active-text-color="#409EFF"
    >
      <sidebar-item
        v-for="route in routes"
        :key="route.path"
        :item="route"
        :base-path="route.path"
      />
    </el-menu>
  </el-scrollbar>
</template>

<script>
import { mapGetters } from 'vuex'
import SidebarItem from './SidebarItem'

export default {
  components: { SidebarItem },
  computed: {
    ...mapGetters(['sidebar', 'routes']),
    isCollapse() {
      return !this.sidebar.opened
    }
  }
}
</script>
