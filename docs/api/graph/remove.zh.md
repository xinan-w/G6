---
title: graph.remove*
order: 10
---

### removeItem(item, stack)

删除元素，当 item 为 group ID 时候，则删除分组。

**参数**

| 名称 | 类型 | 是否必选 | 描述 |
| --- | --- | --- | --- |
| item | string / Object | true | 元素 ID 或元素实例 |
| stack | boolean | false | 操作是否入 undo & redo 栈，当实例化 Graph 时设置 enableStack 为 true 时，默认情况下会自动入栈，入栈以后，就支持 undo & redo 操作，如果不需要，则设置该参数为 false 即可 |

**用法**

```javascript
// 通过 ID 查询节点实例
const item = graph.findById('node');
graph.removeItem(item);

// 该操作不会进入到 undo & redo 栈，即 redo & undo 操作会忽略该操作
graph.removeItem(item, false);
```

### remove(item, stack)

同 removeItem(item, stack)。
