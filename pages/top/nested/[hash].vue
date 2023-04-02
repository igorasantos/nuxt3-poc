<template>
  <div>
    <p>hello</p>
    <p>param ('hash'): {{ route.params.hash }}</p>
    <p>local state (reactive): {{ stateObj.count }}</p>
    <p>local state (ref str): {{ dataTest }}</p>
    <button @click="add">
      Add
    </button>
    <h2 v-if="!fetchedData">Data loading</h2>
    <div v-else>
      <h2>Data fetched</h2>
      <ul>
        <li v-for="(value, key) in fetchedData" :key="key">{{key}}: {{ value }}</li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts" setup>
import { reactive, ref } from 'vue';
import type { Ref } from 'vue';

interface IStateObj {
  count: number
}

interface IDataResponse {
  firstProp: number,
  secondProp: string,
  dataName: string
}

// Route Validation
definePageMeta({
  validate: async (route): Promise<boolean> => {
    const valueToCheck: string = route.params.hash.toString();
    // verifica tamanho da route param p/ ser exatamente 20 dígitos e/ou letras
    return /^[\d\w]{20}$/.test(valueToCheck);
  },
  layout: 'purple'
})

useHead({
  title: 'Tops - Docs',  
})

const route = useRoute();
const stateObj: IStateObj = reactive({count: 0})
const dataTest: Ref<string> = ref('local state')
// const { pending, data: backendData } = useLazyFetch<IDataResponse>(`baseUrl/${route.params.hash}`)
const { default: fetchedData } : { default: IDataResponse } = await import(`../../../api/mockedData/${route.params.hash}.json`);

function add() {
  stateObj.count++;
}

</script>
