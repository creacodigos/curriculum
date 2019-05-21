<template>
  <div class="two">
    <section aria-labelledby="Perfil">
      <article>
        <h4 class="titulo">
          <i class="fas fa-user-circle"></i>Perfil
        </h4>
        <div>
            <pre v-html="this.$options.filters.crearEnlaces(datos.perfil)">
            </pre>
        </div>
      </article>
    </section>
    <section aria-labelledby="Experiencia Laboral">
      <article>
        <h4 class="titulo">
          <i class="fas fa-briefcase"></i> Experiencia Laboral
        </h4>
        <div>
          <ul>
              <cr-listado v-for="(e,i) in datos.experiencia"
                            :key="i" 
                            :numid="i" 
                            :dato="e">
                </cr-listado>
          </ul>
        </div>
      </article>
    </section>
    <section aria-labelledby="tecnologias empleadas">
      <article>
        <h4 class="titulo">
          <i class="fas fa-laptop-code"></i>Tecnologías Empleadas
        </h4>
        <div>
          <p>
            {{ datos.tecnologias }}
          </p>
        </div>
      </article>
    </section>                   
  </div>
</template>

<script>
import Listado from './Listado';
export default {
	name: 'Columna2',
    components: {
        'cr-listado': Listado
    },
    data() {
        return this.$parent.$parent
    }
    ,
    filters: {
      crearEnlaces : texto => {
        
        // Funcion que reemplaza los enlaces planos por enlaces html function url_replace(text) {     
        // Reemplazamos url que inicie con http://, https://, ftp://, file://     

        let exp = /((http:|https:|ftp:|file:)[^\s]+[\w])/g; 
        let texto2 = texto.replace(exp, '<a href="$1" target="_blank" rel="nofollow">$1</a>');  
         //texto2 = (texto2 + '').replace(/([^>\r\n]?)(\r\n|\n\r|\r|\n)/g, '$1 <br> $2');
        return texto2;
          
      }
    },
    methods: {
      nl2br : function(str) {
        if (typeof str === 'undefined' || str === null) {
            return '';
        }
        return (str + '').replace(/([^>\r\n]?)(\r\n|\n\r|\r|\n)/g, '$1 <br> $2');
      }
    }
}
</script>
