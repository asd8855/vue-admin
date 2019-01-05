<template>
  <el-container style="height:100vh">
    <el-header style="text-align: right; font-size: 12px">
      <el-dropdown>
        <i
          class="el-icon-setting"
          style="margin-right: 15px"
        ></i>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>查看</el-dropdown-item>
          <el-dropdown-item>新增</el-dropdown-item>
          <el-dropdown-item>删除</el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown
      <span>王小虎</span>
    </el-header>
    <el-container>
      <el-aside width="200px">
        <el-menu
          :default-openeds="['1', '3']"
          @select="selectMenu"
        >
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-message"></i>
              导航一
            </template>
            <el-menu-item-group>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group>
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="2">
           <template slot="title">
              <i class="el-icon-setting"></i>导航二
            </template>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title">
              <i class="el-icon-setting"></i>导航三
            </template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="3-1">选项1</el-menu-item>
              <el-menu-item index="3-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="3-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="3-4">
              <template slot="title">选项4</template>
              <el-menu-item index="3-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-menu>
        
      </el-aside>
      <el-main>
        <router-view />
      </el-main>
    </el-container>
  </el-container>
</template>

<script>
export default {
  data() {
    const item = {
      date: "2016-05-02",
      name: "王小虎",
      address: "上海市普陀区金沙江路 1518 弄"
    };
    return {
      tableData: Array(20).fill(item)
    };
  },

  methods: {
    selectMenu(index, indexPath) {
      if (index == '1-1') {
        this.$router.push('/');
      } else {
        this.$router.push('/about');
      }
    }
  }
};
</script>

<style>
.el-header {
  background-color: #b3c0d1;
  color: #333;
  text-align: center;
  line-height: 60px;
  position: fixed;
  top: 0;
  right: 0;
  left: 0;
  z-index: 100;
}

.el-aside {
  background-color: #d3dce6;
  color: #333;
  text-align: center;
  position: fixed;
  top: 60px;
  bottom: 60px;
  left: 0;
  height: 100%;
  padding-bottom: 60px;
}

.el-main {
  margin-left: 200px;
  margin-top: 60px;
  background-color: #e9eef3;
}
</style>
