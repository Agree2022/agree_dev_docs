### Vue2.x插件使用说明
#### 组件
+ ex-aside
+ ex-describe
+ ex-empty
+ ex-input
+ ex-markdown
+ ex-result
+ ex-right-menu
+ ex-select
  1）增加了clearText属性，clearable为true时，执行clear后，属性会被重置为""。增加属性后，重置为clearText，默认定为undefined（原因：select一般对应后台的enum类型，上送""会导致解析异常）
  2）增加了readOnly属性，原生组件仅有disabled，样式等和input的readonly不匹配
+ ex-submenu
+ ex-table
+ ex-steps和ex-step
  从iview抄袭过来，原因是element ui的步骤条太丑。原来项目计划重构，切换组件为iview库。但是后续计划被打乱，仅完成10%。且发现很多开发同事，使用和理解新的ui库的能力有待提高，element的生态更好点，因此取消了后续迁移。由于iveiw组件动画和ui较佳，就保留了部分组件在项目里面。造成当前问题：项目中既引入element（全量引入），又引入iview（部分引入）。因此优化版本中移除iview库，但是鉴于iview优秀的ui，部分组件copy过来使用。


其中result和describe组件开发的时候，element ui无相关组件，后续新增的。

### 安装
+ #### npm安装
> 内部插件，未放入npm中央仓库，需要连接到npm私服。使用npm registry地址


+ #### 内网
  + ##### 有私服
    > 可申请插件源码后，发布到私服服务器。然后参考上一步骤**npm安装**
  + ##### 
 


复制node_modules

### 引入方法
+ #### 基础内容引入 
直接在项目main.js中引入组件、指令、filter和公共方法
```
import '@v2-plugins/apom-ui-lib/styles/index.css'
import sdk from '@v2-plugins/apom-ui-lib'
sdk.init(Vue)
```
+ #### 工具方法引入
+ #### 事件调用引入
在需要使用的js中引入
```
// 调用eventBus
import { eventBus } from '@v2-plugins/apom-ui-lib'
eventBus.$on('event-name', params => {

})

eventBus.$emit('event-name', params)
```


// 调用util方法
import { pluginUtils } from '@v2-plugins/apom-ui-lib'

pluginUtils.windowresize.holder.resize()

Object {
base64: {
stringToBase64: stringToBase64(str),
base64ToString: base64ToString(base64Str)
}, ​
commmon: {
generateUUID: generateUUID()
},
crypto: {
rsaEncryptStr: rsaEncryptStr(data),
rsaEncryptObject: rsaEncryptObject(object)
},
windowresize: {
holder: {…}
}
}

