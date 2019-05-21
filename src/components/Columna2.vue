<template>
  <div class="two">
    <section aria-labelledby="Perfil">
      <article>
        <h4 class="titulo">
          <i class="fas fa-user-circle"></i>Perfil
        </h4>
        <div>
            <pre>
                {{ datos.perfil }}
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
}
</script>