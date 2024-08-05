<template>




 <div class="d-flex flex-row flex-wrap justify-center pa-5">


    <div v-for="item in peliculas" :key="item.id">

      <MovieCard :pelicula="item"/>

    </div>





 </div>








</template>

<script setup>

import { ref } from 'vue';
import { supabase } from '../lib/supabaseClient';
import MovieCard from '@/components/MovieCard.vue';



const peliculas = ref([])
const cargando = ref(true)




const {data} = await supabase.from('peliculas').select()
peliculas.value = data
cargando.value = false
console.log(peliculas.value)

/* async function getCountries() {
  const { data } = await supabase.from('peliculas').select()
  peliculas.value = data
}

onMounted(async () => {
  await getCountries()
  console.log(peliculas.value)
}) */




</script>
