<template>
 <div id="testmonials" >
  <h3>{{ title }}</h3>
      <div class="form" >
        <div class="form-group">
          <label>Your Name</label>

          <input class="form-control" type="text" v-model="onecomment.title">
        </div>
        <div class="form-group">
          <label>Your Position</label>
          <input class="form-control" type="text" v-model="onecomment.position">
        </div>
        <div class="form-group">
          <label>Comments</label>
          <textarea class="form-control" type="text" v-model="onecomment.text"></textarea>
        </div>
        <button class="btn btn-primary" @click="addComment">Submit</button>
      </div>
      <div class="col-sm-12">
        <div class="col-sm-4 comment" v-for="comment in comments">
          <div class="card">
            <div class="card-block">
              <h4 class="card-title">{{ comment.title }} - {{ comment.position }}</h4>

              <!-- <h6 class="card-subtitle mb-2 text-mutted">{{ comment.date }}</h6> -->
              <p class="card-text">{{ comment.text }}</p>
            </div>
          </div>
        </div>
      </div>
</div>
</template>

<script>
import axios from "axios";
export default {
  name: 'testmonials',
  data() {
    return {
      title:'Testmonials',
     onecomment: {
            title: '',
            text: '',
            position: '',
            // date: new Date(Date.now()).toLocaleString()
          },
    comments: []
    }
  },
  methods: {
          addComment() {
            let { title, text, position } = this.onecomment
            const obj = {
              'title' : this.onecomment.title,
              'text' : this.onecomment.text,
              'position' : this.onecomment.position
            };

            //  ！！put changed to  Post ， comment out push
            // this.comments.push({
            //   text,
            //   title,
            //   position,
            //   // date: new Date(Date.now()).toLocaleString()
            // });
            axios
              // send the information
              // ！！ put 改为 POST
              .post(
                "https://midterm-lin00146.firebaseio.com/data.json",
                obj
              )
              // whatever com back from the server
              // put not run , then will run,(response => {}) means :function (response){}
              .then(response => {
                //
                console.log(response);
                // status response
                console.log('Your data was saved status: " + response.status');
                // !! 新的post start： copy code from create： get the data from database
                axios
                .get("https://midterm-lin00146.firebaseio.com/data.json")
                // if successful
                // arrow function, es6
                // this "response" is a response
                .then(response => {
                  // console.log(response.data);
                  if (response.data) {
                    this.comments = response.data;
                    // alert('hi')
                  }
                })
                // !! 新的post end
    
              })
              // catch the error
              .catch(error => {
                console.log(error);
              });
          },
        },
  created() {
    axios
      .get("https://midterm-lin00146.firebaseio.com/data.json")
      // if successful
      // arrow function, es6
      // this "response" is a response
      .then(response => {
        // console.log(response.data);
        if (response.data) {
          this.comments = response.data;
          // alert('hi')
        }
      })
      // if not successful
      // "response" is a property of subject
      .catch(error => {
        console.log("There was an error in getting data:" + error.response);
      });
  }
}
</script>
