<template>
    <div class="navbar">
        <div class="navbar_left">
            <div class="navbar_left-icon" @click="changeactive">
                <font-awesome-icon :icon="['fas', 'bars']" />
            </div>
                <img src="img/logo.jpg" alt="" class="image imagelogo">

        </div>
        <div class="navbar_right">
            <ul class="menu">
                <li><a href="#">HOME</a></li>
                <li><a href="#menu">MENU</a></li>
                <li><a href="#">PRODUCTS</a></li>
                <li><a href="#">PAGES</a></li>
                <li><a href="#">BLOG</a></li>
                <li><a href="#">SHORTCODE</a></li>
            </ul> 
        </div>
    </div>
    
</template>

<script>

</script>
<style lang="scss" scoped>
    .navbar{
        width: 100%;
        height: 100px;
        display: grid;
        background-color: #333;
        grid-template-columns: 20% 80%;
        & .navbar_left{
            display: flex;
            justify-content: space-evenly;
            align-items: center;
            position: relative;
            & .navbar_left-icon{
                height: 35px;
                width: 100px;
                display: flex;
                align-items: center;
                justify-content: center;
                & svg{
                    height: 100%;
                    width: 100%;
                }
            }
            & img{
                height: 83px;
                width: 102px;
                border-radius: 50%;
                user-select: none;
                cursor: pointer;
            }
        }
        & .navbar_right{ 
           & .menu{
            display: flex;
            justify-content: space-evenly;
            align-items: center;
            margin-top: 34px;
            
            & li{
                list-style-type: none;
                & a{
                    text-decoration: none;
                    color: #fff;
                    font-size: 20px;
                    font-weight: 600;

                    
                }
                & a:hover{
                    color: #f6dec2;
                }
            }
           }

            
         }
         
    }
    
 
</style>