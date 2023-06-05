<script setup>
  // import CardComponent from './components/CardComponent.vue';
  import CardComponent from '@/components/CardComponent.vue';
  import { ref } from 'vue';
  const users = ref([
  { 
    name: 'Floopa',
    Desc: 'Waos'
  },
  {
    name: 'Sus',
    Desc: 'Waos*2'
  }])

  const borrartarjeta = function(indice) {

    users.value.splice(indice, 1)

  }

  let name = ref("");
  let Desc = ref("");


  const Agregar = function() {

    let Extra = {
      name: name.value,
      Desc: Desc.value
    }

    users.value.push(Extra)
    name.value = "";
    Desc.value = "";

  }

</script>

<template>

  <div class="Card-Wrap flex w-[900px] gap-5 flex-wrap mx-auto">

    <CardComponent v-for="(user, indice) in users" :key="indice" :name="user.name" :Desc = "user.Desc" :indice  = "indice" @borrartarjeta="borrartarjeta"></CardComponent>

  </div>

  <div class="Leer flex flex-col gap-5 mx-auto w-[900px] items-center justify-center mt-10 bg-[#ededed] p-5 rounded-lg">

    <label for="">Nombre</label>
    <input type="text" class="px-[10px] outline-none" v-model="name">
    <label for="">Descripción</label>
    <input type="text" class="px-[10px] outline-none" v-model="Desc">

    <button @click="Agregar" class="border-2 px-[70px] py-[10px] bg-white rounded-lg">subir</button>
  </div>

</template>

<style scoped>

</style>
