<template>
  <div class="contact">
     <br>
    <h1>{{title}}</h1>
    <br>
    <div class="container">
    <div class="row justify-content-md-center">
       <div class="col">
          <h3>Address</h3>
          <br>
          <p>1435 woodroffe avenue, Ottawa, Ontario. K2G1V8</p>
         
          <p>613-72742</p>
        </div>
      <div class="col">
          <h3>Hours of Operation</h3>
         <li v-for="(value, name) in object">
         
         {{ name }}: {{ value }}
        </li>
      </div>
         </div>
       
       
      
    
    </div>
    
  </div>
</template>
<script>
 export default {
  name: 'contact',
  data () {
    return {
      title:'Contact Us',
      object: {
       Monday: '8AM-6PM ',
       Tuesday: '8AM-6PM',
        Wednesday: '8AM-6PM',
        Thursday: '8AM-6PM',
        Friday: '8AM-6PM',
        Saturday: '10AM-4PM',
       Sunday: '10AM-2PM'
      }
    }
  }
 }

</script>
<style scoped>
h1{
  text-align: center;
}
h3 {
  text-decoration: underline;
  color: rgb(11, 113, 230);
}

li {
  list-style: none;
}
</style>
