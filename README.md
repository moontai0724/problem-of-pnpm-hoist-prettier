# Problem of pnpm default hoist Prettier packages

This is a POC for problem that pnpm default hoist Prettier packages may cause.

See https://github.com/pnpm/pnpm/issues/6738

## Steps to reproduce

1. Install the [esbenp.prettier-vscode](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode) VSCode extension.
2. Open [`index.ts`](index.ts) and format, you should see the code being changed.
3. Run `pnpm install` to install package `redis@3.0.0`, which is a problematic package that accidentally required Prettier.
4. Re-format [`index.ts`](index.ts), you should see the code being changed again.
