# 函数参数为 `null` 或 `undefined` 时的处理方法

```typescript
/**
 * 加法
 * 
 * @param a
 * @param b
 * 
 * @returns the result of a + b
 */
function plus(a?: number | null, b?: number | null): number {
  a ??= 0;
  b ??= 0;
  return a + b;
}

plus();
plus(1);
plus(1, null);
plus(null, 1);
plus(1, 1);
```
