<template>
  <div class="hello">
    
        <form action="">
          <InputField v-model="name"/>
            <br> <button> Submit</button>
        </form>
      {{name}}



  
  </div>
</template>

<script>
import InputField from '@/components/InputField.vue'
export default {
  components: {
    InputField
  },

    data(){
      return {
        name :  ''
      }
    },
    // methods:{
    //   updateName(name){
    //     this.name = name;
    //   }
    // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
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
</style>
