<template>
  <div class="component">
    <!-- <h1>fuck the king</h1> -->
    <!-- <bankChooser></bankChooser> -->
    <!-- <kdialog :isShow="showDialog"></kdialog> -->
    <!-- <counter :max="100" :min="20"></counter> -->
    <!-- <Vprogress></Vprogress> -->
    <!-- <HelloWorld></HelloWorld> -->
    <!-- <div class="btn" @click="add">增加</div> -->
    <!-- <input type="button" value="Mike" v-model="checkedNames" @click="add"> -->
    <!-- <elButton @click="openDialog" type="success" round>计数</elButton> -->
    <!-- <el-button type="primary" @click="openDialog">主要按钮</el-button> -->
    <!-- <el-date-picker v-model="value6" size="small" type="daterange" range-separator="至" start-placeholder="开始日期" end-placeholder="结束日期"> -->
    <!-- </el-date-picker> -->
    <!-- <p>按钮点击了{{add}}次</p> -->
    <!-- <chooser :selections="buyTypes"></chooser> -->
    <!-- <datepicker></datepicker> -->
    <!-- <Vtable :activeLine="1" :activeRow="3"></Vtable> -->
    <!-- <div :style="{width:'60%'}"> -->
    <!-- <el-table :data="tableData" border style="width: 100%">
        <el-table-column fixed prop="date" label="日期" width="150">
        </el-table-column>
        <el-table-column prop="name" label="姓名" width="120">
        </el-table-column>
        <el-table-column prop="province" label="省份" width="120">
        </el-table-column>
        <el-table-column prop="city" label="市区" width="120">
        </el-table-column>
        <el-table-column prop="address" label="地址" width="300">
        </el-table-column>
        <el-table-column prop="zip" label="邮编" width="120">
        </el-table-column>
        <el-table-column fixed="right" label="操作" width="100">
          <template slot-scope="scope">
            <el-button @click="handleClick(scope.row)" type="text" size="small">查看</el-button>
            <el-button type="text" size="small">编辑</el-button>
          </template>
        </el-table-column>
      </el-table>
    </div> -->
    <!-- <Bread :options="breadData"></Bread>
    <logForm></logForm>
    <multiplyChooser :selections="multChoose"></multiplyChooser> -->
    <!-- <regForm></regForm> -->
    <!-- <selection :selections="districts"></selection> -->
    <!-- <add></add> -->
    <!-- <slideShow></slideShow> -->
    <!-- <layout></layout> -->
    <Vtree :model="treeData"></Vtree>
  </div>
</template>

<script>
import bankChooser from "./bankChooser";
// import checkOrder from "./checkOrder";
import chooser from "./chooser";
import counter from "./counter";
import HelloWorld from "./HelloWorld";
import datepicker from "./datepicker";
import kdialog from "./dialog";
import layout from "./layout";
import logForm from "./logForm";
import multiplyChooser from "./multiplyChooser";
import regForm from "./regForm";
import selection from "./selection";
import slideShow from "./slideShow";
import add from "./add";
import Bread from "./bread";
import Vprogress from "./progress";
import Vtable from "./table";
import Vtree from "./tree";

import ElementUI from "element-ui";
import "element-ui/lib/theme-chalk/index.css";
import Vue from "vue";
Vue.use(ElementUI);
export default {
    name: "component",
    components: {
        HelloWorld,
        counter,
        kdialog,
        Bread,
        bankChooser,
        chooser,
        datepicker,
        layout,
        logForm,
        multiplyChooser,
        regForm,
        selection,
        slideShow,
        add,
        Vprogress,
        Vtable,
        Vtree
    },
    data() {
        return {
            treeData: {
                name: "My Tree",
                children: [
                    { name: "hello" },
                    { name: "wat" },
                    {
                        name: "child folder",
                        children: [
                            {
                                name: "child folder",
                                children: [{ name: "hello" }, { name: "wat" }]
                            },
                            { name: "hello" },
                            { name: "wat" },
                            {
                                name: "child folder",
                                children: [{ name: "hello" }, { name: "wat" }]
                            }
                        ]
                    }
                ]
            },
            open: false,
            // vue 遍历data对象上的所有属性,通过object.defineProperty()方法将属性转换为getter/setter,vue内部追踪这些依赖,在修改时触发相应变化,完成模型到视图的双向绑定.依赖项触发时通知watecher重新计算新值,触发render()函数重新渲染
            // Vue组件不能检测到实例化后data属性的添加,删除.若想修改,可调用Vue.set(object,key,value);
            checkedNames: "add",
            msg: "",
            add: 0,
            value6: "",
            showDialog: false,
            // chooseData:[{'label':abc,value:abc}]
            breadData: [
                { label: "客单价", value: 1 },
                { label: "南湖店", value: 2 },
                { label: "斯凯", value: 3 }
            ],
            multChoose: [
                {
                    label: "abc",
                    value: 0
                },
                {
                    label: "123",
                    value: 1
                },
                {
                    label: "fuck the king",
                    value: 2
                }
            ],
            districts: [
                {
                    label: "北京",
                    value: 0
                },
                {
                    label: "上海",
                    value: 1
                },
                {
                    label: "广州",
                    value: 2
                },
                {
                    label: "天津",
                    value: 3
                },
                {
                    label: "武汉",
                    value: 4
                },
                {
                    label: "重庆",
                    value: 5
                }
            ],
            buyTypes: [
                {
                    label: "红色版",
                    value: 0
                },
                {
                    label: "绿色版",
                    value: 1
                },
                {
                    label: "紫色版",
                    value: 2
                }
            ],
            tableData: [
                {
                    date: "2016-05-03",
                    name: "王小虎",
                    province: "上海",
                    city: "普陀区",
                    address: "上海市普陀区金沙江路 1518 弄",
                    zip: 200333
                },
                {
                    date: "2016-05-02",
                    name: "王小虎",
                    province: "上海",
                    city: "普陀区",
                    address: "上海市普陀区金沙江路 1518 弄",
                    zip: 200333
                },
                {
                    date: "2016-05-04",
                    name: "王小虎",
                    province: "上海",
                    city: "普陀区",
                    address: "上海市普陀区金沙江路 1518 弄",
                    zip: 200333
                },
                {
                    date: "2016-05-01",
                    name: "王小虎",
                    province: "上海",
                    city: "普陀区",
                    address: "上海市普陀区金沙江路 1518 弄",
                    zip: 200333
                }
            ]
        };
    },
    methods: {
        openDialog: function(e) {
            console.log(e);
            this.showDialog = true;
        },
        handleClick(e) {
            console.log(e);
        }
    },
    mounted() {
        // this.openDialog();
    }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
    font-weight: normal;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    display: inline-block;
    margin: 0 10px;
}

a {
    color: #42b983;
}
.btn {
    display: inline-block;
    width: 60px;
    height: 30px;
    border-radius: 5px;
    background: cyan;
}
.component {
    /* background: radial-gradient(ellipse 40% 40%, #004c9e, #002259); */
}
</style>
