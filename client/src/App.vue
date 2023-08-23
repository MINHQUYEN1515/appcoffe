<template>
  <div class="app">
    <Title></Title>
    <div class="content">
        <Sidebar class="sileabr"/>
         <Home :makerting="makerting"
         ></Home>
    </div>
  </div>
  <div id="menu">
    <Menu></Menu>
  </div>

</template>
<script>
  import Title from './components/navbar.vue'
  import Home from './components/home.vue'
  import Menu from './components/menu.vue'
  import Silebar from './components/silebar.vue'
  import {reactive,ref} from 'vue'
  export default{
    data(){
      return{
        dataproduct:[]   
    }
  },

    methods:{
      check (){
        console.log(this.dataproduct)
      }
    },
    components:{
      Title:Title,
      Home:Home,
      Menu:Menu,
      Sidebar:Silebar
    },
    setup(){
      
      const makerting=reactive([{
        id:1,
        url:'src/img/quangcao1.jpg',
        content:'Cafe là một loại đồ uống hương vị đặc biệt, thường được pha từ hạt cà phê rang và nước nóng'
      },
      {
        id:2,
        url:'src/img/quangcao2.jpg',
        content:'Cafes mang lại cảm giác sảng khoái, tinh thần tỉnh táo và tạo cảm hứng cho người uống. '
      },
      {
        id:3,
        url:'src/img/quangcao3.jpg',
        content:' Ngoài ra, các quán cafe cũng thường là nơi gặp gỡ bạn bè, làm việc hoặc thư giãn sau những giờ làm việc căng thẳng.  '
      },
      {
        id:4,
        url:'src/img/quangcao4.jpg',
        content:'Không chỉ thích hợp cho buổi sáng, cafe còn được ưa chuộng trong cả ngày để tận hưởng hương vị đậm đà và thưởng thức không gian dễ chịu. '
      }])

        // create dataproduct
        
      return {makerting}
    },
  
  }
 
</script>

<style lang="scss">
  *{
    padding: 0;
    margin: 0;
  }
    .app{
      width: 100%;
      height: 1000px;
      background-image: linear-gradient(rgba(0,0,0,0.9),rgba(0,0,0,0.4)),url('./img/background.jpeg');
      opacity: 0.8;
    }
    .content{
      display: flex;
      flex-direction: row;
      & .silebar{
        display: none;
      }

    }
    #menu{
      margin-top: 30px;
      height: 1000px;
      background-color: #333;
      
    }
</style>