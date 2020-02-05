<template>
  <div class="container">
    <form @submit.prevent="addSkill">
      <input type="text" placeholder="Enter a skill you have.." v-model="skill">
      <!-- {{ skill }} -->
    </form>
  
    <!-- {{ name }}

    {{ btnState ? 'Button is enable' : 'Button is disable'}}

     <button @click="changeName" :disabled="btnState">Button</button> -->

     <div class="holder">
       <ul>
         <li v-for="(data, index) in skills" :key='index'>{{data.skill}}
   <i class="fa fa-minus-circle" v-on:click="remove(index)"></i>
  </li>
       </ul>
       <p>These are the skills that you possess.</p>

       <!-- <p v-if="skills.length > 1">More Skills</p>
       <p v-else-if="skills.length === 1">one Skills</p> -->
       
       <!-- <p v-else>No Skills</p> -->

       <!-- <div :class="{ alert: showAlert, 'anotherClass' : showClass}">Hi</div> -->
              <!-- <div :class="alertObject">Hi</div> -->
              <!-- <div :style="{ backgroundColor: bgColor, width: bgWidth, height: bgHeight}">Hi</div> -->

     </div>
  </div> 
 
</template> 



<script>
export default {
  name: 'Skills',
  props: {
  },
  data() {
    return {
      skill: '',
      // name: 'Joyonta',
      // btnState: false,
      skills:[
        {'skill' : 'Vue js'},
        {'skill' : 'Frontend developer'}
      ],
      // alertObject: {
      //  alert: true
      // },
      // bgColor: 'red',
      // bgWidth: '100%',
      // bgHeight: '30px'
      //  showAlert: true,
      // showClass: true
      
    }
  },
  methods: {
    changeName() {
      this.name = 'Joyont Saha'
    },
    addSkill(){
          this.skills.push({skill:this.skill});
          this.skill = '';
      },
      remove(id) {
        this.skills.splice(id, 1);
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.alert{
  background-color: yellow;
  width: 100%;
  height: 30%;
}
.anotherClass{
  border: 60px solid black; */


@import "https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css"; 

    .holder {
    background: #fff;
  }

  ul {
    margin: 0;
    padding: 0;
    list-style-type: none;
  }
  
  ul li {
    padding: 20px;
    font-size: 1.3em;
    background-color: #E0EDF4;
    border-left: 5px solid #3EB3F6;
    margin-bottom: 2px;
    color: #3E5252;
  }

  p {
    text-align:center;
    padding: 30px 0;
    color: gray;
  }

  .container {
    box-shadow: 0px 0px 40px lightgray;
  }
  i {
    float: right;
    cursor:pointer;
  
  }
</style>
