<template>
    <section class="products">
        <div class="container">
            <div class="products-wrapper" id="goods-container">
                <router-link 
                class="products-card"
                v-for="good in goodsArray"
                :key="good.id"
                :to="`/good?id=${good.id}`"
                >
                    <div class="products-card__image">
                        <img :src="getUrl(good.image)" alt="ugor">
                    </div>
                    <div class="products-card__description">
                        <div class="products-card__description--row">
                            <h5 class="products-card__description--name">
                                {{ good.title }}
                            </h5>         

                        </div> 
                        <div class="products-card__description--row">
                            <p class="products-card__description--text">
                                {{ good.text }}
                            </p>       
                        </div> 
                        <div class="products-card__description--row">
                            <div class="products-card__description-controls">
                                <button class="btn btn-primary">
                                    {{ good.btnName }}
                                    <img src="../assets/images/icons/shopping-cart.svg" alt="shopping-cart">
                                </button>

                                <span class="products-card__description-controls--price">
                                    {{ good.price }}
                                </span>
                            </div>    
                        </div>                                            
                    </div>
                </router-link>


                
            </div>                
        </div>
    </section>
</template>
<script setup>
import {goodsArray} from '../constans/goods'

const getUrl = (name) => {
    return new URL(`../assets/images/goods/${name}`, import.meta.url)
}
</script>