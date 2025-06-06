Under tsgo, using a class based react component imported from a `jsx` files produce errors complaining that the props are not assignable to the component's type.

tsgo:

```
$ yarn run tsgo

index.tsx:6:25 - error TS2769: No overload matches this call.
  The last overload gave the following error.
    Type '{ text: string; }' is not assignable to type 'IntrinsicAttributes & IntrinsicClassAttributes<MyComponent> & Readonly<{}>'.
      Property 'text' does not exist on type 'IntrinsicAttributes & IntrinsicClassAttributes<MyComponent> & Readonly<{}>'.

6     return <MyComponent text="hello" />
                          ~~~~

  node_modules/@types/react/index.d.ts:1021:9 - The last overload is declared here.
    1021         constructor(props: P, context: any);
                 ~~~~~~~~~~~

Found 1 error in index.tsx:6

error Command failed with exit code 2.
```

tsc:

```
$ yarn run tsc
Done in 1.93s.
```
