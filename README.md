# NPM
Node Package Manager

## Basic (Javascript)
From the project root directory init a NPM (package.json): 
```sh
npm init
# or scoped name
npm init --scope=@douglasdl
```

Add your code:
```sh
//index.js

function helloNpm() {
  return "hello NPM"
}

module.exports = helloNpm
```

Test your NPM Package:
```sh
npm link
```

Create the node_modules folder:
```sh
npm link <name-of-package>
```

Create a test/script.js file to import your package and test it:
```sh
const helloNpm = require('components')

console.log(helloNpm())
```

Run the file:
```sh
node test/script.js
```

Log in NPM:
```sh
npm login
```

Publish your NPM package:
```sh
npm publish
# or this for scoped name
npm publish --access public
# or
npm publish --access private
```

## With TypeScript:

From the project root directory init a NPM (package.json): 
```sh
npm init
# or scoped name
npm init --scope=@douglasdl
```

Install the dependencies:
```sh
npm install --save-dev typescript ts-node
```

Setup your tsconfig.json (Update the outDir field to "dist"):
```sh
npx tsc --init
```

Create your src folder and create your index.ts:
```sh
export function add(a: number, b: number): number {
  return a + b;
}

console.log(add(3, 5)); //output: 8
```

Start your code:
```sh
npx ts-node src/index
```

Init your git repo:
```sh
git init
```

Create a .gitignore file:
```sh
/node_modules

# Ignore test-related files
/coverage.data
/coverage/

# Build files
/dist
```

Create a README.md file:
```sh
# Description of your project and how to use it
```

Build your project with one of the follow tools (tsup, babel, webpack, rollup).

### Tsup

Install the dependencies:
```sh
npm install tsup -D
```

Create the "tsup.config.ts" file:
```sh
import { defineConfig } from "tsup";

export default defineConfig({
  entry: ["src/index.ts"],
  format: ["cjs", "esm"], // Build for commonJS and ESmodules
  dts: true, // Generate declaration file (.d.ts)
  splitting: false,
  sourcemap: true,
  clean: true,
});
```

Add this build script to your package.json:
```sh
"scripts": {
  "build": "tsup",
  "test": "echo \"Error: no test specified\" && exit 1"
},
```

Build the project:
```sh
npm run build
```

Update your package.json:
```sh
...
"main": "./dist/index.js",
"module": "./dist/index.mjs",
"types": "./dist/index.d.ts",
"files": [
    "dist"
 ],
...
```

### Testing your NPM package:

Install Jest dependencies:
```sh
npm install -D jest ts-jest @types/jest
```

Create the "jest.config.js" file:
```sh
module.exports = {
  preset: "ts-jest",
  testEnvironment: "node",
};
```

Create a "tests" folder and inside it the "add.test.ts" file:
```sh
import { add } from '../src';

test('adds two numbers correctly', () => {
  const result = add(2, 3);
  expect(result).toBe(5);
});
```

Update the "test" script in the "package.json" file:
```sh
"scripts": {
    "build": "tsup",
    "test": "jest"
 },
```

Run the tests:
```sh
npm run test
```

### Publishing your NPM Package:
Test your NPM Package (from the root of your project):
```sh
npm link
```

Create the node_modules folder (from the test folder):
```sh
npm link <name-of-package>
```

Create a "main.ts" file:
```sh
import { add } from "components"

console.log(add(2, 6))
```

Test locally:
```sh
npm install -g typescript
npm install -g ts-node
ts-node test/main.ts
```

Log in NPM:
```sh
npm login
```

Publish your NPM package:
```sh
# Increase the (patch, minor or major) version before publish
npm version patch
npm version minor
npm version major
#
npm publish
# or this for scoped name
npm publish --access public
# or
npm publish --access private
```

## References
 - [Tutorial 1](https://www.freecodecamp.org/news/how-to-create-and-publish-your-first-npm-package/)
 - [Tutorial 2](https://pauloe-me.medium.com/typescript-npm-package-publishing-a-beginners-guide-40b95908e69c)
 - [NPM](https://www.npmjs.com/)
