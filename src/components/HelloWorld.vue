<template>
  <div class="hello">
     <h1>{{title}}</h1>
    <div class="row">
      <div class="column">
        <img :src="image" >
      </div>
      <div class="column">
        <h3>{{ content }}</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      title: 'Welcome',
    
        image       : require('../assets/logo.png'),
        content: 'sasas'
      }
      
      }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 .row {
  display: flex;
}

.column {
  flex: 50%;
}
</style>

