# Proyecto Vue.JS
## Curriculum vitae con framework Javascrit

Creando página con curriculum para proyecto vue.JS

URL: https://github.com/vuejs/vuejs.org/blob/master/src/v2/cookbook/using-axios-to-consume-apis.md
JSON DATA: https://creacodigos.com/data/data.json

## Axios ##

Info JSON importada con AXIOS

App.vue:

  ```js

import axios from 'axios'

export default {
	...
  data() {
    return {
      datos: []
    };
  },
  methods: {
    leerDatos(){
      axios.get('https://creacodigos.com/data/data.json')
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

## Service Worker ##
