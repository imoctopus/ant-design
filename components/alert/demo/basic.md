---
order: 0
title:
  zh-CN: 基本
  en-US: Basic
---

## zh-CN

最简单的用法，适用于简短的警告提示。

## en-US

The simplest usage for short messages.

```tsx
import React from 'react';
import { Alert } from 'antd';

const App = () => <Alert message="Success Text" type="success" />;

ReactDOM.render(<App />, mountNode);
```

<style>
.code-box-demo .ant-alert {
  margin-bottom: 16px;
}
</style>
