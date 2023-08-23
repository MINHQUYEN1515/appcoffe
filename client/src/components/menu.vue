<template>
    <div class="search">
        <input type="text" placeholder="nhập sản phẩm cần tìm kiếm" v-model="search">
    </div>
    
    <div class="menu">
        <div class="item" v-for="Dataproduct in searching" >
             <img :src=Dataproduct.url alt="">
            <h3>Tên sản phẩm:{{ Dataproduct.name }}</h3>
            <h3>Giá:{{ Dataproduct.price }}.000đ</h3>
            <button @click="check(Dataproduct.id)" >Xem thông tin</button>
        </div>
    </div>
    <div class="modal" :class="{active:Isactive}">
        <product :sanpham="sanpham"
        @close="check"
        ></product>
    </div>
   
</template>

<script>
    import product from './product.vue'
    export default{
    data() {
        return {
            dataproduct: [],
            search: '',
            sanpham:{},
            Isactive:false
        };
    },
    async mounted() {
        await this.getdata();
    },
    methods: {
        check(id) {
            this.sanpham=this.dataproduct[id]
            console.log(this.sanpham);
            this.Isactive=!this.Isactive
        },
        async getdata() {
            this.dataproduct = await fetch('src/src_product/product.json').then(res => res.json());
        }
    },
    computed: {
        searching() {
            return this.dataproduct.filter((value) => {
                return value.name.match(this.search);
            });
        }
    },
    components: {
        product:product
     }
}
    
</script>

<style scoped>

    .search{
        min-height: 50px;
        max-width: 800px;
        display: flex;
        margin-left: 30%;
        transform: translateY(100px);
        margin-bottom: 5%;
        z-index: inherit;
    }
    .search>input{

        width: 600px;
        border-radius: 15px;
        padding: 20px;
        margin: 10px 0px;
    }
    .menu{
        margin-top: 100px;
        max-height: 30px;
        max-width: 600px;
        display: grid;
        align-items: center;
        grid-template-columns: repeat(3,1fr);
        grid-template-rows: repeat(2,1fr);
        gap:10px;
        z-index: 10;
        margin-left: 20%;
         border-radius: 10px;
       
        
    }
    .item{
        box-shadow: -3px -3px 7px #ffffff73,2px 2px 5px rgba(94, 104, 121, 0.2888);
        border: 1px solid black;
        height: 300px;
        width: 300px;
        display: flex;
        flex-direction: column;
        align-items: center;
        font-family: "Helvetica Neue", Arial, sans-serif;
        font-weight: 600;
        opacity: 0.8;
        color: #f5f5f5;     
    }
    .item>img{
        height: 200px;
        width: 100%;
    }
    .item>h3{
        
        text-shadow: 1px 1px 1px rgba(0, 0, 0, 0.1);
    }
    .item>button{
        width: 50%;
        height: 50px;
        margin-top: 10px;
        background-color: #3498db;
        color: #fff;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        transition: background-color 0.3s ease;
    }
    .item>button:hover {
        background-color: #2980b9;
    }
    .item:hover{
        transform: scale(0.95);
        transition: all 0.3s;
        opacity: 1;
        background-color: #f5f5f5;
        color: #333;
    }
    
    .modal{
        display: none;
    }
   .active{
    display: block;
   }


</style>