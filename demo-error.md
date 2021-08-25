Use Babel to transpile those JS Modules and you'll be able to write your tests with es6.

Install Babel/preset-env
npm i -D @babel/preset-env

Also install:
 
npm i babel-jest ts-jest typescript @types/jest

Create a babel configuration file with the preset
//babel.config.js
```
module.exports = {presets: ['@babel/preset-env']}
```

Make sure you have a jest.config.js file with the following configuration:
```
module.exports = {
    preset: 'ts-jest',
    testEnvironment: 'node',
    testTimeout: 30000,
    transform: {
      '^.+\\.(ts|tsx)?$': 'ts-jest',
      "^.+\\.(js|jsx)$": "babel-jest",
    }
  };
```