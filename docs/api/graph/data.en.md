---
title: read /save/ load Data
order: 1
---

<!-- ## graph.data(_data_) -->

Load the data for graph.

**Parameters**

### data

<description> _Object_ **required** </description>

Graph data, it should be an object containing an array of nodes and an array of edges. |

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
graph.data(data);
```

### save()

Get the graph data.

**Return**

- Type of the return value: Object;
- The return value has all the nodes and edges as below:

```javascript
{
	nodes: [],
  edges: [],
  groups: [],
}
```

**Usage**

```javascript
graph.save();
```
