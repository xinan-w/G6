---
title: focusItem(item, animate, animateCfg)
order: 10
---

Move the graph to center at the item. This operation can be used as easing animation after searching a node.

**Parameters**

| Name | Type | Required | Description |
| --- | --- | --- | --- |
| item | string / Object | true | The id or the instance of the item. |
| animate | boolean | false | Whether move the graph with animation. If it is not assigned, animates following the graph's `animate`. |
| animateCfg | Object | false | The animation's configuraiton. Its configurations can be found in [Basic Animation Docs](/en/docs/manual/advanced/animation#animatecfg). If it is not assigned, animates following the graph's `animateCfg`. |

**Usage**

```javascript
graph.focusItem(item);

// focus with animation
graph.focusItem(item, true);

// focus with animation and animation's configuration
graph.focusItem(item, true, {
  easing: 'easeCubic',
  duration: 400,
});
```

</div>
