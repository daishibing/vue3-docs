# props

props 用于父组件向子组件传递数据，且是单向数据流，子组件不应直接修改

# 基础示例

`components/DataItem.vue`：

```vue
<script setup lang="ts">
interface Props {
    text: string
}

const props = defineProps<Props>()
</script>

<template>
    <p>{{ props.text }}</p>
</template>
```

`App.vue`：

```vue
<script setup lang="ts">
import DataItem from "@/components/DataItem.vue"
</script>

<template>
    <DataItem text="父组件传入的内容" />
</template>
```


