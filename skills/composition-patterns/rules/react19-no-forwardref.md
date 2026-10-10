---
title: React 19 API Changes
impact: MEDIUM
impactDescription: cleaner component definitions and context usage
tags: react19, refs, context, hooks
---

## React 19 API Changes

> **⚠️ React 19+ only.** Skip this if you're on React 18 or earlier.

In React 19, `ref` is available as a regular prop for function components, so
new components usually do not need a `forwardRef` wrapper. React 19 also allows
reading context with `use()`, including conditionally; `useContext()` remains a
supported and clear choice for unconditional reads.

**Incorrect (forwardRef in React 19):**

```tsx
const ComposerInput = forwardRef<TextInput, Props>((props, ref) => {
  return <TextInput ref={ref} {...props} />
})
```

**Correct (ref as a regular prop):**

```tsx
function ComposerInput({ ref, ...props }: Props & { ref?: React.Ref<TextInput> }) {
  return <TextInput ref={ref} {...props} />
}
```

**Existing unconditional context read (still valid):**

```tsx
const value = useContext(MyContext)
```

**Use `use()` when its conditional-call capability is useful:**

```tsx
const value = use(MyContext)
```

`use()` can also be called conditionally, unlike `useContext()`.
