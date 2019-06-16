# :pencil: Curriculum vitae con framework Javascrit

**:rocket: Creando página con curriculum para proyecto vue.JS**

:mag: Axios Vue: https://github.com/vuejs/vuejs.org/blob/master/src/v2/cookbook/using-axios-to-consume-apis.md

:page_facing_up: JSON DATA: https://raw.githubusercontent.com/creacodigos/curriculum/master/src/assets/data/data.json

:page_facing_up: JSON DATA: https://creacodigos.com/data/data.json

:globe_with_meridians: https://creacodigos.com

## Axios ##

Info JSON importada con AXIOS

App.vue:

  ```js

import axios from 'axios'

export default {
	...
  data() {
    return {
      datos: [],
      api : 'https://creacodigos.com/data/data.json'
    };
  },
  methods: {
    leerDatos(){
      axios.get(this.api)
        .then(response => {
          console.log(response.data);
          this.datos = response.data;
        })
        .catch(function(error) {
          console.log('ERROR: '+ error);
        });
      }
    },
    created: function() {
      this.leerDatos();
    }
};
...
  ```

Componente.vue:

```js
export default {
  ...
    data() {
        return this.$parent
    }
...
}
```

## Alternativa nativa FETCH ##

```js
methods: {
    leerDatos() {
      fetch(this.api)
          .then(response => response.json())
          .then(data => {
            console.log(data)
            this.datos = data
          })
          .catch(error => {
            console.error('ERROR: '+ error)
          });
    }
  }
```

## Usando Filtros en Webcomponentes

`this.$options.filters.nombreFiltro(parámetros)`

```js
<pre v-html="this.$options.filters.crearEnlaces(datos.perfil)">
</pre>

...
    filters: {
      crearEnlaces : texto => {
        
        // Funcion que reemplaza los enlaces planos por enlaces html function url_replace(text) {     
        // Reemplazamos url que inicie con http://, https://, ftp://, file://     

        let exp = /((http:|https:|ftp:|file:)[^\s]+[\w])/g; 
        let texto2 = texto.replace(exp, '<a href="$1" target="_blank" rel="nofollow">$1</a>');  
        return texto2;
          
      }
    },
...
```

## Usando Métodos en Webcomponentes

`this.$options.methods.nombreMétodo(parámetros)`

```js
<pre v-html="this.$options.methods.nl2br(datos.perfil)">
</pre>

...
methods: {
      nl2br : function(str) {
        if (typeof str === 'undefined' || str === null) {
            return '';
        }
        return (str + '').replace(/([^>\r\n]?)(\r\n|\n\r|\r|\n)/g, '$1 <br> $2');
      }
    }
...
```

## Usando Filtro y Métodos en Webcomponente

`this.$options.filters.nombreFiltro(this.$options.methods.nombreMétodo(parámetro))`

## Service Worker
https://dev.to/sarmis/single-page-progressive-web-applications-with-vue-js-2op8

`<link rel="manifest" href="./manifest.webmanifest">`

```js
<script src="./index.js"></script>
<script>
    if ('serviceWorker' in navigator) {
        window.addEventListener('load', () => {
            navigator.serviceWorker.register('/service-worker.js');
        });
    }            
</script>
```

**Imprtante extensión `.webmanifest` para compatibilidad coon PARCEL

`./src/web/service-worker.js`
Se define que use primero la estrategia de red para permitir uso offline de la caché.

```js
console.log("service-worker.js")
// import service worker script
importScripts('https://storage.googleapis.com/workbox-cdn/releases/4.2.0/workbox-sw.js');

// Network First
[ 
    '/$',  // Index 
    '/*',  // Anything in the same host
    '.+/*' // Anything in any host 
]
.forEach(mask => {
    workbox.routing.registerRoute(
        new RegExp(mask),
        new workbox.strategies.NetworkFirst( { cacheName: 'dynamic' } ) 
    );
});
```

## Analytics en index.html

```js
<!-- Global site tag (gtag.js) - Google Analytics -->
  <script async src="https://www.googletagmanager.com/gtag/js?id=UA-XXXXXXXXX-1"></script>
  <script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());  
    gtag('config', 'UA-XXXXXXXXX-1');
  </script>
```

# :see_no_evil:
