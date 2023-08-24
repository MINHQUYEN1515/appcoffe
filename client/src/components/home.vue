<template>
    <div class="contaner">
        <div class="content">
            <div class="word">
                Cà phê - nơi hòa quyện giữa hương thơm, hương vị và nhịp sống đô thị. 
                    Đó là một điểm đến không thể bỏ qua cho những ai yêu thích không gian thư giãn và tận hưởng những ly cà phê tinh tế. 
                    Cafe là nơi mà ta có thể thoả mình với những hạt cà phê thơm ngon, được pha chế bởi những nhân viên chuyên nghiệp và tâm huyết.
                    Không chỉ là nơi để thưởng thức cà phê, cafe cũng là điểm đến cho những cuộc gặp gỡ bạn bè,
                    giao lưu với những người đam mê cà phê và thảo luận về những điều thú vị trong cuộc sống.
                    Với không gian ấm cúng, decor đẹp mắt và âm nhạc nhẹ nhàng, cafe trở thành điểm đến lý
                    tưởng để tránh xa sự xô bồ của cuộc sống hàng ngày.
                    Hãy đến và khám phá vẻ đẹp riêng tại cafe, nơi mà cà phê trở thành niềm đam mê và tinh thần sống của bạn.
                       <div class="getstart">
                    <button @click="check">TRẢI NGHIỆM</button>
                </div>
            </div>
         
            </div>
        <div class="background">
            <img src="img/logo.jpg" alt="">
        </div>
    </div>
</template>


<script>
    import {reactive} from 'vue'
    export default{
        props:{
                makerting:{
                    type:Array
                }
            },
        setup({makerting},{emit}){
            function next(){
                emit('next',{makerting})
            }
            function previous(){
                emit('prev',{makerting})
            }
            return {next,previous}
        }
    }
</script>

<style lang="scss" scoped>
    .contaner{
        flex: 4;
        display: grid;
        grid-template-columns: repeat(2,1fr);
        padding: 20px;
       
        gap:10px;
        & .content{
        & .word{
            color: #fff;
            font-size: 20px;
            font-weight: 500;
            text-indent:32px;
            max-height: 200px;
            padding: 50px;
            cursor: pointer;
             & .getstart{
            width: 150px;
            height: 50px;
            padding: 100px;
            
            & button{
                width: 100%;
                height: 100%;
                background-color: pink;
                border-radius: 10px;
                font-weight: 600;
                cursor: pointer;

            }
        }

        }
       
        
    }
    & .background{
            width: 70%;
            height: 200px;
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 50px;
            & img{
                width: 100%;
                height: 100%;
                border-radius: 50%;
            }
        }
    }
    
    
</style>