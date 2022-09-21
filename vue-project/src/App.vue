<script >
  import axios from 'axios'
 export default{
  data(){
    return{
    cep: "",
    endereco: {}
    };
  },
  methods: {
    async buscar(){
      const url = `https://viacep.com.br/ws/${this.cep}/json/`;
      const res =  await axios.get (url);
      this.endereco = res.data;
    }
  }
 }
</script>

<template>
  <h1 class="flex justify-center text-4xl">Teste</h1>
  <div class="flex justify-center p-10">
  <form class="flex items-center " @submit.prevent="buscar">
    <label for="simple-search" class="sr-only">Buscar</label>
    <div class="relative ">
      <div
        class="flex absolute inset-y-0 left-0 items-center pl-3 pointer-events-none"
      >
        <svg
          aria-hidden="true"
          class="w-5 h-5 text-gray-500 dark:text-gray-400"
          fill="currentColor"
          viewBox="0 0 20 20"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            d="M8 4a4 4 0 100 8 4 4 0 000-8zM2 8a6 6 0 1110.89 3.476l4.817 4.817a1 1 0 01-1.414 1.414l-4.816-4.816A6 6 0 012 8z"
            clip-rule="evenodd"
          ></path>
        </svg>
      </div>
      <input
        type="text"
        v-model="cep"
        id="simple-search"
        class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full pl-10 p-2.5 dark:bg-gray-700 dark:border-gray-600 dark:placeholder-gray-400 dark:text-white dark:focus:ring-blue-500 dark:focus:border-blue-500"
        placeholder="Digite o CEP"
        required=""
      />
    </div>
    <button
      type="submit"
      class="p-2.5 ml-2 text-sm font-medium text-white bg-blue-700 rounded-lg border border-blue-700 hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800"
    >
      <svg
        class="w-5 h-5"
        fill="none"
        stroke="currentColor"
        viewBox="0 0 24 24"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          stroke-linecap="round"
          stroke-linejoin="round"
          stroke-width="2"
          d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
        ></path>
      </svg>
      <span class="sr-only">Buscar</span>
    </button>
  </form>
</div>
<div class="flex justify-center border-2 rounded-full p-2 ">
  <form  class="end flex flex-col space-y-4">
    <label for="rua">Rua: </label>
    <input type="text" v-model="endereco.logradouro">
    <label for="rua">Numero: </label>
    <input type="text" v-model="endereco.numero">
    <label for="rua">Bairro: </label>
    <input type="text" v-model="endereco.bairro">
    <label for="rua">Cidade: </label>
    <input type="text" v-model="endereco.localidade">
    <label for="rua">UF: </label>
    <input type="text" v-model="endereco.uf">
    <label for="rua">IBGE: </label>
    <input type="text" v-model="endereco.ibge">
    <label for="rua">Gia: </label>
    <input type="text" v-model="endereco.gia">
    <label for="rua">DDD: </label>
    <input type="text" v-model="endereco.ddd">
    <label for="rua">Siafi: </label>
    <input type="text" v-model="endereco.siafi">
  </form>

</div>


</template>
<style></style>
