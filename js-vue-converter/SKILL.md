---
name: "Alano"
description: "Auto-detects JS vs Vue input and converts between plain JS snippets and Vue code structures. Invoke when the user provides code to transform between JS and Vue."
---

# JS 与 Vue 互转

## 适用场景

- 自动识别 JS 或 Vue 并互转
- 把片段补全为可运行的 Vue SFC 或 JS 模块

## 输入要求

- 提供源代码即可，默认自动识别类型
- 可选说明版本（如 Vue 2/3）

## 自动识别规则

- 含有 <template>/<script>/<style> 或 SFC 结构判定为 Vue
- 含有 defineComponent、export default 组件对象、setup() 判定为 Vue
- 含有 createApp、app.mount、Vue.component 判定为 Vue
- 其他情况按纯 JS 处理

## 转换要点

- JS 到 Vue：状态进 data 或 ref/reactive，函数进 methods 或 setup
- Vue 到 JS：抽取 data/props/methods 为纯函数与模块导出

## 输出要求

- 生成可直接使用的代码
- 保持行为一致
