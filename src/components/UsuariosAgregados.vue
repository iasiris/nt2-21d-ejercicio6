<template lang="html">
  <section class="src-componentes-usuariosagregados">
    <div class="jumbotron">
      <h2>Ejercicio 2</h2>
      <hr />
      <div class="jumbotron">
        <div v-if="usuarios.length" class="table-responsive">
          <table class="table table-dark">
            <tr>
              <th v-for="(col, index) in getCols" :key="index">{{ col }}</th>
            </tr>

            <tr v-for="(info, index) in usuarios" :key="index">
              <td v-for="(col, index) in getCols" :key="index">
                {{ info[col] }}
              </td>
            </tr>
          </table>
        </div>
      </div>
    </div>
  </section>
</template>

<script lang="js">

  export default  {
    name: 'src-components-usuariosagregados',
    props: [],
    mounted () {
      this.getUsuarios()
    },
    data () {
      return {
        url:'https://60aac34c66f1d000177732f0.mockapi.io/usuarios-TP6/',
        usuarios : []
      }
    },
    methods: {
      /*axios then catch*/
      getUsuarios(){
        this.axios(this.url)
          .then(respuesta => {
            console.log('AXIOS GET USUARIOS', respuesta.data)
            this.usuarios = respuesta.data
          })
          .catch(error => console.error(error))
      },

    },
    computed: {
      getCols() {
        return Object.keys(this.usuarios[0])
      }
    }
}
</script>

<style scoped lang="css">
.src-components-usuariosagregados {
}
</style>
