<template>
      <div class="modal-overlay">
     <div class="modal-content">
      <div class="close">
        <button @click="close">Close</button>
      </div>
       <!-- Modal content goes here -->
       <div class="left">
        <img :src="sanpham.url" alt="">
        <div class="size">
              <div class="sizeproduct">
                <button @click="test">M</button>
              </div>
              <div class="sizeproduct">
                <button>L</button>
              </div>
              <div class="sizeproduct">
                <button>XL</button>
              </div>
        </div>
       </div>
      
       <div class="content">
          <h3>{{ sanpham.name }}</h3>
          <p>This is my text</p>
          <div class="cart">
          <img src="src/src_product/img_product/add.png" alt="" @click="add">
          <h2>{{ count }}</h2>
          <img src="src/src_product/img_product/minus (1).png" alt="" @click="remove">
            </div>
       </div>
       <div class="buy">
        <button>Thêm vào giỏ hàng</button>
        <button>Đặt hàng</button>
       </div>
     </div>
   </div>
</template>

<script>
    import {ref,reactive} from 'vue'
    
    export default{
      props:{
        sanpham:{
          type:Object
        }
        
      },
     
      setup(props,emit){
        const count=ref(0)
        class Product{
          constructor(name,size){
            this.name=name
            this.size=size
          }
        }
        function add(){
          count.value++
          
        }
        function close(){
         emit.emit('close',1)
        }
        function test(){
          console.log(props.sanpham);
        }
        function remove(){
          var coffe=new Product('coffe',"L")
          var coffe1=new Product('coffe1','M')
          var a=[coffe,coffe1]
          console.log(a);
          count.value--;
          if(count.value<0){
            count.value=0;
          }
        }
        return {count,add,remove,test,close}
      }
    }
</script>



<style>
   .modal-overlay {
     position: fixed;
     top: 0;
     left: 0;
     width: 100%;
     height: 100%;
     background-color: rgba(0, 0, 0, 0.5); /* semi-transparent overlay */
     display: block;
     
    
   }

   .modal-content {
     background-color: #fff;
     max-width: 700px;
     min-height: 500px;
     margin: 100px auto;
     padding: 20px;
     border-radius: 5px;
     display: flex;
     border-radius: 20px;
 
     
   }
   .left img{
    height: 300px;
    width: 300px;
    margin-top: 50px;
    background-size: cover;
    flex:1;
   }
   .content{
    word-wrap: break-word;
    overflow-wrap: break-word;
    flex: 5;
   }
   .cart{
    display: flex;
    transform: translate(10px,200px);
    justify-content: space-between;
    width: 100px;
    border: 1px solid black;
   }
  .size{
    width: 300px;
    height: 50px;
    display: flex;
    flex-direction: row;

    
  }
  .sizeproduct{
    width: 100px;
    padding: 10px;
    
  }
  .sizeproduct button{
    height: 100%;
    width: 100%;
    background-color: transparent;
 
  }
  .sizeproduct button:focus{
    background-color: red;
  }
   .cart>img{
    height: 30px;
    width: 30px;
    border: 1px solid black;
   }
   .close>button{
    transform: translate(650px,-15px);
    background-color: transparent;
    border: none;
    color: #000;
    cursor: pointer;
    font-size: 18px;
   }
   .close>button:hover {
  color: #ff0000; /* Change color on hover if desired */
}
</style>