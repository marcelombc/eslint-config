# eslint-config

My own eslint configurations.


## Installation

`$ npm install --save-dev satazor@eslint-config eslint@^1.10.3`

Additional dependencies that need to be installed per addon:

react addon: `$ npm install --save-dev eslint-plugin-react@^3.13.0`

This plugin was tested with these dependencies version ranges. Use other versions at your own risk. I will try to keep this project up to date with the changes of `eslint` and the plugins used here.


## Usage

First you need to choose the **base** configuration to use:

- `es5` - The configuration to be used in ECMAScript 5 based projects
- `es6` - The configuration to be used in ECMAScript 6 based projects

Then enhance it with one or more **addons**:

- `browser` - If you are going to develop code for the browser (having in mind IE >= 9)
- `node` - If you are going to develop code for NodeJS
- `react` - If you are going to use React and JSX (requires `eslint-plugin-react`)

Alternatively, you can make your own configuration by using the set of **rules** individually. If you're interested in doing that, you can check `es5.js` to see how it is done.

Simply create a `.eslintrc.json` file with your desired base configuration and addons. Feel free to override rules you won't agree with. You can look at some examples bellow.


### Examples

Cutting edge ES6 in the browser, using react:

```json
{
    "root": true,
    "extends": [
        "@satazor/es6",
        "@satazor/addons/browser",
        "@satazor/addons/react"
    ]
}
```

Cutting edge ES6 in NodeJS:

```json
{
    "root": true,
    "extends": [
        "@satazor/es5",
        "@satazor/addons/browser"
    ]
}
```

Good old ES5 in NodeJS:

```json
{
    "root": true,
    "extends": [
        "@satazor/es6",
        "@satazor/addons/node"
    ]
}
```

Note that by setting `root` to true, we ensure that no ancestor configuration is used which also improves `eslint` performance because no more file lookups need to be done.


## File name convention

If your file exports a single class, your filename should be exactly the name of the class. For other cases, the name of the file should be the same as the default exports (prefer camelCase).


## License

[MIT License](http://opensource.org/licenses/MIT)
