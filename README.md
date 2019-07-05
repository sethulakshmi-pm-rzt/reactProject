# reactProject
reactProject

#Steps to run
`
npm install
npm run build
npm start
`


React -- setup

Create repository from github
Clone it to the local machine and open in the webstorm
Create .gitignore file (when doing git push, ignore those files.)
node_modules/*
__build__/*
dist/*
.idea/*

.4 to create the package.json file we need to run the below code in terminal
	npm init -y
5. To get the dependencies
npm i react react-dom --save

Now u will get the dependencies in the package.json

6. Webpack
	npm install --save-dev webpack webpack-dev-server webpack-cli

Now u will get the dev- dependencies in the package.json

7. Write start command

"scripts": {
 "start": "webpack-dev-server --mode development",
 "test": "echo \"Error: no test specified\" && exit 1",
 "build": "webpack --mode production"
},


8. “touch” command to create the file
	Touch index.html
<! Then click tab will generate the html code


<!doctype html>
<html lang='en'>
<head>
  <meta charset='UTF-8'>
  <meta name='viewport'
        content='width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0'>
  <meta http-equiv='X-UA-Compatible' content='ie=edge'>
  <title>Document</title>
</head>
<body>
<div id='root'>

</div>
Its Me...Sethu..!!!

<script src='./dist/bundle.js'></script>
</body>
</html>


9. mkdir src && cd src && touch index.js

Creates the file

10. In that index.js create on class

import React, { Component } from 'react';
import ReactDOM from 'react-dom';

class App extends Component {
 render() {
   return (<div>HI...!!!</div>);
 }
}

App.propTypes = {};


App.defaultProps = {};

ReactDOM.render(<App />, document.getElementById('root'));


11. Run
Babel -- convert all jsx and ES6 to ES5

npm install --save-dev @babel/core @babel/preset-env \@babel/preset-react babel-loader

12. Create Configuration
Create a file webpack.config.js


const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');

module.exports = {
 entry: './src/index.js',
 output: {
   path: path.resolve(__dirname, 'build'), // change this
   publicPath: '/',
   filename: 'bundle.js'
 },
 devServer: {
   contentBase: "./build",
 },
 module: {
   rules: [
     {
       test: /\.(js|jsx)$/,
       exclude: /node_modules/,
       use: ['babel-loader']
     }
   ]
 },
 plugins: [
   new HtmlWebpackPlugin({
     template: path.resolve('./index.html')
   })
 ],
};




13. Create babelrc file in the root

touch .babelrc

Add these commands there

{
"presets": [
"@babel/preset-env",
"@babel/preset-react"
]
}

14. npm install html-webpack-plugin -D

15. https://www.netlify.com/

16. https://medium.com/free-code-camp/how-to-set-up-deploy-your-react-app-from-scratch-using-webpack-and-babel-a669891033d4

17.

