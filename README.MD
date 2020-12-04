# Root app

Aplicación base para cargar múltiples aplicaciones spa

[Single SPA Docs](https://single-spa.js.org/docs/configuration)

Es necesario clonar y correr estas dos apps antes

* [App React](https://github.com/britez/react-single-spa-application)
* [App Angular](https://github.com/britez/angular-single-spa-application)

### Para correr esta app...

```
npm install
npm run start
```

### Como agregar otra app?

Agregar import en index.ejs

```
<script type="systemjs-importmap">
      {
        "imports": {
          "react": "https://cdn.jsdelivr.net/npm/react@16.13.1/umd/react.production.min.js",
          "react-dom": "https://cdn.jsdelivr.net/npm/react-dom@16.13.1/umd/react-dom.production.min.js",
          "app1": "http://localhost:4201/main.js",
          "@redbee/Dogs": "http://localhost:8080/redbee-Dogs.js",
          "@redbee/root-config": "http://localhost:9000/redbee-root-config.js",
          "single-spa": "https://cdnjs.cloudflare.com/ajax/libs/single-spa/5.5.0/system/single-spa.min.js",
          "single-spa-layout": "https://unpkg.com/single-spa-layout@1.0.0-beta.2/dist/system/single-spa-layout.min.js"
        }
      }
</script>
```

Cambiar Agregar en router

```
<route path="/react">
  <application name="@redbee/Dogs"></application>
</route>
```

