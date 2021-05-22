# Some Snippets

_Personal collection of frequented snippets for VSCode._ Find it in the [VSCode Marketplace](https://marketplace.visualstudio.com/items?itemName=ErinLee.react-typescript-cypress-testing-lib-snippets)

**Stack:** TypeScript ・ React ・ React Testing Library ・ Cypress

Found a lot of the current vscode snippets in the marketplace have aliases difficult to remember. Ain't nobody got time for that.
Created a personal set that makes it faster to retrieve & autocomplete.

- `add-` - Adds a snippet
- `new-` - Creates a new file template using the filename
- `clip-` - Wraps the clipboard contents in a snippet

## Example Screenshot:
`add-ComponentProps`:

![Screenshot: new-ComponentProps](https://user-images.githubusercontent.com/50590950/119012290-e92eee80-b963-11eb-8955-687f77ee788e.gif)

---

## Some JS Methods Snippets with Clipboard Copy

_works for JS & TS files_

|          Prefix | Method                            |
| --------------: | --------------------------------- |
| `clip-variable` | `const variable = YOUR_CLIPBOARD` |
|  `clip-console` | `console.log(YOUR_CLIPBOARD)`     |

## Some TS Methods Snippets

_works for TS files_

|          Prefix  | Method                     | Also works with |
| ---------------: | -------------------------- |-----------------|
| `add-interface` | `export interface IComponentContext { props: string }` | `interface` |
|  `add-type`     | `export type TSomething = props`    | `type` |
|  `ts-ignore`     | `// @ts-ignore`    |  |

## Some Snippets for React

### Hooks

|          Prefix  | Method                     | Also works with |
| ---------------: | -------------------------- |-----------------|
|  `add-useState`  | `const [item, setItem] = useState(CHOOSE_DEFAULTS)`  |    `useState`   |
| `add-useEffect`  | `useEffect(() => { }, [])` |    `useEffect`  |
| `add-useContext` | `const featureContext = useContext(FeatureContext)` |    `useContext`   |
| `add-useMemo`    | `const memoizedValue = useMemo(() => computeExpensiveValue(deps), [deps])` |    `useMemo`      |
| `add-useCallback`| `const memoizedCallback = useCallback(() => { fn(deps) }, [deps])` |    `useCallback`  |
| `add-useReducer` | `const [state, dispatch] = useReducer(reducer, initializerArg)` |    `useReducer`   |
| `add-useContext` | `const featureContext = useContext(FeatureContext)` |    `useContext`   |
| `add-useRef`     | `const ref = useRef(initialValue)` |    `useRef`       |

---
### `add-Props`

```javascript

interface IComponentProps {
  props: string
}

const Component: FC<IComponentProps> = (props) => {
```

### `new-Component`

```javascript
import React, { FC } from "react";

const Component: FC = () => {
  return <div></div>;
};

export default Component;
```

### `new-ComponentProps`

```javascript
import React, { FC } from "react";

interface IComponentProps {
  prop: <string|boolean|() => void|>;
}

const Component: FC<IComponentProps> = ({ prop }) => {
  return <div>{prop}</div>;
};

export default Component;
```

### `new-ContextProvider`

```javascript
import React, { createContext, ReactNode } from 'react'

export interface IComponentContextState {

}

const defaultState: IComponentContextState = {

}

export const ComponentContext = createContext(defaultState)

export const ComponentContextProvider = ({ children }: { children: ReactNode }): JSX.Element => {
  const state =
  return <ComponentContext.Provider value={state}>{children}</ComponentContext.Provider>
}

```

### `clip-Component`

```javascript
const Component: FC = () => {
  return <div></div>;
};
```

### `clip-ComponentProps`

```javascript
interface IComponentProps {
  prop: string;
}

const Component: FC<IComponentProps> = ({ prop }) => {
  return <div>{prop}</div>;
};
```

## Some Snippets for Unit Specs

Includes a quick way to watch your generated spec file. Just copy & paste to your console.

Remove commented snippet when done.

_works for JS & TS files_

### `add-test-Util`

```javascript
import { helper } from "./helper";

describe("helper", () => {
  it("", () => {
    const valueCheck = helper();
    expect(valueCheck).toBeTruthy();
  });
});

// npx jest ~/<FILE_PATH_TO_YOUR_COMPONENT>/helper.spec.ts --watch
```

## Some Snippets for React Specs

_ends in `.tsx`_

Uses [react-testing-library](https://testing-library.com/docs/react-testing-library/). Links to the testing library's cheatsheet.

Includes a quick way to watch your generated spec file. Just copy & paste to your console.

Remove commented links and snippet when done.

### `new-test-Component`

```javascript
import React from "react";
import {
  screen,
  fireEvent,
  waitFor,
  cleanup,
  render,
} from "@testing-library/react";
import userEvent from "@testing-library/user-event";
import Component from "./Component";

// See https://testing-library.com/docs/react-testing-library/cheatsheet
describe("<Component />", () => {
  beforeEach(() => {
    render(<Component />);
  });

  afterEach(cleanup);

  it("renders ", () => {
    expect(screen.getByText(/text/)).toBeTruthy();
  });
});

// npx jest ~/<FILE_PATH_TO_YOUR_COMPONENT>/Component.spec.tsx --watch
```

### `add-test-RenderBlock`

```javascript
it("renders ", () => {
  expect(screen.getByText(/text/)).toBeTruthy();
});
```

### `add-test-AsyncBlock`

```javascript
it("should allow user to enter values", async () => {
  fireEvent.change(screen.getByTestId("data-test"), {
    target: { value: "VALUE" },
  });
  userEvent.type(screen.getByTestId("data-test"), "{enter}");
  await waitFor(() => expect(screen.getByText(/text/i)).toBeTruthy());
});
```

## Some Snippets for Cypress Specs

### `add-test-Cy`

```javascript
describe("", () => {
  beforeEach(() => {
    cy.route("GET", "", {}).as("");
    cy.visit("/");
    cy.wait("@");
  });

  it("", () => {});
});
```

### `add-test-CyItBlock`

```javascript

it('', () => {
  cy.
})
```

### `add-test-CyRoute`

```javascript
cy.route("GET", "").as("");
```

--

😎
