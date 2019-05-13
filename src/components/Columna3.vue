<template>
  <div class="three">
    <section aria-labelledby="Formación Académica">
      <article>
        <h4 class="titulo">
          <i class="fas fa-user-graduate"></i>Formación Académica
        </h4>
        <div>
          <ul>
              <cr-listado v-for="(e,i) in datos.formacion"
                            :key="i" 
                            :numid="i" 
                            :dato="e">
                </cr-listado>
          </ul>
        </div>
      </article>
    </section>

    <section aria-labelledby="Cursos">
      <article>
        <h4 class="titulo">
          <i class="fas fa-chalkboard-teacher"></i>Cursos
        </h4>
        <div>
          <ul>
            <cr-listado v-for="(e,i) in datos.cursos"
                        :key="i" 
                        :numid="i" 
                        :dato="e">
            </cr-listado>
          </ul>
        </div>
      </article>
    </section>
 
    <section aria-labelledby="aficiones">
      <article>
        <h4 class="titulo">
          <i class="fas fa-guitar"></i>Aficiones
        </h4>
        <div>
          <p>
            {{ datos.aficiones }}
          </p>
        </div>
      </article>
    </section>             
  </div>
</template>

<script>
import Listado from './Listado';
export default {
	name: 'Columna3',
    components: {
        'cr-listado': Listado
    },
    data() {
        return {
            datos: this.$parent.$parent.datos
        }
    }
}
</script>
