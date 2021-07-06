<template>
    <div class="card col-4 col-sm-1 col-md-3" style="width: 18rem;">
        <img src={{img}} class="card-img-top" alt="">
        <div class="card-body">
          <h5 class="card-title">Card title</h5>
          <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
          <a href="#" class="btn btn-primary">Go somewhere</a>
        </div>
      </div>
</template>

<script>
    export default {
        props:{
          image
        },
        data(){
          return {img: this.image}
        }
    }
</script>

<style lang="stylus" scoped>

</style>