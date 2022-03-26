---
order: 6.1
title:
  zh-CN: 选择不超过七天的范围
  en-US: Select range dates in 7 days
---

## zh-CN

这里举例如何用 `onCalendarChange` 和 `disabledDate` 来限制动态的日期区间选择。

## en-US

A example shows how to select a dynamic range by using `onCalendarChange` and `disabledDate`.

```tsx
import { DatePicker } from 'antd';
import type { Moment } from 'moment';

const { RangePicker } = DatePicker;

const App = () => {
  const [dates, setDates] = React.useState([]);
  const [hackValue, setHackValue] = React.useState<[Moment, Moment] | undefined>();
  const [value, setValue] = React.useState<[Moment, Moment]>([null, null]);

  const disabledDate = (current: Moment) => {
    if (!dates || dates.length === 0) {
      return false;
    }
    const tooLate = dates[0] && current.diff(dates[0], 'days') > 7;
    const tooEarly = dates[1] && dates[1].diff(current, 'days') > 7;
    return tooEarly || tooLate;
  };

  const onOpenChange = (open: boolean) => {
    if (open) {
      setHackValue([null, null]);
      setDates([]);
    } else {
      setHackValue(undefined);
    }
  };

  return (
    <RangePicker
      value={hackValue || value}
      disabledDate={disabledDate}
      onCalendarChange={val => setDates(val)}
      onChange={val => setValue(val)}
      onOpenChange={onOpenChange}
    />
  );
};

ReactDOM.render(<App />, mountNode);
```
