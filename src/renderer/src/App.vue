<template>
  <el-container class="layout-container">
    <el-aside width="200px">
      <el-scrollbar>
        <el-menu :default-openeds="['1', '3']">
          <el-sub-menu index="1">
            <template #title>
              <el-icon><message /></el-icon>Navigator One
            </template>
            <el-menu-item-group>
              <template #title>Group 1</template>
              <el-menu-item index="1-1">Option 1</el-menu-item>
              <el-menu-item index="1-2">Option 2</el-menu-item>
            </el-menu-item-group>
            <el-sub-menu index="1-4">
              <template #title>Option4</template>
              <el-menu-item index="1-4-1">Option 4-1</el-menu-item>
            </el-sub-menu>
          </el-sub-menu>
        </el-menu>
      </el-scrollbar>
    </el-aside>

    <el-container>
      <el-header style="text-align: right; font-size: 12px">
        <div class="toolbar">
          <el-dropdown>
            <el-icon style="margin-right: 8px; margin-top: 1px">
              <setting />
            </el-icon>
            <template #dropdown>
              <el-dropdown-menu>
                <el-dropdown-item>View</el-dropdown-item>
                <el-dropdown-item>Add</el-dropdown-item>
                <el-dropdown-item>Delete</el-dropdown-item>
              </el-dropdown-menu>
            </template>
          </el-dropdown>
          <span>Tom</span>
        </div>
      </el-header>

      <el-main>
        <div style="flex-direction: row; margin: 10px">
          <el-text class="mx-1">管道外径</el-text>
          <el-input
              v-model="pipe_outer_diameter"
              style="width: 240px; margin-left: 20px"
              placeholder="外径"
          />
        </div>
        <div style="flex-direction: row; margin: 10px">
          <el-text class="mx-1">管道壁厚</el-text>
          <el-input
              v-model="pipe_thickness"
              style="width: 240px; margin-left: 20px"
              placeholder="壁厚"
          />
        </div>
        <div style="flex-direction: row; margin: 10px">
          <el-text class="mx-1">管道屈服极限</el-text>
          <el-input
              v-model="SMYS"
              style="width: 240px; margin-left: 20px"
              placeholder="屈服极限"
          />
        </div>
        <div style="flex-direction: row; margin: 10px">
          <el-text class="mx-1">管道强度极限</el-text>
          <el-input
              v-model="SMTS"
              style="width: 240px; margin-left: 20px"
              placeholder="强度极限"
          />
        </div>
      </el-main>
    </el-container>
  </el-container>
</template>

<script lang="ts" setup>
import { ref } from 'vue'
import { Message, Setting } from '@element-plus/icons-vue'

const pipe_outer_diameter = ref('')
const pipe_thickness = ref('')
const SMYS = ref('')
const SMTS = ref('')

</script>

<style scoped>
.layout-container {
  height: 100vh;
  width: 100vw;
  background-color: aqua;
}
.layout-container .el-header {
  position: relative;
  background-color: var(--el-color-primary-light-7);
  color: var(--el-text-color-primary);
}
.layout-container .el-aside {
  color: var(--el-text-color-primary);
  background: var(--el-color-primary-light-8);
}
.layout-container .el-menu {
  border-right: none;
}
.layout-container .el-main {
  padding: 0;
}
.layout-container .toolbar {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  right: 20px;
}
.el-row {
  margin-bottom: 20px;
}
.el-row:last-child {
  margin-bottom: 0;
}
.el-col {
  border-radius: 4px;
}

.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
</style>
