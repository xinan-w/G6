---
title: graph.node(nodeFn)
order: 10
---

Set the style and other configurations for each node.

<span style="background-color: rgb(251, 233, 231); color: rgb(139, 53, 56)"><strong>⚠️Attention:</strong></span> this funcion must **be called before graph.render()**. It does not take effect otherwise.

**Parameters**

| Name   | Type     | Required | Description                              |
| ------ | -------- | -------- | ---------------------------------------- |
| nodeFn | Function | true     | Return the configurations for each node. |

**Usage**

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
