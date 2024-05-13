<script  lang="ts">
import {defineComponent} from "vue";
import Temporizador from "@/components/Temporizador.vue";
export default defineComponent({
  name: "Formulario",
  emits: ["aoSalvarTarefa"],
  components: {
    Temporizador
  },
 data() {
     return{
       descrisao: ''
     }
 },
  methods:{
    finalizarTarefas(tempoDecorrido: number): void {
      this.$emit('aoSalvarTarefa', {
        duracaoEmSegundos: tempoDecorrido,
        descrisao: this.descrisao
       })
      this.descrisao ='';
    }
  }
})
</script>

<template>
  <div class="box">
    <div class="columns">
      <div class="column is-8" role="form" aria-labelledby="formulario pra criação de npvas tarefas">
        <input type="text" class="input" placeholder="Qual tarefa você deseja iniciar" v-model="descrisao"/>
      </div>
      <div class="column">
        <temporizador @aoTemporizadorFinalizado="finalizarTarefas"/>
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>