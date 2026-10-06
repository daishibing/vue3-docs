# Vue 文件规范

通过 ESLint 配置，统一 Vue 文件规范

# 规范说明

| 规则             | 主要作用         | 使用原因                                            |
|------------------|------------------|-----------------------------------------------------|
| block-order      | 检查代码块顺序   | 统一 `<script>`、`<template>`、`<style>` 的排列顺序 |
| block-lang       | 检查代码块语言   | 统一 `<script>` 使用 TypeScript                     |
| attributes-order | 检查模板属性顺序 | 统一 Vue 模板属性的排列顺序                         |

# 配置 `eslint.config.ts`

```ts
import { defineConfigWithVueTs } from "@vue/eslint-config-typescript"

export default defineConfigWithVueTs(
    // 其他配置
    {
        rules: {
            "vue/block-order": [
                "error",
                {
                    order: ["script", "template", "style"],
                },
            ],
            "vue/block-lang": [
                "error",
                {
                    script: {
                        lang: "ts",
                    },
                },
            ],
            "vue/attributes-order": "error",
        },
    },
)
```


