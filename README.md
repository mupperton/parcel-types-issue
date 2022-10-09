# parcel-types-issue

Two examples of typing declaration files appearing to not bundle as expected

Issue filed on parcel's repo: https://github.com/parcel-bundler/parcel/issues/7790

## Setup

```sh
npm ci
```

## Example one

Source code imports custom type from declaration file in the **same** directory

```sh
npm run one
```

Look at `/dist/types.d.ts` and note that it's also trying to import my custom type from a file in the same directory that doesn't exist

## Example two

Source code imports custom type from declaration file in the **parent** directory

```sh
npm run two
```

Look at `/dist/types.d.ts` and note that it's also trying to import my custom type from a file in the parent directory that doesn't exist


## Findings

In both examples the resulting declaration file in the `dist` folder appears to mimic the relativity of the imports from the source code, but does not bundle the referenced declaration file...
