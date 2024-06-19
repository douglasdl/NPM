# NPM
Node Package Manager

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





## References
- [Tutorial 1](https://www.freecodecamp.org/news/how-to-create-and-publish-your-first-npm-package/)
https://www.npmjs.com/
