---
aliases: 
created_at: 2023-04-18T10:57:00-04:00
created: 2023-04-18, 10:52:07 am (Tuesday, April 18th)
updated: 2023-04-18, 10:57:55 am (Tuesday, April 18th)
---

## Passing in styles from the `css` helper
```
import styled, { FlattenSimpleInterpolation } from 'styled-components';

const Container = styled.div<{ styleOverrides?: FlattenSimpleInterpolation }>`
    ${p => p.styleOverrides || null}
`;

const fixedWidthContainerStyles = css`
  width: 200px;
`;

const FixedWidthContainer = () => (
  <Container
    styleOverrides={fixedWidthContainerStyles}
  />
);
```

## Spreading props
https://copyprogramming.com/howto/using-the-spread-operator-in-styled-components