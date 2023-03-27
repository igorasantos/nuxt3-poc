<template>
  <p>hello</p>
  <p>param ('hash'): {{ route.params.hash }}</p>
  <p>local state (reactive): {{ stateObj.count }}</p>
  <p>local state (ref str): {{ dataTest }}</p>
  <button @click="add">
    Add
  </button>
</template>

<script lang="ts" setup>
import { reactive, ref } from 'vue';
import type { Ref } from 'vue';

interface IStateObj {
  count: number
}

// Route Validation
definePageMeta({
  validate: async (route): Promise<boolean> => {
    const valueToCheck: string = route.params.hash.toString();
    // verifica tamanho da route param p/ ser exatamente 20 dígitos e/ou letras
    return /^[\d\w]{20}$/.test(valueToCheck);
  }
})

useHead({
  title: 'Tops - Docs',  
})

const route = useRoute();
const stateObj: IStateObj = reactive({count: 0})
const dataTest: Ref<string> = ref('local state')

function add() {
  stateObj.count++;
}

</script>
