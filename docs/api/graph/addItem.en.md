---
title: graph.addItem(type, model, stack)
order: 10
---

### addItem(type, model, stack)

Add item(node, edge, or group) to the graph.

<span style="background-color: rgb(251, 233, 231); color: rgb(139, 53, 56)"><strong>⚠️ Attention:</strong></span> G6 will use the `model` object as the model of the newly added item, and the `model` might be modified. If you do not want it to be modified, use the deep cloned `model` instead.

**Parameters**

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| type | string | true | The type of the item. Options: `'node'`, `'edge'`, and `'group'`. |
| model | Object | true | The data model of the item, refer to [Item Model Properties](/en/docs/api/nodeEdge/itemProperties). When `type: 'group'`, refer to [Create Node Group](/en/docs/manual/advanced/create-node-group) |
| stack | boolean | false | Whether to push the operator into the undo & redo stack. If the `enableStack` is `true`, this operation will be automatically pushed into the stack by default. Set `stack` to be `false` if you do not want it. |

**Usage**

```javascript
const model = {
  id: 'node',
  label: 'node',
  address: 'cq',
  x: 200,
  y: 150,
  style: {
    fill: 'blue',
  },
};

graph.addItem('node', model);

// Here is the model example for type = 'group'
const model = {
  groupId: 'xxx000999',
  nodes: ['123', '23'],
  type: 'rect',
  zIndex: 0,
  title: {
    text: 'group name',
  },
};

graph.addItem('group', model);
```

### add(type, model, stack)

The same as addItem(type, model).
