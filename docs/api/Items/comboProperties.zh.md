---
title: Combo 配置项
order: 5
---
## Combo 的通用属性

### id
| 属性名 | 类型 | 是否必须 | 示例 | 解释 |
| ----- | ---- | ---- | ---- | ---- |
| id | string | true | 'comboA' | 一个 Combo 的唯一标识，**必须是 string 类型，必须唯一** |

### parentId
| 属性名 | 类型 | 是否必须 | 示例 | 解释 |
| ----- | ---- | ---- | ---- | ---- |
| parentId | string | false | 'comboB' | 该 Combo 的父 Combo 的 ID |

### padding
| 属性名 | 类型 | 是否必须 | 示例 | 解释 |
| ----- | ---- | ---- | ---- | ---- |
| padding | Number / Number[] | false | 10 或 [ 10, 20, 10, 20 ] | 该 Combo 内边距 |

### style
| 属性名 | 类型 | 是否必须 | 示例 | 解释 |
| ----- | ---- | ---- | ---- | ---- |
| style | Object | false |  | 该 Combo 的样式配置项，详见[内置 Combo 配置文档](/zh/docs/manual/middle/elements/combos/defaultCombo#样式属性-style)及各类型 Combo 的文档 |

### label
| 属性名 | 类型 | 是否必须 | 示例 | 解释 |
| ----- | ---- | ---- | ---- | ---- |
| label | string | false | 'combo A' | 该 Combo 的文本标签 |

### labelCfg
| 属性名 | 类型 | 是否必须 | 示例 | 解释 |
| ----- | ---- | ---- | ---- | ---- |
| labelCfg | Object | false |  | 该 Combo 的文本标签样式配置项，详见[内置 Combo 配置文档](/zh/docs/manual/middle/elements/combos/defaultCombo#标签文本-label-及其配置-labelcfg)及各类型 Combo 的文档 |

## 内置 Combo 的特有属性
