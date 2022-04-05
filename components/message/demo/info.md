---
order: 0
title:
  zh-CN: 普通提示
  en-US: Normal prompt
---

## zh-CN

信息提醒反馈。

## en-US

Normal message for information.

```tsx
import React from 'react';
import { message, Button } from 'antd';

const info = () => {
  message.info('This is a normal message');
};

const App = () => (
  <Button type="primary" onClick={info}>
    Display normal message
  </Button>
);

ReactDOM.render(<App />, mountNode);
```
