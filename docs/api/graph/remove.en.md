---
title: graph.remove*
order: 10
---

### removeItem(item, stack)

Remove the item. When the item is the id of a group, this operation will delete the corresponding group.

**Parameters**

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| item | string / Object | true | The id or the instance of the item. |
| stack | boolean | false | Whether to push the operator into the undo & redo stack. If the `enableStack` is `true`, this operation will be automatically pushed into the stack by default. Set `stack` to be `false` if you do not want it. |

**Usage**

```javascript
// Find the item instance by id
const item = graph.findById('node');
graph.removeItem(item);
```

### remove(item, stack)

The same as removeItem(item)。
