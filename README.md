- 直したところ（ [差分](https://github.com/Cside/eslint-plugin-react-memo/compare/49b926..HEAD) ）
  - ⭐⭐無引数の場合は警告しない
  - ⭐Component じゃないやつを誤判定しちゃう問題
  - named export したやつを検出しない問題
- TODO: https://www.notion.so/239431d647c04f70bfdf2837b039fd6c ⚠️⚠️⚠️

---------------------

# eslint-plugin-react-memo

Enforce that all function components are wrapped in `React.memo`, and that all props and deps are wrapped in `useMemo`/`useCallback` so they don’t break memo.

Rationale: [Why we memo all the things](https://attardi.org/why-we-memo-all-the-things/).

## Rules

### `require-memo`

Requires all function components to be wrapped in `React.memo()`.

### `require-usememo`

Requires complex values (objects, arrays, functions, and JSX) that get passed props or referenced as a hook dependency to be wrapped in `React.useMemo()` or `React.useCallback()`.

Options:

- `{strict: true}`: Fails even in cases where it is difficult to determine if the value in question is a primitive (string or number) or a complex value (object, array, etc.).

### `require-usememo-children` (**ADVANCED**)

Requires complex values (objects, arrays, functions, and JSX) that get passed as children to be wrapped in `React.useMemo()` or `React.useCallback()`.

Options:

- `{strict: true}`: Fails even in cases where it is difficult to determine if the value in question is a primitive (string or number) or a complex value (object, array, etc.).
