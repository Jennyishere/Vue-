### 含义
Vue是一套用于构建用户界面的渐进式框架.

### 核心思想Model-View-ViewModel

### 起步

一、基于webpack安装vue-cli脚手架
1、npm i @vue/cli
2、vue create 创建项目
3、npm run serve运行服务器

二、基本语法
<div id="app">
  {{ message }}
</div>
var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue!'
  }
})
三、组件
（一）全局组件
**语法**
var 组件对象 = Vue.component(“组件名称”，{ 配置 })
组件的配置 ：
    配置模板
	template:
    配置数据
	data() {}  //为了组件的复用，数据配置应是一个函数，由于对象的存储是地址
注意：组件只能在vue根实例前创建使用
（二）单文件组件
**语法**
1、结构
<template id=""> html 代码</template>
2、功能，需要暴露组件
export default {
	不用指定template
	date函数() { }
 }
3、样式
<style lang=''css语言'', scoped只对当前的文件有效> </style>
**使用**
1、在webpack打包的主js文件中引入单文件组件，通过Vue实例进行渲染：
new Vue({
  render: h => h(组件)
}).$mount('#app')
2、在其他组件中使用
（1）注册组件：components属性中添加引入的组件
（2）把组件用标签在结构模板里使用
四、指令
**插值**
