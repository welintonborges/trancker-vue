<script lang="ts">
import Cronometro from "@/components/Cronometro.vue";
import {defineComponent, PropType} from "vue";
import ITarefa from "../interfaces/ITarefas";
import Box from "@/components/Box.vue";
export default defineComponent({
  name: "Tarefa",
  components:{
    Box,
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
    <Box>
      <div class="columns">
        <div class="column is-7">
          {{ tarefa.descrisao || 'Tarefa sem decriçao' }}
        </div>
        <div class="columns">
          <Cronometro :tempoEmSegundos="tarefa.duracaoEmSegundos"/>
        </div>
      </div>
    </Box>
</template>

<style scoped>

</style>