<template>

  <div class="black-bg" v-if="modalStatus==true">
    <div class="white-bg">
      <h4>상세페이지임</h4>
        <p>상세페이지 내용</p>
    </div>
    <button @click="closeBtn"> 닫기</button>
  </div>


  <div class="menu">
    <a v-for="(menu) in menus" v-bind:key="menu" >{{menu}}</a>
  </div>

      <!-- <div>
      <img src="./assets/room1.jpg" class="room-img">
      <p @click="viewDetail">{{products[0]}}</p>
      <p>30만원</p>
      </div>
       
      <div>
      <img src="./assets/room2.jpg" class="room-img">
      <p>{{products[1]}}</p>
      <p>40만원</p>
      </div> 

      <div>
      <img src="./assets/room3.jpg" class="room-img">
      <p>{{products[2]}}</p>
      <p>50만원</p>

  </div> -->
    <div v-for="data in datas" v-bind:key="data">
        <img :src="data.image" class="room-img">
        <p>{{data.title}}</p>
        <p>{{data.content}}</p>
        <p>{{data.price}}</p>
    </div>

</template>
<script>
import data from "./assets/data";

export default {
  name: 'App',
  data : function(){
    return {
      datas : data, 

      modalStatus : false,
      count : [0,0,0], 
      menus : ['Home','Products','About'],
      products:['역삼동원룸','천호동원룸','마포구원룸'],
      price :  ['10만', '20만원', '30만원']
    }
  },
  methods :{
    viewDetail(){
      this.modalStatus = true;
    },
    closeBtn() {
       this.modalStatus = false;
    }
  },
  components: {
 
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background-color: green ;
  padding : 10px;
}
.menu a {
  color : whitesmoke;
  padding: 30px;
}
.room-img{
  width:30%;
  margin-top : 40px
}
.black-bg {
  width: 50%; height : 50%; top:10%;  text-align:center;
  margin-left: 25%;
  background-color: black;
  position : fixed; padding: 20px;
}
.black-bg .white-bg{
  position: relative;
  width: 80%; height:80%; 
 
   background: gray;
  border-radius : 8px;
  padding:20px;
}

</style>
