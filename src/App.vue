<script lang="ts">

import {defineComponent} from "vue";
import BarraLateral from "@/components/BarraLateral.vue";
import Formulario  from "@/components/Formulario.vue";
import Tarefa from "@/components/Tarefa.vue";
import ITarefas from "./interfaces/ITarefas.js";
import Box from "@/components/Box.vue";

export default defineComponent({
  components: {
    Box,
    Tarefa,
    Formulario,
    BarraLateral
  },
  data(){
    return{
      tarefas: [] as ITarefas[],
    }
  },
  computed: {
    listaEstaVazia(): boolean{
      return this.tarefas.length == 0
    }
  },
  methods:{
    salvarTarefa(tarefa: ITarefas[]): void{
      this.tarefas.push(tarefa);
    }
  }
})
</script>

<template>
      <main class="columns is-gapless is-multiline">
        <div class="column is-one-quarter">
          <BarraLateral/>
        </div>
        <div class="column is-three-quarter">
        <formulario @aoSalvarTarefa="salvarTarefa"/>
       <!-- Lista de tarefa-->
          <div class="lista">
            <Tarefa v-for="(tarefa, index ) in tarefas"  :key="index" :tarefa="tarefa"/>
          </div>
          <Box v-if="listaEstaVazia">
            Você não está muito produtivo hoje :(
          </Box>
        </div>
      </main>
</template>

<style>
.lista{
  padding:  1.25rem;
}
</style>
