# SCC spec

SCC is based on CSS Spec and styled-components, it extends css by adding following new specs.

## 1. new rule: component

```css
container: {
  component: h1;
  color: red;
}
```

`component` is used to specify which html tag to be used.

it is optional, default to `div`

## 2. `calc()` accepts JavaScript functions

```css
container: {
  component: h1;
  color: red;
  font-size: calc((props) => props.size);
}
```

css `calc()` only accept simple calculation with special rules.
in scc, `calc()` could be also be used as props function in styled component.

`calc((props) => prop.size)` will be transformed into `${(props) => props.size}` in styled component,

yet normal `calc()` not starting with `(props)` or `props` will be treated as normal css rules and no touched.
