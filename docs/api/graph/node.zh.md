---
title: graph.node(nodeFn) 设置节点配置
order: 10
---

### node(nodeFn)

设置各个节点样式及其他配置，以及在各个状态下节点的 KeyShape 的样式。

<span style="background-color: rgb(251, 233, 231); color: rgb(139, 53, 56)"><strong>提示:</strong></span> 该方法必须**在 render 之前调用**，否则不起作用。

**参数**

| 名称   | 类型     | 是否必选 | 描述               |
| ------ | -------- | -------- | ------------------ |
| nodeFn | Function | true     | 返回每个节点的配置 |

**用法**

```javascript
graph.node((node) => {
  return {
    id: node.id,
    type: 'rect',
    style: {
      fill: 'blue',
    },
  };
});

graph.data(data);
graph.render();
```
