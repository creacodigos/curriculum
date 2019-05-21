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
