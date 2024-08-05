<template lang="">
  <div>
    <v-card
    class="mx-auto ma-3"
    max-width="400"
  >
    <v-card-item :title="pelicula.titulo">
      <template v-slot:subtitle>
        <div class="d-flex align-center mt-1 " style="font-size: 12px">
        <v-icon
          class="me-1 pb-1"
          color="info"
          icon="mdi-movie-open"
          size="14"
        ></v-icon>

          {{pelicula.genero}}
        </div>




      </template>
    </v-card-item>

    <v-divider></v-divider>


    <v-card-text  style="font-size: 10px">
      <v-row align="start" no-gutters class="mb-3" justify-content-start >

        <v-col cols="auto" class="text-right">

          <div class="rounded pa-3" style="width:auto; background: #ffffff url('https://png.pngtree.com/thumb_back/fh260/background/20200802/pngtree-3d-abstract-dark-grey-gradient-background-image_374469.jpg');border: 2px solid red;">

          <v-img
          :aspect-ratio="1"
          class="elevation-7"
          :src="pelicula.imagen"
          width="210"
          contain

          ></v-img>

        </div>




      </v-col>


    </v-row>
    </v-card-text>


    <v-divider></v-divider>



        <v-card-text>

          <v-row style="font-size: 8px;" gap=1 justify="center">
        <v-col cols="auto">


          <v-chip
      class="ma-2"
      color="pink"
      label
    >
      <v-icon icon="mdi-label" start></v-icon>
      Tags
    </v-chip>
         <!--  <v-list-item

          rounded="sm"
          slim
        density="compact"
        prepend-icon="mdi-account-question"
      >
        <v-list-item-subtitle style="font-size: 12px">{{pelicula.clasificacion}}</v-list-item-subtitle>
      </v-list-item> -->

        </v-col>

        <v-col cols="auto">

          <v-chip
      class="ma-2"
      color="pink"
      label
    >
      <v-icon icon="mdi-label" start></v-icon>
      Tags
    </v-chip>
          <!-- <v-list-item
          slim
        density="compact"
        prepend-icon="mdi-timer-outline"
      >
        <v-list-item-subtitle  style="font-size: 12px" >{{pelicula.duracion}}'</v-list-item-subtitle>
      </v-list-item> -->

        </v-col>

        <v-col cols="auto">

          <v-chip
      class="ma-2"
      color="green"
      label
    >
      <v-icon icon="mdi-label" start></v-icon>
      Tags
    </v-chip>
         <!--  <v-list-item
          slim
        density="compact"
        prepend-icon="mdi-information-outline"
      >
        <v-list-item-subtitle  style="font-size: 12px" >+Info</v-list-item-subtitle>
      </v-list-item> -->

        </v-col>





      </v-row>
    </v-card-text>





    <v-expand-transition>
      <div v-if="expand">
        <div class="pa-3" style="font-size: 12px; text-align: justify">

          {{pelicula.sipnosis}}

        </div>




        <!-- <v-list class="bg-transparent">
          <v-list-item
            v-for="item in forecast"
            :key="item.day"
            :append-icon="item.icon"
            :subtitle="item.temp"
            :title="item.day"
          >
          </v-list-item>
        </v-list> -->
      </div>
    </v-expand-transition>

    <v-divider></v-divider>

    <v-card-actions>
      <v-btn
      style="color:red;font-size:12px"
        :text= "!expand ? 'Ver sipnosis' : 'Ocultar sipnosis'"
        @click="expand = !expand"
      ></v-btn>
    </v-card-actions>
  </v-card>

  </div>
</template>


<script setup>
import { ref } from 'vue';


const props = defineProps({
  pelicula: {
    type: Object,
    required: true
  }
})

const expand = ref(false)

</script>
<style lang="css">



</style>
