# how SCC came

When I first found [styled components](https://www.styled-components.com/),
I thought it would be the cure to chaos of className binding.

I usually use React + css-modules, that's why there would be a lot of code like:

```js
import styles from "./componnet.css";

export default () => (
  <div className={styles.container}>
    <h1 className={styles.title}>Title</h1>
    <button className={styles.button}>Click Me!</h1>
  </div>
);
```

It looks look, but when component is complicated it looks not concise anymore.

With styled component, we write it in a more componented way in js fashion

```js
export default () => (
  <Container>
    <Title>Title</Title>
    <Button>Click me!</Button>
  </Container>
);

const Container = styled.div`
  background-color: #eee;
`;
const Title = styled.h1`
  font-size: 2rem;
`;
```

This looks good in jsx!
But the declaration of styled component still looks not natural.

Styled component declarations are mostly raw css code, so why don't we keep in a css fashion?

with SCC, we could write it in two files:

style

```
Container {
  component: div;
  background-color: #eee;
}

Title {
  component: h1;
  font-size: 2rem;
}
```

js

```js
import * from './component.scc'
export default () => (
  <Container>
    <Title>Title</Title>
    <Button>Click me!</Button>
  </Container>
);
```

isn't this cool? there is no information about html or css in js file.
and it works good!
