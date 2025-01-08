# React.FC
**Reactで関数コンポーネントを定義するときはTypeScriptの型付けには2つ書き方がある。**

1. React.FCを使用する書き方

```TypeScript:React.FC
type Props = {
    name: string;
}

const MyComponent: React.FC<Props> = ({name}) => {
    return <h1> Hello {name} </h1>
}
```

2. React.FCを使用しない書き方

```TypeScript:NotReact.FC
type Props = {
    name: string;
}

const Mycomponent: ({name}:Props):React.JSX.Element => {
    return <h1> Hello {name} </h1>
}
```

## 使わない人の考え方
・ Childrenが勝手に許容されるから(既に修正済み)
・ジェネリクスが使えない

## 積極的に使う理由
・ Reactのコンポーネントの戻り値の型が多くどれを使えばいいかわからない問題
```tsx
React.ReactNode, JSX.Element, React.JSX.Element, React.ReactElement
```
どれを記述してもReactコンポーネントとして認識する。

