---
title: 节点属性
order: 5
---

## extends Items

## 内置节点的通用属性

### id
| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| id | true | String | 节点唯一 ID，**必须**是唯一的 string |

### x
| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| x | false | Number | x 坐标 |

### y
| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| y | false | Number | y 坐标 |

### type
| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| type | false | String | 指定节点类型，内置节点类型名称或自定义节点的名称。默认为 `'circle'` |

### size
| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| size | false | Number / Array | 节点的大小 |

### anchorPoints
| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| anchorPoints | false | Array | 指定边连入节点的连接点的位置（相对于该节点而言），可以为空。例如: `[0, 0]`，代表节点左上角的锚点，`[1, 1]`,代表节点右下角的锚点 |

### style

Object 类型。通过 `style` 配置来修改节点的填充色、边框颜色、阴影等属性。下表是 `style` 对象中常用的配置项：

| 名称          | 是否必须 | 类型   | 备注                          |
| ------------- | -------- | ------ | ----------------------------- |
| fill          | false    | String | 节点填充色                    |
| stroke        | false    | String | 节点的描边颜色                |
| lineWidth     | false    | Number | 描边宽度                      |
| lineDash     | false    | Number[] | 描边虚线，数组代表实、虚长度    |
| shadowColor   | false    | String | 阴影颜色                      |
| shadowBlur    | false    | Number | 阴影范围                      |
| shadowOffsetX | false    | Number | 阴影 x 方向偏移量             |
| shadowOffsetY | false    | Number | 阴影 y 方向偏移量             |
| opacity       | false    | Number | 设置绘图的当前 alpha 或透明值 |
| fillOpacity   | false    | Number | 设置填充的 alpha 或透明值     |
| cursor        | false    | String | 鼠标在该节点上时的鼠标样式，[CSS 的 cursor](https://developer.mozilla.org/en-US/docs/Web/CSS/cursor) 选项都支持  |


### label
| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| label | false | String | 文本文字 |

### labelCfg

| 名称 | 是否必须 | 类型 | 备注 |
| --- | --- | --- | --- |
| position | false | String | 文本相对于节点的位置，目前支持的位置有：`'center'`，`'top'`，`'left'`，`'right'`，`'bottom'`。默认为 `'center'`。modelRect 节点不支持该属性 |
| offset | false | Number | 文本的偏移，`position` 为 `'bottom'` 时，文本的上方偏移量；`position` 为 `'left'` 时，文本的右方偏移量；以此类推在其他 `position` 时的情况。modelRect 节点的 `offset` 为左边距 |
| style | false | Object | 标签的样式属性。 |

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

## 内置节点的特有属性
各个内置节点的特有属性见 [内置节点](/zh/docs/manual/middle/elements/nodes/defaultNode) 目录下各文档。