# 封装 jsonRequest

封装 `jsonRequest<T>()`，统一处理 JSON 数据请求

# 封装实现

`src/requests/json.ts`：

```ts
import { request } from "./instance"

import type { AxiosRequestConfig } from "axios"

/**
 * 发送 JSON 数据请求
 * @param config 请求配置
 */
async function jsonRequest<T>(config: Omit<AxiosRequestConfig, "headers">): Promise<T> {
    const response = await request<T>({
        ...config,
        headers: {
            "Content-Type": "application/json",
        },
        method: config.method ?? "post",
        responseType: config.responseType ?? "json",
    })

    return response.data
}

export { jsonRequest }
```


