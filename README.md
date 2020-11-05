# Next.js with chakra-ui, GraphQL and Typescript

This [Next.js](https://nextjs.org/) app uses the [chakra-ui](https://next.chakra-ui.com/) component library and [Apollo Client](https://www.apollographql.com/docs/react/) to connect to your GraphQL backend out of the box.

Next.js, chakra-ui and Apollo all have built-in TypeScript declarations.

The chakra-ui `ChakraProvider` in `/pages/_app.tsx` provides theming context, color mode (dark/light) and global styles from `theme.tsx` to all components.

## Deploy this demo

Deploy the example using [Vercel](https://vercel.com):

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/import/project?template=https://github.com/anselbrandt/next-chakra)

## How to use

### Using `npx degit`

Execute [`npx degit`](https://github.com/Rich-Harris/degit) to bootstrap the example:

```bash
npx degit https://github.com/anselbrandt/next-chakra next-chakra
```

Then:

```
cd next-chakra
yarn
```

After that:

```
yarn dev
or
yarn build
```

## Setup

GraphQL server endpoints may be configured in `constants.ts` and `.env.local` ensuring to prefix variables with `NEXT_PUBLIC_` as in the `sample.env.local` file.

The GraphQL client can be configured in `/utils/withApollo.ts`

## GraphQL

Queries must be named:

```
query QueryName {
  ...
}
```

After adding any new queries to the `/graphql/` folder, execute `yarn gen`

[GraphQL code generator](https://graphql-code-generator.com/) will connect to your GraphQL server, generate typings based on your schema and output custom `hooks` to `/generated/graphql.tsx`.

Queries can be imported as:

```
import { useQueryName } from "../generated/graphql";
...
const { data, loading, error } = useQueryName();
```
