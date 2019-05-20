# Proyecto Vue.JS
## Curriculum vitae con framework Javascrit

Creando página con curriculum para proyecto vue.JS

URL: http://creacodigos.com

## Axios ##

Info JSON importada con AXIOS

  ```js
  código js

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
      axios.get('http://creacodigos.com/data/data.json')
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
      // lerr Datos
      this.leerDatos();
    }
};
...
  ```

## Service Worker ##
