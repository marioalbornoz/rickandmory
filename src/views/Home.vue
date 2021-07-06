<template>
  <div class="container">
    <div class="row mt-5">
      <!-- <Card v-for="personaje in personajes" :key="personaje.id" v-bind:image="personaje.image"/> -->
      <div class="card col-4 col-sm-1 col-md-3" v-for="personaje in personajes.data.results" :key="personaje.id">
        <img :src="personaje.image" class="card-img-top" alt="" />
        <div class="card-body">
          <h5 class="card-title">{{personaje.name}}</h5>
          <!-- <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p> -->
          <!-- <a href="#" class="btn btn-secondary btn-block">Ir al personaje</a> -->
          <router-link class="btn btn-secondary" :to="`/character/${personaje.id}`">Ir al personaje </router-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue';
// import Card from './../components/Card.vue';
import axios from 'axios';
export default {
  name: 'Home',
  components: {
    // Card
  },
  data(){
    return{
      personajes:[]
    }
  },
  methods:{
    async obtenerPersonajes(){
      const url = `https://rickandmortyapi.com/api/character`;
      const data = await axios(url);
      this.personajes = await data;
      console.log(this.personajes.data.results);
    }
  },
  created(){
  this.obtenerPersonajes()
  }
}
</script>
