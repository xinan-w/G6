---
title: new Graph() 创建 Graph 实例
order: 0
---

<!-- ## new Graph() 创建 Graph 实例 -->

Graph 是 G6 图表的载体，所有的 G6 节点实例操作以及事件，行为监听都在 Graph 实例上进行。Graph 的初始化通过 new 进行实例化，实例化时需要传入需要的参数。

```ts
// highlight-start
new Graph(params: GraphOptions) => Graph
// highlight-end
```

**用法**

```javascript
const graph = new G6.Graph({
  container: '',
  width: 500,
  height: 500,
  modes: {
    default: ['drag-canvas'],
  },
  layout: {
    type: 'radial',
    unitRadius: 50,
    center: [500, 300],
  },
});
```

**参数**

### container

<description> _string | HTMLElement_ **required** </description>

图的  DOM 容器，可以传入该 DOM 的 id 或者直接传入容器的 HTML 节点对象。

### width

<description> _Number_ **required** </description>

指定画布宽度，单位为 'px'。

### height

<description> _Number_ **required** </description>

指定画布高度，单位为 'px'。

### fitView

<description> _Boolean_ **optional** _default:_ `false`</description>

是否开启画布自适应。开启后图自动适配画布大小。

### fitViewPadding

<description> _Array | Number_ **optional** _default:_ `0`</description>

`fitView` 为 `true` 时生效。图适应画布时，指定四周的留白。<br />- 可以是一个值, 例如：`fitViewPadding: 20`<br />- 也可以是一个数组，例如：`fitViewPadding: [ 20, 40, 50, 20 ]`<br />当指定一个值时，四边的边距都相等，当指定数组时，数组内数值依次对应 上，右，下，左四边的边距。

## fitCenter

<description> _Boolean_ **optional** _default:_ `false`</description>

*v3.5.1 后支持。*开启后，图将会被平移，图的中心将对齐到画布中心，但不缩放。优先级低于 fitView。

### linkCenter

<description> _Boolean_ **optional** _default:_ `false`</description>

指定边是否连入节点的中心。

### groupByTypes

<description> _Boolean_ **optional** _default:_ `true`</description>

各种元素是否在一个分组内，决定节点和边的层级问题，默认情况下所有的节点在一个分组中，所有的边在一个分组中，当这个参数为 false 时，节点和边的层级根据生成的顺序确定。当使用 Combo 时，**必须**将其设置为 `false` 。

### autoPaint

<description> _Boolean_ **optional** _default:_ `true`</description>

当图中元素更新，或视口变换时，是否自动重绘。建议在批量操作节点时关闭，以提高性能，完成批量操作后再打开，参见后面的 setAutoPaint() 方法。

### modes

<description> _Object_ **optional** _default:_ `{}`</description>

设置画布的交互模式。详情可见  [交互模式 Mode](/zh/docs/manual/middle/states/mode)  文档。

#### modes.default

<description> _Object_ **optional** _default:_ `[]`</description>

画布默认的模式。详情可参见 [内置的 Behavior](/zh/docs/manual/middle/states/defaultBehavior) 文档。

### nodeStateStyles

<description> _Object_ **optional** _default:_ `{}`</description>

各个状态下节点的样式，例如 `hover`、`selected`，3.1 版本新增。

<span style="background-color: rgb(251, 233, 231); color: rgb(139, 53, 56)"><strong>⚠️ 注意:</strong></span> G6 3.1 版本中实例化 Graph 时，新增了 `nodeStateStyles` 及  `edgeStateStyles` 两个配置项，删除了 `nodeStyle` 和 `edgeStyle` ，使用 3.1 以下版本的同学，只需要将  `nodeStyle` 改成 `nodeStateStyles` ，将  `edgeStyle` 改成  `edgeStateStyles` ，配置内容保持不变。

### edgeStateStyles

<description> _Object_ **optional** _default:_ `{}`</description>

各个状态下边的样式，例如 `hover`、`selected`，3.1 版本新增。

### comboStateStyles

<description> _Object_ **optional** _default:_ `{}`</description>

各个状态下 Combo 的样式，例如 `hover`、`selected`，3.5 版本新增。

### defaultNode

<description> _Object_ **optional** _default:_ `{}`</description>

默认状态下节点的配置，比如 `type`, `size`, `color`。会被写入的 data 覆盖。 见 [节点的通用属性](/zh/docs/manual/middle/elements/nodes/defaultNode#节点的通用属性) 。

### defaultEdge

<description> _Object_ **optional** _default:_ `{}`</description>

默认状态下边的配置，比如 `type`, `size`, `color`。会被写入的 data 覆盖。 见 [边的通用属性](/zh/docs/manual/middle/elements/edges/defaultEdge#边的通用属性) 。

### defaultCombo

<description> _Object_ **optional** _default:_ `{}`</description>

默认状态下 Combo 的配置，比如 `type`, `color`。会被写入的 data 覆盖。3.5 版本新增。 见 [Combo 的通用属性](/zh/docs/manual/middle/elements/combos/defaultCombo#combo-的通用属性) 。

### plugins

<description> _Array _ **optional** _default:_ `[]`</description>

向 graph 注册插件。插件机制请见：[插件](/zh/docs/manual/tutorial/plugins#插件) 。

### animate

<description> _Boolean _ **optional** _default:_ `false`</description>

是否启用全局动画。

### animateCfg

<description> _Object_ **optional** _default:_ `{}`</description>

动画配置项，仅在 `animate` 为 `true` 时有效。关于 `animateCfg` 的更多配置项参见[基础动画教程](/zh/docs/manual/advanced/animation#animatecfg)。

#### animateCfg.onFrame

<description> _Function_ **optional** _default:_ `null`</description>

回调函数，用于自定义节点运动路径，为空时线性运动。

#### animateCfg.duration

<description> _Number_ **optional** _default:_ `500`</description>

动画时长，单位为毫秒。

#### animateCfg.easing

<description> _string_ **optional** _default:_ `easeLinear`</description>

动画动效，可参见 d3 ease。

### minZoom

<description> _Number_ **optional** _default:_ `0.2`</description>

最小缩放比例。

### maxZoom

<description> _Number_ **optional** _default:_ `10`</description>

最大缩放比例。

### layout

<description> _Object_ **optional** _default:_ `{}`</description>

布局配置项，使用 type 字段指定使用的布局方式，type 可取以下值：random, radial, mds, circular, fruchterman, force, dagre，各布局详细的配置请参考  [Layout API 文档](/zh/docs/api/G6/Layout/Layout) 。

### renderer

<description> _'canvas' / 'svg' _ **optional** _default:_ `'canvas'`</description>

渲染方式，该配置项除 V3.3.x 外其他版本均支持。

### enabledStack

<description> _boolean_ **optional** _default:_ `false`</description>

是否启用 stack，即是否开启 redo & undo 功能，该配置项 V3.6 及以上版本支持。

### maxStep

<description> _number_ **optional** _default:_ `10`</description>

redo & undo 最大步数, 只有当 enabledStack 为 true 时才起作用，该配置项 V3.6 及以上版本支持。

</div>
