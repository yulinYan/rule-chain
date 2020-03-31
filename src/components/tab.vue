<template>
  <div>
    <el-button type="text" @click="table = true">打开嵌套表格的 Drawer</el-button>
<!--    <el-button type="text" @click="dialog = true">打开嵌套 Form 的 Drawer</el-button>-->
    <el-drawer
      title="我嵌套了tab页!"
      :visible.sync="tab"
      direction="rtl"
      size="50%">
      <el-tabs  v-model="activeName" @tab-click="handleClick" v-if="data">
        <el-tab-pane label="详情" name="first">
          <input type="text" v-if="data.name=='checkExistenceFields'" v-model="data.text" />
          <input type="text" v-if="data.name=='inputControl'" v-model="data.text" >
          <input type="text" v-if="data.name=='customerAttributes'" v-model="data.text" />
          <input type="text" v-if="data.name=='ruleChainControl'" v-model="data.text" >
          <input type="text" v-if="data.name=='line'" v-model="data.text" />
        </el-tab-pane>
        <el-tab-pane label="事件" name="second">事件</el-tab-pane>
        <el-tab-pane label="帮助" name="third">帮助</el-tab-pane>
      </el-tabs>
    </el-drawer>
  </div>
</template>

<script>
    export default {
        name: "tab",
      data(){
          return {
            // table: true,
            // dialog: false,
            // loading: false,
            activeName: 'first',//默认刚开始是第几个tab页
            formLabelWidth: '80px',
            timer: null,
        }
      },
      props:["data","tab"],
      methods:{
        handleClick(tab, event) {
          // console.log(tab, event);
          // console.log("1212")
        },

      }
    }
</script>

<style scoped>
input{
  width: 90%;
  line-height: 2;
  border: none;
  border-bottom: 1.5px solid #d9d9d9;
  outline: none;
  color: darkturquoise;
}
</style>
