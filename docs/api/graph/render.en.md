---
title: render/refresh/pain
order: 10
---

### render()

Render the graph with data onto the canvas.

**Usage**

```javascript
graph.render();
```

### renderCustomGroup(data, groupType)

Render a node group according to the data.

**Parameters**

| Name      | Type   | Required | Description                                         |
| --------- | ------ | -------- | --------------------------------------------------- |
| data      | Object | true     | The data to be rendered                             |
| groupType | string | true     | Type of node group. Options: `'circle'` or `'rect'` |

**Usage**

```javascript
const data = {
  nodes: [
    {
      id: 'node1',
      groupId: 'group1',
      label: 'node1',
    },
    {
      id: 'node2',
      groupId: 'group1',
      label: 'node2',
    },
  ],
  edges: [
    {
      source: 'node1',
      target: 'node2',
    },
  ],
  groups: [
    {
      id: 'group1',
      title: {
        text: 'My Group 1',
        stroke: '#444',
        offsetX: -20,
        offsetY: 30,
      },
    },
  ],
};

// graph is an instance of Graph
graph.renderCustomGroup(data, 'circle');
```

### read(data)

Read the data and render the graph. It is equal to combining graph.data(data) and graph.render().

**Parameters**

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| data | Object | true | Graph data, it should be an object containing an array of nodes and an array of edges. |

**Usage**

```javascript
const data = {
  nodes: [
    {
      id: 'node1',
      label: 'node1',
    },
    {
      id: 'node2',
      label: 'node2',
    },
  ],
  edges: [
    {
      source: 'node1',
      target: 'node2',
    },
  ],
};

// graph is an instance of Graph
graph.read(data);
```

### changeData(data, stack)

Change the data source, and render the graph according to the new data.

**Parameters**

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| data | Object | false | Graph data, it should be an object containing an array of nodes and an array of edges. If it is not assigned, the graph will be re-rendered with the current data on the graph |
| stack | boolean | false | Whether to push the operator into the undo & redo stack. If the `enableStack` is `true`, this operation will be automatically pushed into the stack by default. Set `stack` to be `false` if you do not want it. |

**Usage**

```javascript
const data = {
  nodes: [
    {
      id: 'node1',
      label: 'node1',
    },
    {
      id: 'node2',
      label: 'node2',
    },
  ],
  edges: [
    {
      source: 'node1',
      target: 'node2',
    },
  ],
};

// graph is an instance of Graph
graph.changeData(data);

// If there is no parameter, the graph will be re-rendered with the current data on the graph
graph.changeData();
```

### refresh()

Refresh the canvas when the **existing** data items' configurations is changed in the source data.

Attention: If there are some new nodes/edges/combos to be added or some nodes/edges/combos to be removed, use [graph.addItem](./Graph#additemtype-model) / [graph.removeItem](./Graph#removeitemitem) or [graph.changeData](./Graph#changedatadata) instead.

**Usage**

```javascript
graph.refresh();
```

### refreshItem(item)

Refresh the item.

**Parameters**

| Name | Type            | Required | Description                         |
| ---- | --------------- | -------- | ----------------------------------- |
| item | string / Object | true     | The id or the instance of the item. |

**Usage**

```javascript
// Find the item instance by id
const item = graph.findById('node');
graph.refreshItem(item);
```

### refreshPositions()

When the positions of nodes in their data models are changed, refresh the canvas to paint the nodes with new positions. It will update the edges in the same time.

**Usage**

```javascript
graph.refreshPositions();
```

### paint()

Repaint the canvas. Use it after changing the item's style or state.

**Usage**

```javascript
const item = e.item;
const graph = this.graph;

const autoPaint = graph.get('autoPaint');
graph.setAutoPaint(false);

graph.setItemState(item, 'selected', true);

graph.paint();
graph.setAutoPaint(autoPaint);
```

### setAutoPaint(auto)

Whether to repaint the canvas automatically after updating or deleting items.

**Parameters**

| Name | Type    | Required | Description                                  |
| ---- | ------- | -------- | -------------------------------------------- |
| auto | Boolean | true     | Whether to repaint the canvas automatically. |

**Usage**

```javascript
const item = e.item;
const graph = this.graph;

const autoPaint = graph.get('autoPaint');
graph.setAutoPaint(false);

graph.setItemState(item, 'selected', true);

graph.paint();
graph.setAutoPaint(autoPaint);
```
