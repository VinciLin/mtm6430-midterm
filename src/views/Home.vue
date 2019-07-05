<template>
  <div class="home">
    <br>
    <h1>{{title}}</h1>
     <br>
    <div class="container">
      <div class="row justify-content-md-center">
        <div class="col"> <img :src="image" ></div>
        <div class="col"> <h3>{{ content }}</h3></div>
     </div>
    </div>
   
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      title: 'Welcome My Vue App',
    
        image       : require('../assets/logo.png'),
        content: 'Lorem ipsum dolor sit amet, mei in ullum equidem moderatius, impetus gubergren vim id, ius putent volumus eu. Et mea mucius molestie periculis, in idque senserit voluptatibus vel. Ea vel agam iudico similique. Percipit signiferumque cu mel, quo an nostrud perfecto oportere, sed harum regione eripuit cu.'
      }
      
      }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
 h1 {
   text-align: center;
   color: rgb(11, 113, 230);
 }


</style>

