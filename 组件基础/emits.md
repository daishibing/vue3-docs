# emits

emits 用于子组件触发父组件绑定的自定义事件，并可携带数据

# 基础示例

`components/DataItem.vue`：

```vue
<script setup lang="ts">
interface Emits {
    send: [text: string]
}

const emit = defineEmits<Emits>()

function sendData() {
    emit("send", "子组件传入的内容")
}
</script>

<template>
    <button @click="sendData">触发事件</button>
</template>
```

`App.vue`：

```vue
<script setup lang="ts">
import DataItem from "@/components/DataItem.vue"

function handleSend(text: string) {
    console.log(text)
}
</script>

<template>
    <DataItem @send="handleSend" />
</template>
```


