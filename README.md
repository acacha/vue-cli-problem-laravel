# Module build failed (from ./node_modules/eslint-loader/index.js): Error: No ESLint configuration found.

See https://github.com/vuejs/vue-cli/issues/2539

File **vue.config.js**

```javascript
const path = require('path');
module.exports = {
  chainWebpack: config => {
    config.module
      .rule('eslint')
      .use('eslint-loader')
      .tap(options => {
        options.configFile = path.resolve(__dirname, ".eslintrc.js");
        return options;
      })
  },
  css: {
    loaderOptions: {
      postcss: {
        config:{
          path:__dirname
        }
      }
    }
  }
}
```
