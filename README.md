# nuxt-vuetify-material-design-icons-iconfont
Nuxt.js Vuetify Material Design Icons

## initialize

```bash
npm i -g create-nuxt-app
create-nuxt-app my-app # choose Vuetify.js, axios, dotenv, pwa
cd my-app/
npm i -E  material-design-icons-iconfont
npm i -ED @nuxtjs/proxy css-loader svg-loader nuxt-webfontloader vue vuex axios
```

## configure

_nuxt.config.js_

```js
export default {
  // ...skip other...
  css: [
    'material-design-icons-iconfont/dist/material-design-icons.css',
  ],
  modules: [
    'nuxt-webfontloader',
  ],
  webfontloader: {
    google: {
      // https://fonts.googleapis.com/css?family=Roboto:100,300,400,500,700,900&display=swap
      families: ['Roboto:100,300,400,500,700,900&display=swap'],
    }
  },
  vuetify: {
    icons: {
      iconfont: 'mdiSvg' // || 'md' || 'fa' || 'fa4' || 'mdi', // default - only for display purposes
    },
  },
};
```

_layouts/default.vue_

```vue
<template>
  <v-app dark>
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; 2019</span>
    </v-footer>
  </v-app>
</template>
```

_pages/index.vue_

```vue
<template>
  <v-layout>
    <v-flex class="text-center">
      <h1>Hello World!</h1>
      <v-btn @click="getMessageAction">
        <v-icon>email</v-icon>
      </v-btn>
    </v-flex>
  </v-layout>
</template>
```
