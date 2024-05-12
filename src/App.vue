<script >

import {defineComponent} from "vue";
import BarraLateral from "@/components/BarraLateral.vue";
import Formulario  from "@/components/Formulario.vue";
export default defineComponent({
  components: {Formulario, BarraLateral}
})
</script>

<template>
      <main class="columns is-gapless is-multiline">
        <div class="column is-one-quarter">
          <BarraLateral/>
        </div>
        <div class="column is-three-quarter">
        <formulario/>
        </div>
      </main>
</template>
