<template>

    <v-container>



      <div :style="active ? divPrincipal : divPrincipalActive"  @mouseover="active = true" @mouseout="active = false">
        <v-container :style="overlay" v-show="active" >
          <div

            class="d-flex align-center justify-center mb-2"
            style="width: 100%"
          >
            {{ pelicula.titulo }}
          </div>

          <div class="d-flex align-center justify-center" style="width: 100%">
            <v-chip class="ma-2" color="pink" label>
              <v-icon icon="mdi-label" start></v-icon>
              Tags
            </v-chip>

            <v-chip class="ma-2" color="pink" label>
              <v-icon icon="mdi-label" start></v-icon>
              Tags
            </v-chip>

            <v-chip class="ma-2" color="pink" label>
              <v-icon icon="mdi-label" start></v-icon>
              Tags
            </v-chip>
          </div>

          <div class="d-flex align-center justify-center bg-white" style="width: 200px;height: 30px;">
            <v-chip class="ma-2" color="pink" label>
              <v-icon icon="mdi-label" start></v-icon>
              Tags
            </v-chip>

            <v-chip class="ma-2" color="pink" label>
              <v-icon icon="mdi-label" start></v-icon>
              Tags
            </v-chip>


          </div>

        </v-container>
      </div>

    </v-container>

</template>

<script setup>
import {ref} from "vue";
const active = ref(false);

const props = defineProps({
  pelicula: {
    type: Object,
    required: true
  }
})


const overlay = {
  background: "rgba(20, 18, 18, 0.5)",
  padding: "20px",
  borderRadius: "8px",
  justifyContent: "center",
  alignItems:"center",
  display: "flex",
  flexDirection: "column",

}

const overlayNew = {
  background: "rgba(20, 18, 18, 0.5)",
  padding: "20px",
  borderRadius: "8px",
  justifyContent: "center",
  alignItems:"center",
  display: "flex",
  flexDirection: "row",

}

const divPrincipal = {


  backgroundImage: `url(${props.pelicula.imagen})`,
  backgroundSize: "cover",
  backgroundPosition: "center",
  borderRadius: "8px",
  height: "200px",
  width: "230px",
  display: "flex",
  alignItems: "flex-end",
  justifyContent: "center",

}

const divPrincipalActive = {

  backgroundImage: `url(${props.pelicula.imagen})`,
  backgroundSize: "contain",
  backgroundPosition: "center",
  borderRadius: "8px",
  height: "200px",
  width: "230px",
  display: "flex",
  alignItems: "flex-end",
  justifyContent: "center",

}

const cambiarEstilo = () => {
  active.value = !active.value;


}

</script>

<style scoped>
.background-image {
  background-image: url("https://culturalalbacete.es/wp-content/uploads/2024/07/Pepe-Viyuela-2-scaled.jpg");
  background-size: contain;
  background-position: center;
  border-radius: 8px;
  height: 200px;
  width: 230px;
  display: flex;
  align-items: flex-end;
  justify-content: center;
}
.overlay {
  background: rgba(20, 18, 18, 0.5);
  padding: 20px;
  border-radius: 8px;
  justify-content: center;
  align-items: center;
  display: flex;
  flex-direction: column;
}


</style>
