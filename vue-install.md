# Vue install

Vue 설치

```text
npm install vue
cd node_module/vue
npm install
npm run build
```

```javascript
/root/
- src
    - assets
    - components
    - routes
        - index.js
        - linkgroup.js
    - store
    - views
    - App.vue
    - main.js
- public
    - index.html
- .gitignore
- README.md
- babel.config.js
- package.json
- package-lock.json
- vue.config.js
- yarn.lock
```

index html

```markup
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
    <link rel="icon" href="<%= BASE_URL %>favicon.ico">
    <title>vue-news</title>
  </head>
  <body>
    <noscript>
      <strong>
        We're sorry but vue-news doesn't work properly without JavaScript enabled.
        Please enable it to continue.
      </strong>
    </noscript>
    <div id="app"></div>
    <!-- built files will be auto injected -->
  </body>
</html>
```

App vue

```javascript
<template>
  <div id="app">
    <sample-div />
  </div>
</template>

<script>
import SampleDiv from '/path/to/SampleDiv.vue'

export default {
  name: 'app',
  components: {
    SampleDiv
  }
}
</script>

<style>
</style>
```

main js

```javascript
import Vue from 'vue';
import App from './App.vue';
import { router } from './routes/index.js';

Vue.config.productionTip = false

new Vue({
  render: h => h(App),
  router,
}).$mount('#app')
```

routes js

```javascript
import Vue from 'vue'
import VueRouter from 'vue-router'
import NewsView from '../views/NewsView.vue';
import AskView from '../views/AskView.vue';
import JobsView from '../views/JobsView.vue';
import UserView from '../views/UserView.vue';
import ItemView from '../views/ItemView.vue';

Vue.use(VueRouter);

export const router = new VueRouter({
  mode: 'history',
  routes: [{
    path: '/',
    redirect: '/news'
  },
  {
    // path: url 주소
    path: '/news',
    // url 주소로 갔을 때 표시될 컴포넌트
    component: NewsView,
  },
  ]
})
```

babel config js

```javascript
module.exports = {
  presets: [
    '@vue/app'
  ]
}
```

vue config js

```javascript
module.exports = {
  lintOnSave: false
}
```



