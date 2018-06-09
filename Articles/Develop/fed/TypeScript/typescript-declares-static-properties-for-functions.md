# `Typescript` 为函数声明静态属性

```typescript
function setup() {
  if (setup.installed) return;
  setup.installed = true;
}

declare namespace setup {
  let installed: undefined | boolean;
}
```
