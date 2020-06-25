<p align="center">
  <img src="https://cdn.rawgit.com/walterradduso/electron-express-react-webpack-boilerplate/master/docs/images/electron-express-react-webpack-boilerplate.png" width="135" align="center">
  <br>
  <br>
</p>

<p align="center">
  <a href="https://david-dm.org/walterradduso/electron-express-react-webpack-boilerplate">
    <img alt="Dependency Status" src="https://david-dm.org/walterradduso/electron-react-webpack-boilerplate.svg?style=flat">
  </a>
  <a href="https://david-dm.org/walterradduso/electron-express-react-webpack-boilerplate?type=dev">
    <img alt="devDependency Status" src="https://david-dm.org/walterradduso/electron-react-webpack-boilerplate/dev-status.svg?style=flat">
  </a>
  <a href="http://opensource.org/licenses/MIT">
    <img alt="MIT License" src="https://img.shields.io/npm/l/express.svg">
  </a>
  <a href="https://github.com/walterradduso/electron-express-react-webpack-boilerplate/releases">
    <img alt="Current release" src="https://img.shields.io/github/release/walterradduso/electron-react-webpack-boilerplate.svg">
  </a>
</p>

<p align="center">
  <a href="https://paypal.me/walterradduso" rel="nofollow">
    <img src="https://img.shields.io/badge/Paypal-Donate-%2300457C.svg?logo=paypal&style=flat" alt="Paypal" data-canonical-src="https://img.shields.io/badge/Paypal-Donate-%2300457C.svg?logo=buy-me-a-coffee&style=flat" style="max-width:100%;">
  </a>
  <a href="https://www.buymeacoffee.com/walterradduso" rel="nofollow">
    <img src="https://img.shields.io/badge/Coffee-Donate-%23FF813F.svg?logo=buy-me-a-coffee&style=flat" alt="buymeacoffee" data-canonical-src="https://img.shields.io/badge/Coffee-Donate-%23FF813F.svg?logo=buy-me-a-coffee&style=flat" style="max-width:100%;">
  </a>
</p>

## Minimal Electron, Express, React and Webpack boilerplate

This is an update of https://github.com/alexdevero/electron-react-webpack-boilerplate.

Minimal Electron, Express, React and Webpack boilerplate to help you get started with building your next app.

### Table of contents

* [Install](#install)
* [Configuration](#configuration)
* [Usage](#usage)
* [Change app title](#change-app-title)
* [Generate packages](#generate-packages)

### Install

#### Clone this repo

```
git clone git@github.com:WalterRadduso/electron-express-react-boilerplate.git
```

#### Install dependencies

```
yarn
```
or
```
npm install
```

### Configuration

#### Server Port

Copy the example environment variable.

```
cp .env.example .env
```

Now you are able to change the port.

### Usage

#### Run in dev

```
yarn start-all
```
or
```
npm run start-all
```

#### Run in prod

```
yarn prod
```
or
```
npm run prod
```

#### Build the app

```
yarn build
```
or
```
npm run build
```

### Change app title

This boilerplate uses [HTML Webpack Plugin](https://github.com/jantimon/html-webpack-plugin#options) to generate the HTML file of the app. Changing app title is possible only through webpack configs, `webpack.build.config.js` and `webpack.dev.config.js`. App title can be changed by adding objects of options.

In `webpack.build.config.js`:

```JavaScript
plugins: [
  new HtmlWebpackPlugin({title: 'New app title'}),// Add this (line 41)
  new MiniCssExtractPlugin({
    // Options similar to the same options in webpackOptions.output
    // both options are optional
    filename: 'bundle.css',
    chunkFilename: '[id].css'
  }),
  new webpack.DefinePlugin({
    'process.env.NODE_ENV': JSON.stringify('production')
  }),
  new BabiliPlugin()
]
```

In `webpack.dev.config.js`:

```JavaScript
plugins: [
  new HtmlWebpackPlugin({title: 'New app title '}),// Add this (line 36)
  new webpack.DefinePlugin({
    'process.env.NODE_ENV': JSON.stringify('development')
  })
]
```

### Generate packages

#### Files needed

You are able to add the files/folders that you need in your package.

In `package.json` you have to add/remove the files that you need in your own project.

```json
{
  "build": {
    "files": [
      "dist",
      "electron.js",
      "node_modules",
      "package.json",
      "server.js",
      "src",
      "splash"
    ]
  }
}
```

#### MacOS

```
yarn package-mac
```
or
```
npm run package-mac
```

#### Windows

```
yarn package-win
```
or
```
npm run package-win
```

#### Linux

```
yarn package-linux
```
or
```
npm run package-linux
```
