<template>
    <div class="col-lg-4 col-md-12">
        <div class="woocommerce-sidebar-area">
            <div class="collapse-widget collections-list-widget">
                <h3 v-b-toggle.collapse-2 class="collapse-widget-title">
                    Фильтры
                </h3>
                <b-collapse visible id="collapse-2"  v-for="product in products" :key="product.id">
                     <div class="item">
                    <input 
                    @input="Check" 
                    class="inp-cbx" id="cbx"
                    :value="product.type"
                     type="checkbox">
                    <label class="cbx" for="cbx">
                      {{product.type}}
                    </label>
                </div>                
                </b-collapse>
                <div>
                    <input type="number" v-model.number="minPrice" @change="InputChange" min="0">
                    <input type="number" v-model.number="maxPrice" @change="InputChange" max="10000">
                </div>
            </div>
            <div class="collapse-widget size-list-widget">
                <h3 v-b-toggle.collapse-4 class="collapse-widget-title">
                    Size
                    <i class="fas fa-angle-up"></i>
                </h3>

                <b-collapse visible id="collapse-4">
                    <ul class="size-list-row">
                        <li class="active"><a href="#">XS</a></li>
                        <li><a href="#">S</a></li>
                        <li><a href="#">M</a></li>
                        <li><a href="#">L</a></li>
                        <li><a href="#">L</a></li>
                        <li><a href="#">XL</a></li>
                    </ul>
                </b-collapse>
            </div>

            <div class="collapse-widget color-list-widget">
                <h3 v-b-toggle.collapse-6 class="collapse-widget-title">
                    Color
                    <i class="fas fa-angle-up"></i>
                </h3>

                <b-collapse visible id="collapse-6">
                    <ul class="color-list-row">
                        <li><a href="#" title="Black" class="color-black"></a></li>
                        <li><a href="#" title="Red" class="color-red"></a></li>
                        <li><a href="#" title="Yellow" class="color-yellow"></a></li>
                        <li><a href="#" title="White" class="color-white"></a></li>
                        <li><a href="#" title="Blue" class="color-blue"></a></li>
                        <li><a href="#" title="Green" class="color-green"></a></li>
                    </ul>
                </b-collapse>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props:['minPrice','maxPrice'],
    methods:{
        Check(e){
            let value = e.target.value
            this.$emit('Check',value)
        },
        InputChange(){
            this.$emit('InputChange')
        }
    },
    props:{
        products:{
            type: Array
        }
    }
}
</script>