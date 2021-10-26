<template>
    <div>
        <!-- Start Page Title Area -->
        <div class="page-title-area">
            <div class="container">
                <ul>
                    <li><nuxt-link to="/">Home</nuxt-link></li>
                    <li @click="PO">All Products</li>
                </ul>
            </div>
        </div>
        <!-- End Page Title Area -->

        <!-- Start Collections Area -->
        <section class="products-collections-area">
            <div class="container">
                <div class="row">
                    <Sidebar :maxPrice="maxPrice" :minPrice="minPrice" @InputChange="InputChange" @Check="Check" :products="products" />
                    <AllProducts :products="fiterProducts" />
                </div>
            </div>
        </section>
        <!-- End Collections Area -->
    </div>
</template>

<script>
import Sidebar from '../components/all-products/Sidebar';
import AllProducts from '../components/all-products/AllProducts';
export default {
    components: {
        Sidebar, AllProducts
    },
    data(){
        return{
            sortTedProduct:[],
             minPrice:0,
             maxPrice:10000
        }
    },
      computed: {
        products(){
            return this.$store.state.products.all
        },
        fiterProducts(){
            let vm = this
            if(this.sortTedProduct.length){
                return this.sortTedProduct
            }else{
                return this.products
            }
        }
    },
    methods: {
        Check(e){
            this.sortTedProduct = []
            let vm = this
           this.products.map(function(item){
               if(item.type === e){
                   vm.sortTedProduct.push(item)
               }
           })
        },
        Po(){}
        
    },
    mounted(){
        this.$store.dispatch('getOrder')
        console.log('mounted')
    }
}
</script>