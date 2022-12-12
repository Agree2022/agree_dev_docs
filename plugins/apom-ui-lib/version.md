### 升级说明
### 1.2.7
ex-input增加了value格式化的触发场景——原来只能在鼠标点击过后，触发了blur才可以格式化。改造为mounted和input后也可以格式
### 1.2.6
重新优化draggable指令
### 1.2.5
修复因为rowkey的问题导致无法被鼠标选中的bug
### 1.2.4
修复浏览器窗口改变table高度动态使用的bug
### 1.2.3
完善
### 1.2.2
修复金额、比率、数字的正负格式和比率的格式化处理
### 1.2.1
优化ex-table，增加了支持多级header
### 1.2.0
重新更新版本号
### 1.1.2
增加了ex-input-list扩展组件，用于input内容为动态增减的list形式的form item。使用el-tag进行处理
### 1.1.0
更新次级版本号
### 1.0.37
增加了v-auth指令，可以根据拥有拥有的权限信息进行页面组件的控制
使用说明
```
<el-button type="warning" icon="el-icon-circle-plus-outline" @click="addClick" v-auth:any.none="'/user/add'">添加</el-button>
```

```
// 该自定义指令
// 1、value
// value—可为数组、亦可为字符串
// 2、arg为any/both
// any——满足任意一个value中选项，both——满足所有value中选项
// 3、modifiers为none、disabled、default，优先级从左至右
// none-隐藏   disabled-禁用   default-同disabled，但是鼠标hover事件未disabeld

// 示例
v-auth:both.disabled="['a', 'b']"
v-auth:both="'b'"
v-auth:any.none="['a', 'b', 'c']"
```

### 1.0.36
增加了ExportExcel组件和ExportExcelWrapper组件，区别是Wrapper是包含一个dialog，包括导出按钮等，ExportExcel为核心内容
使用说明
```
<export-excel-wrapper
  v-if="exportExcelVisible"
  ref="exportExcelRef"
  :visible.sync="exportExcelVisible"
  :data="dataSource"
  :selectedData="selectedData"
  :columns="typeColumns"
  :filename="fileName"
  :currentPage="currentPage"
></export-excel-wrapper>

// 注意其中dataSource和currentPage是从ex-table组件中通过事件暴露出来的，参考如下内容
<ex-table-pagination
  ref="FreeFormQueryTable"
  tableRef="FreeFormQueryTable_extend"
  :columns="typeColumns"
  @selectDataChange="selectDataChange"
  @providers:page="pageProvider"
  @providers:data="dataProvider"
  @size-change="sizeChangeEvent"
  :queryMethod="extendQueryMehthod"
  :parentRefs="$refs"
  :minusRef="['conditionForm']"
  :indexFixed="false"
></ex-table-pagination>

  //获取总条数和当前页
  pageProvider(pagination) {
    this.currentPage = pagination.currentPage
  },
  dataProvider(data = []) {
    this.dataSource = data
  },

```
### 1.0.35
增加了浏览器窗口缩放事件监听，可重新渲染ex-table的大小

---



# 组件API
## ex-table
### Attributes

### methods

### events

### example