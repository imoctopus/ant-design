---
order: 4
title:
  zh-CN: 自定义描述文案
  en-US: Customized description
---

## zh-CN

自定义描述文案。

## en-US

Customized description content.

```tsx
import React from 'react';
import { Spin, Alert } from 'antd';

const App = () => (
  <Spin tip="Loading...">
    <Alert
      message="Alert message title"
      description="Further details about the context of this alert."
      type="info"
    />
  </Spin>
);

ReactDOM.render(<App />, mountNode);
```
