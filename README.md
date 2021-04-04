### Initialize Project

```react
npx create-react-app jira --template typescript
```

### Project Configuration

```json
//tsconfig.json
{
  "compilerOptions": {
    "baseUrl": "./src",
    "target": "es5",
    "lib": [
      "dom",
      "dom.iterable",
      "esnext"
    ],
    "allowJs": true,
    "skipLibCheck": true,
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noFallthroughCasesInSwitch": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "jsx": "react-jsx"
  },
  "include": [
    "src"
  ]
}

```

```js
npm install --save-dev --save-exact prettier
yarn add --dev --exact prettier
```

#### Pre-commit Hook

```js
npx mrm lint-staged
npm install husky -D
```

```json
//package.json
"devDependencies": {
    "lint-staged": "^10.5.4",
    "prettier": "2.2.1",
    "simple-git-hooks": "^2.2.0"
  },
  "simple-git-hooks": {
    "pre-commit": "npx lint-staged"
  },
  "lint-staged": {
    "*.{js,css,md,ts,tsx}": "prettier --write"
  }
```

#### ESLint

```js
yarn add eslint-config-prettier -D
```

```json
//package.json
"eslintConfig": {
    "extends": [
      "react-app",
      "react-app/jest",
      "prettier"
    ]
  }
```

#### commitlint

```js
npm install --save-dev @commitlint/config-conventional @commitlint/cli

echo "module.exports = {extends: ['@commitlint/config-conventional']}" > commitlint.config.js
```

```js
npm install husky --save-dev

yarn husky install

yarn husky add .husky/commit-msg "yarn commitlint --edit $1"
```

#### json-server

```js
yarn add json-server -D
```

