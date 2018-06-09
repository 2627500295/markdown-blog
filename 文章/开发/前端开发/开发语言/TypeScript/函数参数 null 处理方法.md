# 函数参数 null 处理方法

```typescript
function func(a: number|null = 1, n: number = 1): number {
  let b: number;
  b = a || 1;

  return b + n;
}

func(null, 3);
```
