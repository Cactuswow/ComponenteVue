<script setup>

const Mensaje = function() {

    alert("Curioso");

}

const borrartarjeta = function(indice) {

    emit('borrartarjeta', indice)

}

const emit = defineEmits(['borrartarjeta'])

const props = defineProps(
    {
      name: {
        type: String,
        default: 'no name'
      },
      Desc: {
        type: String,
        default: 'no Desc'
      },
      indice: {
        type: Number
      }
    }
  )

</script>

<template>

    <div class="Card flex flex-col items-center bg-[#ededed] w-[350px] mx-auto p-5 gap-5 rounded-xl transition-[1s] hover:shadow-xl relative mt-10">

        <span @click="Mensaje" class="imageProfile w-[300px] rounded-lg overflow-hidden cursor-pointer">
            <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bf/Big_Floppa_and_Justin_2_%28cropped%29.jpg/1127px-Big_Floppa_and_Justin_2_%28cropped%29.jpg">
        </span>

        <div class="info text-center">

            <h1 class="text-[30px]">{{ props.name }}</h1>
            <p>{{ props.Desc }}</p>

        </div>

        <span class="absolute top-3 right-3 bg-[#bbb] text-[25px] w-[50px] h-[50px] text-center rounded-full flex justify-center items-center cursor-pointer" @click="borrartarjeta(props.indice)">X</span>

    </div>

</template>