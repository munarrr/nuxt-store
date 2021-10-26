<template>
    <div class="col-lg-8 col-md-12">
        <div class="products-filter-options">
            <div class="row align-items-center">
    

                <div class="col d-flex">
                    <span>Сортировать по:</span>

                    <div class="products-ordering-list">
                        <select>
                            <option value="1">Популярности</option>
                            <option value="2">Цене</option>
                            <option value="3">По алфавиту</option>
                        </select>
                    </div>
                </div>
            </div>
        </div>

        <div id="products-filter" class="products-collections-listing row">
            <ProductItem
                v-for="(product, index) in products"
                :product="product"
                :key="index"
                @clicked="toggle"
                :className="`col-lg-4 col-md-6 products-col-item`"
            ></ProductItem>
            
        </div>

        <nav class="woocommerce-pagination">
            <ul>
                <li><a href="#" class="page-numbers current">Назад</a></li>
                <li><a href="#" class="page-numbers">1</a></li>
                <li><span class="page-numbers current">2</span></li>
                <li><a href="#" class="page-numbers">3</a></li>
                <li><a href="#" class="page-numbers">4</a></li>
                <li><span class="page-numbers dots">…</span></li>
                <li><a href="#" class="page-numbers">11</a></li>
                <li><a href="#" class="page-numbers">12</a></li>
                <li><a href="#" class="next page-numbers current">Вперед</a></li>
            </ul>
        </nav>

        <QuckView />
    </div>
</template>

<script>
import QuckView from '../modals/QuckView';
import { mutations } from '../../utils/sidebar-util';
import ProductItem from '../landing-one/ProductItem';
export default {
    components: {
        QuckView,
        ProductItem
    },
    methods: {
        toggle() {
            mutations.toggleQuickView();
        }
    },
  props:{
      products:{
          type:Array,
      }
  }
}
</script>