<template>
  <div class="container">
      <div class="row">
          <div class="col-auto">
                <img src="" alt="">
          </div>
          <div class="col-8">
              <h1>Nombre</h1>
              <p>Especie</p>
              <p>Estado</p>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    
methods:{
    async obtenerPersonajes(){
      try {
          const url = `https://rickandmortyapi.com/api/character/${this.$route.params.id}`;
            const data = await axios(url);
            this.personajes = await data;
            console.log(this.personajes.data.results);
      } catch (error) {
          console.error(error);
      }
    }
  },
  created(){
  this.obtenerPersonajes()
  }
}
</script>

<style>

</style>