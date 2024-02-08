---
title: React封装axios
date: 2023-10-17 08:04:00
categories: Front End
tags:
  - React
  - Front-end
---

封装 Axios 可以让你更方便地在 React 应用中使用 HTTP 请求。
下面是一个简单的例子，演示如何在 React 中封装 Axios：

1. 首先，确保你已经安装了 Axios：

```bash
npm install axios
```

2. 创建一个新的文件，例如 `api.js`，并在其中封装 Axios：

```javascript
// api.js
import axios from 'axios';

const instance = axios.create({
  baseURL: 'https://your-api-base-url.com/', // 修改为你的API基地址
  timeout: 10000, // 设置请求超时
  headers: {
    'Content-Type': 'application/json',
  },
});

export default instance;
```

3. 在 React 组件中使用封装好的 Axios：

```javascript
// MyComponent.jsx
import React, { useState, useEffect } from 'react';
import api from './api';

function MyComponent() {
  const [data, setData] = useState(null);
  const [loading, setLoading] = useState(true);
  const [error, setError] = useState(null);

  useEffect(() => {
    api.get('/endpoint')
      .then(response => {
        setData(response.data);
        setLoading(false);
      })
      .catch(err => {
        setError(err);
        setLoading(false);
      });
  }, []);

  if (loading) return <div>Loading...</div>;

  return (
    <div>
      <h1>Data fetched from API:</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
}

export default MyComponent;
```

这是一个简单的封装示例。根据你的需求，你可能需要添加更多的功能，例如错误处理、请求拦截、响应拦截等。

这种方式将网络请求逻辑与组件逻辑分离，使得代码更加模块化和可维护。
