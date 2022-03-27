---
order: 7
title:
  zh-CN: 菜单隐藏方式
  en-US: The way of hiding menu.
---

## zh-CN

默认是点击关闭菜单，可以关闭此功能。

## en-US

The default is to close the menu when you click on menu items, this feature can be turned off.

```tsx
import { Menu, Dropdown } from 'antd';
import { DownOutlined } from '@ant-design/icons';
import type { MenuProps } from 'antd';

const App = () => {
  const [visible, setVisible] = React.useState(false);

  const handleMenuClick: MenuProps['onClick'] = e => {
    if (e.key === '3') {
      setVisible(false);
    }
  };

  const menu = (
    <Menu onClick={handleMenuClick}>
      <Menu.Item key="1">Clicking me will not close the menu.</Menu.Item>
      <Menu.Item key="2">Clicking me will not close the menu also.</Menu.Item>
      <Menu.Item key="3">Clicking me will close the menu.</Menu.Item>
    </Menu>
  );

  return (
    <Dropdown overlay={menu} visible={visible} onVisibleChange={setVisible}>
      <a className="ant-dropdown-link" onClick={e => e.preventDefault()}>
        Hover me <DownOutlined />
      </a>
    </Dropdown>
  );
};

ReactDOM.render(<App />, mountNode);
```
