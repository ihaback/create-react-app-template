# Create your own Create React App Template

Create React App is a convienient way to start building a new single-page application in React. Your app only needs one build dependency `react-scripts`. Under the hood it uses webpack, Babel, ESLint, and other amazing projects to power your app.

## Make it your own

If you don't like the default scaffold of create react app it really easy to adjust.

- Start by creating a folder called `cra-template`.

- Cd into the folder and run `yarn init -y` or `npm init -y` if your prefer npm. This will generate a basic `package.json` file for you.

- Create a `template.json` with your specific template settings. Any dependencies you add here will be added to the final dependency list.

```json
{
  "package": {
    "dependencies": {
      "@testing-library/jest-dom": "^5.11.4",
      "@testing-library/react": "^11.1.0",
      "@testing-library/user-event": "^12.1.10",
      "web-vitals": "^1.0.1"
    },
    "eslintConfig": {
      "extends": ["react-app", "react-app/jest"]
    }
  }
}
```

- Create a `template` folder.

- Create a `gitignore` file with the content below. Make sure to omit the dot.

```yml
# See https://help.github.com/articles/ignoring-files/ for more about ignoring files.

# dependencies
/node_modules
/.pnp
.pnp.js

# testing
/coverage

# production
/build

# misc
.DS_Store
.env.local
.env.development.local
.env.test.local
.env.production.local

npm-debug.log*
yarn-debug.log*
yarn-error.log*
```

- Inside the `template` folder create a `public` folder with the following `index.html`.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8" />
    <link rel="icon" href="%PUBLIC_URL%/favicon.ico" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <meta name="theme-color" content="#000000" />
    <meta
      name="description"
      content="Web site created using create-react-app"
    />
    <link rel="apple-touch-icon" href="%PUBLIC_URL%/logo192.png" />
    <link rel="manifest" href="%PUBLIC_URL%/manifest.json" />

    <title>CRA template</title>
  </head>
  <body>
    <noscript>You need to enable JavaScript to run this app.</noscript>
    <div id="root"></div>
  </body>
</html>
```

- Inside the `template` folder create a `src` folder and an `index.tsx` in it.

```ts
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";

ReactDOM.render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
  document.getElementById("root")
);
```

- Inside the `template/src` folder create a `App.tsx` file.

```ts
import React from "react";

const App = () => {
  return <div>My CRA template</div>;
};

export default App;
```

- Test that your scaffold is working locally by running

```bash
npx create-react-app my-app --template file:.
```

## Publish to npm

```bash
npm publish
```

## Use your published template in a project

```bash
npx create-react-app my-app --template your-template-name
```

```bash
npx create-react-app my-app --template barebones
```
