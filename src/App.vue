<template>
  <div id="app" >
      <div v-for="(p, i) in personajes" :key="i">
        <Personaje  :src="p.imagen" :name="p.nombre"  />
      </div>
  </div>
</template>

<script>
import Personaje from "./components/personaje";
export default {
  components: {
    Personaje,
  },
  data() {
    return {
      personajes: [],
      
    };
  },
  methods: {
   
  },
  mounted() {
    fetch("https://rickandmortyapi.com/api/character")
      .then((response) => response.json())
      .then((json) => {
        let data = json.results;
     
        data.forEach((el) => {
          let nombre = el.name;
          let imagen = el.image;

          this.personajes.push({
            nombre,
            imagen,
          });
        });
      })
      .catch((err) => {
        console.log(`error en  ${err}`);
      });
  },
};
</script>

<style lang="scss">
#app {
  
  display: flex;
  flex-wrap: wrap;
  margin: auto;
  justify-content: space-around;
  margin: 10px;
}


.img{
  height:300px;
  background-image: url("../src/assets/ricklogo.png");
  background-repeat: no-repeat;
  background-position: center;
}

body{


  background: green;
}

h3{

color: white;
text-align: center;
font-weight: bold;

}
</style>
