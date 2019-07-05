<template>
  <div class="about">
     <br>
     <h1>{{title}}</h1>
      <br>
     <div class="container">
  <div class="row">
    <div class="col"><img :src="image" ></div>
    <div class="col"><h3>{{ content }}</h3></div>
    <div class="w-100"></div>
    <div class="col"><h3>{{ content }}</h3></div>
    <div class="col"><img :src="image" ></div>
  </div>
</div>
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      title: 'About Us',
    
        image       : require('../assets/logo.png'),
        content: 'Lorem ipsum dolor sit amet, mei in ullum equidem moderatius, impetus gubergren vim id, ius putent volumus eu. Et mea mucius molestie periculis, in idque senserit voluptatibus vel. Ea vel agam iudico similique. Percipit signiferumque cu mel, quo an nostrud perfecto oportere, sed harum regione eripuit cu.'
      }
      
      }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1{
  text-align: center;
}
</style>

