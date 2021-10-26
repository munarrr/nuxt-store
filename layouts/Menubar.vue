<template>
    <div>
        <!-- Start Navbar Area -->
        <div :class="['navbar-area', {'is-sticky': isSticky}]">
            <div class="comero-nav">
                <div class="container">
                    <nav class="navbar navbar-expand-md navbar-light">
                        <nuxt-link class="navbar-brand" to="/">
                            <img src="../assets/img/logotip.png" alt="logo">
                        </nuxt-link>
                        <b-navbar-toggle target="navbarSupportedContent"></b-navbar-toggle>
                        <b-collapse class="collapse navbar-collapse" id="navbarSupportedContent" is-nav>
                            <ul class="navbar-nav">                                
                                <li class="nav-item p-relative"> <nuxt-link to="/" class="nav-link">Главная</nuxt-link>
                                </li>

                                <li class="nav-item p-relative">
                                    <nuxt-link class="nav-link" to="/products">Категории</nuxt-link>
                                    </li>

                                <li class="nav-item">
                                    <nuxt-link to="/gallery-one" class="nav-link">Новинки</nuxt-link>
                                </li>

                                <li class="nav-item p-relative"><a href="#" class="nav-link">О магазине <i class="fas fa-chevron-down"></i></a>
                                    <ul class="dropdown-menu">
                                        <li class="nav-item">
                                            <nuxt-link to="/gallery-one" class="nav-link">Gallery</nuxt-link>
                                        </li>

                                        <li class="nav-item">
                                            <nuxt-link to="/cart" class="nav-link">Cart</nuxt-link>
                                        </li>

                                        <li class="nav-item">
                                            <nuxt-link to="/checkout" class="nav-link">Checkout</nuxt-link>
                                        </li>

                                        <li class="nav-item">
                                            <nuxt-link to="/login" class="nav-link">Login</nuxt-link>
                                        </li>

                                        <li class="nav-item">
                                            <nuxt-link to="/signup" class="nav-link">Signup</nuxt-link>
                                        </li>

                                        <li class="nav-item">
                                            <nuxt-link to="/not-found" class="nav-link">Error 404</nuxt-link>
                                        </li>

                                        <li class="nav-item">
                                            <nuxt-link to="/contact" class="nav-link">Contact</nuxt-link>
                                        </li>
                                    </ul>
                                </li>

                                <li class="nav-item p-relative">  <nuxt-link to="/contact-us" class="nav-link">Contact</nuxt-link></li>

                                <li class="nav-item">
                                    <nuxt-link to="/contact" class="nav-link">Доставка</nuxt-link>
                                </li>
                                 <li class="nav-item">
                                    <nuxt-link to="/contact" class="nav-link">Sale</nuxt-link>
                                </li>
                            </ul>
                     </b-collapse>
                            <div class="others-option">
                                <div class="option-item">
                                    <nuxt-link to="/login"><i style="font-size: 22px" class="far fa-user"></i></nuxt-link>
                                </div>
                              
                                 <div class="option-item">
                                    <nuxt-link to="/login">  <i style="font-size: 22px" class="fas fa-search"></i></nuxt-link>
                                </div>
                                  <div class="option-item">
                                    <nuxt-link to="/login"> <i style="font-size: 22px" class="far fa-heart"></i></nuxt-link>
                                </div>
                                <div class="option-item">
                                    <a @click.prevent="toggle" href="#">
                                        <ul class="flex-row justify-content-end flex-wrap align-items-center ">    
                                        <li class="nav-item  text-uppercase mb-0 position-relative d-lg-flex">                                        
                                            <a href="#" class="cart position-relative d-inline-flex" aria-label="View your shopping cart">
                                            <i style="font-size: 22px" class="fas fa fa-shopping-cart fa-lg"></i>
                                            <span class="cart-basket d-flex align-items-center justify-content-center">
                                              {{cart.length}}
                                            </span>
                                            </a>
                                        </li>
                                        </ul>
                                    </a>
                                </div>
                            </div>
                       
                    </nav>
                </div>
            </div>
        </div>
        <!-- End Navbar Area -->

        <SidebarPanel></SidebarPanel>
    </div>
</template>

<script>
import SidebarPanel from '../layouts/SidebarPanel';
import { mutations } from '../utils/sidebar-util';
export default {
    components: {
        SidebarPanel
    },
    data(){
        return {
            isSticky: false
        }
    },
    mounted(){
        const that = this;
        window.addEventListener('scroll', () => {
            let scrollPos = window.scrollY;
            if(scrollPos >= 100){
                that.isSticky = true;
            } else {
                that.isSticky = false;
            }
        })
    },
    computed: {
        cart(){
            return this.$store.getters.cart
        }
    },
    methods: {
        toggle() {
            mutations.toggleNav()
        }
    }
}
</script>