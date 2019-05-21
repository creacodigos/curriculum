<template>
  <div class="one">

    <section aria-labelledby="datos">
      <article id="foto">
        <div :title=`${datos.datos.nombre}`>
          <img src="../assets/img/jorge_santana.jpg" alt="Foto Jorge Santana">
        </div>
      </article>
      <article>
        <div>
          <ul>
            <li><strong><i class="fas fa-envelope"></i>EMAIL:</strong> <a :href=`mailto:${datos.datos.email}`>{{ datos.datos.email }}</a></li>
            <li><strong><i class="fas fa-baby-carriage"></i>HIJO:</strong> <a :href=`${datos.datos.hijo}` target="_blank" title="Portal de Músicos Canarios">{{ datos.datos.hijo }}</a></li>
            <li><strong><i class="fas fa-robot"></i>WEB:</strong> <a :href=`${datos.datos.url}`>{{ datos.datos.url }}</a></li>
            <li><strong><i class="fab fa-linkedin"></i>LINKEDIN:</strong> <a :href=`https://www.linkedin.com/in/${datos.datos.linkedin}/` target="_blank">{{ datos.datos.linkedin }}</a></li>
          </ul>
        </div>
      </article>
    </section>
    <section aria-labelledby="habilidades">
      <article>
        <h4 class="titulo">
          <i class="fas fa-fire"></i>habilidades
        </h4>
        <div>
          <ul>
            <cr-listado v-for="(e,i) in datos.habilidades"
                :key="i" 
                :numid="i" 
                :dato="e">
            </cr-listado>
          </ul>
        </div>
      </article>
    </section>
  </div>    
</template>

<script>
import Listado from './Listado';
export default {
    name: 'Columna1',
    components: {
        'cr-listado': Listado
    },
    data() {
        return this.$parent.$parent
    }
}
</script>
