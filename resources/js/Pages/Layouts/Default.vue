<template>
  <n-layout has-sider>
    <n-layout-sider
      class="h-screen md:flex hidden"
      bordered
      collapse-mode="width"
      :collapsed-width="64"
      :width="260"
      show-trigger="arrow-circle"
      :native-scrollbar="false"
    >
    <Link href="/login">Login</Link>
      <n-menu
        :collapsed-width="64"
        :collapsed-icon-size="22"
        :options="menuOptions"
      />
    </n-layout-sider>
    <n-layout>
      <n-layout-header class="flex h-10 bg-slate-300">
        <div>Avatar</div>
        <div>search</div>
      </n-layout-header>
      <n-layout-content>Content</n-layout-content>
      <n-layout-footer>Footer</n-layout-footer>
    </n-layout>
  </n-layout>
</template>

<script setup>
import { InertiaProgress } from '@inertiajs/progress'
import { h, defineComponent } from "vue";
import { NIcon } from "naive-ui";
import {
  BookOutline as BookIcon,
  PersonOutline as PersonIcon,
  WineOutline as WineIcon,
} from "@vicons/ionicons5";

import NProgress from 'nprogress'
import { Inertia } from '@inertiajs/inertia'
import { Link } from '@inertiajs/inertia-vue3'
function renderIcon(icon) {
  return () => h(NIcon, null, { default: () => h(icon) });
}

Inertia.on('start', () => NProgress.start())
Inertia.on('progress', (event) => {
  if (NProgress.isStarted() && event.detail.progress.percentage) {
    NProgress.set((event.detail.progress.percentage / 100) * 0.9)
  }
})
Inertia.on('finish', () => NProgress.done())

const menuOptions = [
  {
    label: "Hear the Wind Sing",
    key: "hear-the-wind-sing",
    icon: () => h(PersonIcon),
  },
];
</script>


<style>
    .n-layout-sider .n-layout-toggle-button {
        top: 20px;
    }
</style>