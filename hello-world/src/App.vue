<template>
  <div id="app">
    <Tab1 v-if="viewTab==='tab1'" @changeTab="changeTab"></Tab1>
    <Tab2 v-else :inputs="input" @changeTab="changeTab"></Tab2>
  </div>
</template>

<script>
import Tab1 from "./components/tab1"
import Tab2 from "./components/tab2"

export default {
  name: "app",
  data() {
    return {
      viewTab:'tab1',
      input:''
    }
  },
  components: {
    Tab1,
    Tab2
  },
  methods: {
    changeTab(e){
      this.input = e
      this.viewTab = this.viewTab === 'tab2' ? 'tab1' : 'tab2'
    }
  },
};
</script>

<style>

</style>
