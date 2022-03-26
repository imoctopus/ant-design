---
order: 12
title:
  zh-CN: 带字数提示
  en-US: With character counting
---

## zh-CN

展示字数提示。

## en-US

Show character counting.

```tsx
import { Input } from 'antd';

const { TextArea } = Input;

const onChange = (e: React.ChangeEvent<HTMLInputElement | HTMLTextAreaElement>) => {
  console.log('Change:', e.target.value);
};

ReactDOM.render(
  <>
    <Input showCount maxLength={20} onChange={onChange} />
    <br />
    <br />
    <TextArea showCount maxLength={100} onChange={onChange} />
  </>,
  mountNode,
);
```
