# Custom Grid
Custom Grid is customise version of bootstrap grid where this is available with Multiple Grid column, multiple gutter width for respective multiple breakpoints.

# Getting Started
Default configurations are 3 breakpoints: 
xs - 4  columns and gutter width 10px
sm - 6  columns and gutter width 20px
md - 12 columns and gutter width 30px

If you want to use default configuration provided here. 
Run `npm i custom-grid` to install this package.
Create two files in src folder style.scss and index.js
Add path of node modules custom-grid scss file in your style.scss like `@import "~custom-grid/scss/bootstrap-grid";` 
Include style.scss path in index.js file like `import './style.scss';`

Below is the guidance for webpack configuration:
```
const path = require('path');
const miniCssExtractPlugin = require('mini-css-extract-plugin');

module.exports = {
  mode: "development",
  entry: "./src/index.js",
  output: {
    path: path.join(__dirname, "/dist"),
    filename: "bundle.js"
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: ['babel-loader'],
      },
      {
        test: /\.(sa|sc|c)ss$/,
        //exclude: /(node_modules)/,
        use: [miniCssExtractPlugin.loader,'css-loader', 'sass-loader'],
      }
    ]
  },
  plugins: [
		new miniCssExtractPlugin({
			filename: 'style.css'
		})
	]
};

```
OR

You can download the folder and update the variables value as per individual requirement.

# Usage of function
Example to call sass function to create container or row or columns with respect to different breakpoints 

```
.newfluidcontainer {
  @include make-container();
}
.newcontainer {
  @include make-container();
  @include make-container-max-widths();
}
.newrow {
  @include make-row();
}
.newclass {
  @include make-col-ready();
  @include make-column(2, xs);
  @include make-col-offset(1, 4);
  @include media-breakpoint-down(xs) {
      margin-top: 32px;
  }
  @include media-breakpoint-up(sm) {
      @include make-column(4, sm);
      @include make-col-offset(0, 8);
  }
}
```