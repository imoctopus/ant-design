---
order: 2
title:
  zh-CN: 嵌套评论
  en-US: Nested comments
---

## zh-CN

评论可以嵌套。

## en-US

Comments can be nested.

```tsx
import React from 'react';
import { Comment, Avatar } from 'antd';

const ExampleComment: React.FC = ({ children }) => (
  <Comment
    actions={[<span key="comment-nested-reply-to">Reply to</span>]}
    author={<a>Han Solo</a>}
    avatar={<Avatar src="https://joeschmoe.io/api/v1/random" alt="Han Solo" />}
    content={
      <p>
        We supply a series of design principles, practical patterns and high quality design
        resources (Sketch and Axure).
      </p>
    }
  >
    {children}
  </Comment>
);

const App = () => (
  <ExampleComment>
    <ExampleComment>
      <ExampleComment />
      <ExampleComment />
    </ExampleComment>
  </ExampleComment>
);

ReactDOM.render(<App />, mountNode);
```
