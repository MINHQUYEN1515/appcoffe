<template>
    <div class="menucustomer">
                        <ul>
                            <li>
                                <font-awesome-icon :icon="['fas', 'house']" />
                                <a href="#">Trang chủ</a></li>
                            <li>
                                <font-awesome-icon :icon="['far', 'circle-user']" />
                                <a href="#">Đăng nhập</a>
                            </li>
                            <li>
                                <font-awesome-icon :icon="['fas', 'cart-shopping']" />
                                <a href="#">Đơn hàng</a>
                            </li>
                            <li>
                                <font-awesome-icon :icon="['fas', 'gear']" />
                                <a href="#">Cài đặt</a>
                            </li>
                        </ul>
                    </div>
       
    
</template>

<script>
    import { ref } from 'vue';
    export default{
       
    }
</script>

<style lang="scss">
        .menucustomer{
            width: 0px;
            position: relative;
            display: block;
            color: black;
            background-color: #fff;
            width: 200px;
            height: 918px;

               & svg{

                   height: 25px;
                   width: 25px;
               }
            
            & ul{
              display: grid;
              grid-template-rows: 100px 100px 100px 100px;
              justify-content: space-between;
              align-items: center;
              color: black;
              & li:hover{
                width: 99%;
                height: 50px;
                transform: translateY(-10px); /* Di chuyển vật thể lên trên */
             box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.3);
             cursor: pointer;
              }
                & li{
                    padding-left: 10px;
                    width:183px;
                    display: grid;
                    grid-template-columns: 30% 70%;
                    justify-content: space-evenly;
                    align-items: center;
                    font-size: 25px;
                    font-weight: 600;
                    list-style-type: none;
              
                    & a{
                        color: black;
                        text-decoration: none;
                    }
                }
            }
           
 
         }
        
       
</style>