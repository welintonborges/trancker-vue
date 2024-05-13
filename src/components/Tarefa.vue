<script lang="ts">
import Cronometro from "@/components/Cronometro.vue";
import {defineComponent, PropType} from "vue";
import ITarefa from "../interfaces/ITarefas";
export default defineComponent({
  name: "Tarefa",
  components:{
    Cronometro,
  },
  props:{
    tarefa:{
      type: Object as PropType<ITarefa>,
      required: true
    }
  }
})
</script>

<template>
<!--  <pre>{{tarefa}}</pre>-->
    <div class="box has-text-weight-bold">
      <div class="columns">
        <div class="column is-7">
          {{ tarefa.descrisao }}
        </div>
        <div class="columns">
          <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
        </div>
      </div>
    </div>
</template>

<style scoped>
.box{
  background: #FAF0CA;
}
</style>