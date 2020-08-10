---
title: 边配置项
order: 5
---
## 通用属性
### id
| 名称         | 是否必须 | 类型   | 备注                         |
| ------------ | -------- | ------ | ---------------------------- |
| id           | false    | String | 边唯一 ID，**必须**是唯一的 string                       |

### source
| 名称         | 是否必须 | 类型   | 备注                         |
| ------------ | -------- | ------ | ---------------------------- |
| source       | true     | String | Number                       | 起始点 id |

### target
| 名称         | 是否必须 | 类型   | 备注                         |
| ------------ | -------- | ------ | ---------------------------- |
| target       | true     | String | 结束点 id                    |

### type
| 名称         | 是否必须 | 类型   | 备注                         |
| ------------ | -------- | ------ | ---------------------------- |
| type        | false    | String | 指定边的类型，可以是内置边的类型名称，也可以是自定义边的名称。默认为 `'line'`      |

### sourceAnchor
| 名称         | 是否必须 | 类型   | 备注                         |
| ------------ | -------- | ------ | ---------------------------- |
| sourceAnchor | false    | Number | 边的起始节点上的锚点的索引值 |

### targetAnchor
| 名称         | 是否必须 | 类型   | 备注                         |
| ------------ | -------- | ------ | ---------------------------- |
| targetAnchor | false    | Number | 边的终止节点上的锚点的索引值 |

### style

Object 类型。通过 `style` 配置来修改边的颜色、线宽等属性。下表是 `style` 对象中常用的配置项：

| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| stroke | false | String | 边的颜色 |
| lineWidth | false | Number | 边宽度 |
| lineAppendWidth | false | Number | 边响应鼠标事件时的检测宽度，当 `lineWidth` 太小而不易选中时，可以通过该参数提升击中范围 |
| endArrow | false | Boolean / Object | 为 `true` 时在边的结束端绘制默认箭头，为 `false` 时不绘制结束端箭头；也可以使用[内置箭头配置]()，例如：<br />endArrow: {<br /> path: G6.arrow.vee(10, 20, 10), // 内置箭头，参数为箭头宽度、长度、偏移量 d（默认为 0）<br /> d: 10 // 偏移量<br />} ；或通过 path 自定义的箭头，例如：<br />endArrow: {<br /> path: 'M 0,0 L 20,10 L 20,-10 Z', // 自定义箭头路径<br /> d: -2 // 偏移量<br />} |
| startArrow | false | Boolean / Object | 为 `true` 时在边的开始端绘制默认箭头，为 `false` 时不绘制结束端箭头；也可以使用[内置箭头配置]()，例如：<br />startArrow: {<br /> path: G6.arrow.vee(10, 20, 10), // 内置箭头，参数为箭头宽度、长度、偏移量 d（默认为 0）<br /> d: 10 // 偏移量<br />} ；或通过 path 自定义的箭头，例如：<br />startArrow: {<br /> path: 'M 0,0 L 20,10 L 20,-10 Z', // 自定义箭头路径<br /> d: -2 // 偏移量<br />} |
| strokeOpacity | false | Number | 边透明度 |
| shadowColor | false | String | 阴影颜色 |
| shadowBlur | false | Number | 阴影模糊程度 |
| shadowOffsetX | false | Number | 阴影 x 方向偏移量 |
| shadowOffsetY | false | Number | 阴影 y 方向偏移量 |
| lineDash | false | Array | 设置线的虚线样式，可以指定一个数组。一组描述交替绘制线段和间距（坐标空间单位）长度的数字。 如果数组元素的数量是奇数， 数组的元素会被复制并重复。例如， [5, 15, 25] 会变成 [5, 15, 25, 5, 15, 25]。 |
| cursor  | false    | String | 鼠标在该边上时的鼠标样式，[CSS 的 cursor](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor) 选项都支持  |

### label

| 名称         | 是否必须 | 类型   | 备注                         |
| ------------ | -------- | ------ | ---------------------------- |
| label        | false    | String | 文本文字，如果没有则不会显示 |

### labelCfg

`label` String 类型。标签文本的文字内容。<br />`labelCfg` Object 类型。配置标签文本。下面是 `labelCfg` 对象中的常用配置项：

| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| refX | false | Number | 标签在 x 方向的偏移量 |
| refY | false | Number | 标签在 y 方向的偏移量 |
| position | false | String | 文本相对于边的位置，目前支持的位置有：`'start'`，`'middle'`，`'end'`。默认为`'middle'`。 |
| autoRotate | false | Boolean | 标签文字是否跟随边旋转，默认 `false` |
| style | false | Object | 标签的样式属性 |

上表中的标签的样式属性 `style` 的常用配置项如下：

| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| fill | false | String | 文本颜色 |
| stroke | false | String | 文本描边颜色 |
| lineWidth | false | Number | 文本描边粗细 |
| opacity | false | Number | 文本透明度 |
| fontFamily | false | Number | 文本字体 |
| fontSize | false | Number | 文本字体大小 |
| ... 节点标签与边标签样式属性相同，统一整理在 [Text 图形 API](/zh/docs/api/nodeEdge/shapeProperties/#文本-text) |  |  |  |