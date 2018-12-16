# SCC

SCC (**S**tyled **C**omponents in **C**SS) enables writing [Styled Components](https://github.com/styled-components/styled-components) in a CSS fashion.

# A brief example

define you styles and html tags in `scc` file

```
Title {
  component: h1;
  font-size: 1.5em;
  text-align: center;
}

Container {
  component: section;
  padding: 4em;
  background: papayawhip;
  font-size: (props.size === "large" ? "14px": "12px");
}
```

then import it , you can use it like styled component

```js
import React from "react";
import S from "./index.scc";
export default function Component() {
  return (
    <S.Container>
      <S.Title>Hello World, this is my first styled component!</c.Title>
    </S.Container>
  );
}
```

# interested?

if you find it interesting, here are links:

- [how it came](./history.md)
- [how to use it](./to-start.md)
- [spec](./spec.md)
