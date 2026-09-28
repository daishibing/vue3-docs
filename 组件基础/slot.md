# slot

slot 用于向子组件传递模板内容

# 默认插槽基础示例

`components/DataItem.vue`：

```vue
<template>
    <div>
        <slot>
            <p>默认内容</p>
        </slot>
    </div>
</template>
```

`App.vue`：

```vue
<script setup lang="ts">
import DataItem from "@/components/DataItem.vue"
</script>

<template>
    <DataItem>
        <p>插槽内容</p>
    </DataItem>
</template>
```

# 具名插槽基础示例

`components/DataItem.vue`：

```vue
<template>
    <div>
        <slot name="slot-name">
            <p>默认内容</p>
        </slot>
    </div>
</template>
```

`App.vue`：

```vue
<script setup lang="ts">
import DataItem from "@/components/DataItem.vue"
</script>

<template>
    <DataItem>
        <template #slot-name>
            <p>插槽内容</p>
        </template>
    </DataItem>
</template>
```


