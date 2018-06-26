# SCC

SCC (**S**tyled **C**omponents in **C**SS) enables writing [Styled Components](https://github.com/styled-components/styled-components) in a CSS fashion.

# why

Style Component is good, but for some cases I find it better to separate the UI from the logic.

like for this example from styled component

```js
import React from 'react';

import styled from 'styled-components';

const Title = styled.h1`
  font-size: 1.5em;
  text-align: center;
  color: palevioletred;
`;

const Wrapper = styled.section`
  padding: 4em;
  background: papayawhip;
`;

export default function Component() {
    return <Wrapper>
        <Title>Hello World, this is my first styled component!</Title>
    </Wrapper>
}
```

With SCC, you can write in this way,


index.js
```js
import React from 'react';
import C from './index.scc';
export default function Component() {
    return <c.Wrapper>
        <c.Title>
            Hello World, this is my first styled component!
        </c.Title>
    </c.Wrapper>
}
```

index.scc
```css
Title {
    component: h1;
    font-size: 1.5em;
    text-align: center;
}

Wrapper {
    component: section;
    padding: 4em;
    background: papayawhip;
    font-size: (props.size === 'large' ? '14px': '12px')
}
```

# how to use

