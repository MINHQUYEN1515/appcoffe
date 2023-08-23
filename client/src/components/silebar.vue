<template>
    <div class="menucustomer" :class="{ active: Isactive }">
                        <div class="exit" @click="changeactive">
                            <font-awesome-icon :icon="['far', 'circle-xmark']" /> 
                        </div>
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
        setup() {
        const Isactive = ref(false)
        function changeactive() {
            Isactive.value = !Isactive.value
            console.log(1);
        }
        return { changeactive, Isactive }
    }
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
            & .exit{
               position: absolute;
               right: 0;
               & svg{

                   height: 25px;
                   width: 25px;
               }
            }
            & ul{
              display: grid;
              grid-template-rows: 100px 100px 100px 100px;
              justify-content: space-between;
              align-items: center;
              color: black;
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
            &.active{
             display: block;
            }
 
         }
       
</style>