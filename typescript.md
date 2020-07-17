# TypeScript Note

## TypeScript Set up (Node)

## Installing TypeScript Dependencies
1. Install typescript by running a command below.
   ```shell
   $ npm install typescript --save--dev
   ```
2. **(Optional But Recommended)** Install eslint by running a command below.
   ```shell
   $ npm install eslint --save--dev
   ```
   1. Initialize a configuration file of eslint by running a command below.
      ```
      $ npx eslint --init
      ```
3. Initialize a configuration file of TypeScript by running a command below.
   ```shell
   $ tsc --init
   ```
   
   ###### tsconfig.json
   ```json
   {
     "compilerOptions": {
       "module": "commonjs",
       "esModuleInterop": true,
       "target": "es6",
       "moduleResolution": "node",
       "sourceMap": true,
       "outDir": "dist"
      },
     "lib": ["es2015"]
   }
   ```
