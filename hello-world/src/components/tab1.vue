<template>
  <div id="app">
    页面1
    <div class="header">
      <div class="dropdown">
        <el-dropdown @command="handleCommand">
          <span class="el-dropdown-link">
            下拉菜单
            <i class="el-icon-arrow-down el-icon--right"></i>
          </span>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item command="下拉1">下拉1</el-dropdown-item>
            <el-dropdown-item command="下拉2">下拉2</el-dropdown-item>
            <el-dropdown-item command="下拉3">下拉3</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </div>
    </div>
    <el-tabs tab-position="left" style="height: 200px;"
     @tab-click="setTab"
     type="border-card" v-model="value">
      <el-tab-pane :label="label+'菜单1'" name="菜单1">
        <div class="inputs">
          <el-input v-model="input" size="small" placeholder="请输入内容"></el-input>
        </div>
        <el-button @click="changeTab" size="small">搜索</el-button>

        <div style="padding:10px 0">
          我是{{label}} 下的菜单1
          我的数据是{{input}}
        </div>
      </el-tab-pane>
      <el-tab-pane :label="label+'菜单2'" name="菜单2">
        <div class="inputs">
          <el-input v-model="input" size="small" placeholder="请输入内容"></el-input>
        </div>
        <el-button @click="changeTab" size="small">搜索</el-button>
        <div style="padding:10px 0">
          我是{{label}} 下的菜单2
          我的数据是{{input}}
        </div>
      </el-tab-pane>
      <el-tab-pane :label="label+'菜单3'" name="菜单3">
        <div class="inputs">
          <el-input v-model="input" size="small" placeholder="请输入内容"></el-input>
        </div>
        <el-button @click="changeTab" size="small">搜索</el-button>
        <div style="padding:10px 0">
          我是{{label}} 下的菜单3
          我的数据是{{input}}
        </div>
      </el-tab-pane>
      <el-tab-pane :label="label+'菜单4'" name="菜单4">
        <div class="inputs">
          <el-input v-model="input" size="small" placeholder="请输入内容"></el-input>
        </div>
        <el-button @click="changeTab" size="small">搜索</el-button>
        <div style="padding:10px 0">
          我是{{label}} 下的菜单4
          我的数据是{{input}}
        </div>
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
export default {
  data() {
    return {
      label: localStorage.label || "下拉1",
      input: "",
      value: localStorage.value || '菜单1',
    };
  },
  methods: {
    handleCommand(command) {
      this.label = command;
      localStorage.label = this.label
    },
    setTab(){
      localStorage.value = this.value
    },
    changeTab(){
      this.$emit("changeTab",this.input)
    }
  },
  components: {}
};
</script>

<style>
.header {
  display: flow-root;
  padding: 10px;
}
.dropdown {
  float: right;
  padding: 8px;
}
.inputs {
  display: inline-block;
  width: 20%;
  margin-right: 20px;
}
</style>
