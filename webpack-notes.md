# Webpack Study Notes

1. Make a new NPM project 
2. Write the JS
3. Include and configure Webpack
4. Run webpack

- npm init
- create src
- index.js
- sum.js

# Babel

- babel-loader: Tells babel how to work with webpack
- babel-core: Parser
- babel-preset-env: Rules to tell babel how to convert ES6 to ES5

npm install --save-dev babel-loader babel-core babel-preset-env

add babel to webpack.config.js as follows:
	```
		module: {
			rules: [
				{
					use: 'babel-loader',
					test: /\.js$/  // regex to choose only js files to convert in babel
				}
			]
		}
	```

Add babel-preset-env in an array to "presets" by creating a new file called .babelrc

**
need to include react preset in .babelrc to parse JSX

-- included

https://stackoverflow.com/questions/26566317/invariant-violation-registercomponent-target-container-is-not-a-dom-elem

Always place bundle.js at the bottom of the body