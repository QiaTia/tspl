# TSPL打印指令生成

### 开始使用

```typescript
import TSPL, { toBytes } from 'js-tspl';
const tspl = new TSPL();
tspl.addText('Print test!');

const cmd = toBytes(tspl.toPrint());

```

### 链式调用

```typescript
import TSPL, { toBytes } from 'js-tspl';

const cmd = toBytes(
  new TSPL()
    .addText('Print test!')
    .addLine()
    // toPrint 和 toBytes 会结束调用
    .toBytes();
);

```
### 国内打印机一般需要先转gbk码
```typescript
import TSPL, { toBytes, encodeGBK } from 'js-tspl';
const tspl = new TSPL();
tspl.addText('Print test!');

const cmd = toBytes(encodeGBK(tspl.toPrint()));

```
