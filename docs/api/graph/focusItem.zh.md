---
title: focusItem(item, animate, animateCfg)
order: 10
---

移动图，使得 item 对齐到视口中心，该方法可用于做搜索后的缓动动画。

**参数**

| 名称 | 类型 | 是否必选 | 描述 |
| --- | --- | --- | --- |
| item | string / Object | true | 元素 ID 或元素实例 |
| animate | boolean | false | 是否带有动画。若未配置，则跟随 graph 的 `animate` 参数 |
| animateCfg | Object | false | 若带有动画，可配置动画，参见[基础动画教程](/zh/docs/manual/advanced/animation#animatecfg)。若未配置，则跟随 graph 的 `animateCfg` 参数 |

**用法**

```javascript
graph.focusItem(item);

// 动画地移动
graph.focusItem(item, true);

// 动画地移动，并配置动画
graph.focusItem(item, true, {
  easing: 'easeCubic',
  duration: 400,
});
```

</div>
