<template>
  <div>
    <Banner></Banner>
    <Related ></Related>
    <Offer></Offer>
    <LatestProducts></LatestProducts>
    <ProductCategory></ProductCategory>
    <TrendingProducts></TrendingProducts>
    <BestSellers></BestSellers>
    <Facility></Facility>
  
    <News></News>
    <Subscribe></Subscribe>
    <Partner></Partner>
    <InstagramPhotos></InstagramPhotos>
     <Testimonials></Testimonials>
  </div>
</template>

<script>
import Related from '../components/products/RelatedProducts'
import Banner from '../components/landing-one/Banner';
import Offer from '../components/landing-one/Offer';
import LatestProducts from '../components/landing-one/LatestProducts';
import ProductCategory from '../components/landing-one/ProductCategory';
import TrendingProducts from '../components/landing-one/TrendingProducts';
import BestSellers from '../components/landing-one/BestSellers';
import Facility from '../components/landing-one/Facility';
import Testimonials from '../components/landing-one/Testimonials';
import News from '../components/landing-one/News';
import Subscribe from '../components/common/Subscribe';
import Partner from '../components/common/Partner';
import InstagramPhotos from '../components/common/InstagramPhotos';

export default {
  components: {
    Banner, Offer, LatestProducts, ProductCategory, TrendingProducts,
    BestSellers, Facility, Testimonials, News, Subscribe, Partner, InstagramPhotos
  }
}
</script>