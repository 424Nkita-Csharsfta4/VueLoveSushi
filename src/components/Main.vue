<template>
    <div class="wrapper">
        <div class="header">
            <div class="container">
                <div class="header__logo">
                    <img alt="Pizza logo" src="https://www.pngjoy.com/pngm/407/7480138_cute-love-sushi-t-shirt-design-png-download.png" width="58" />
                    <div>
                        <h1>LoveSushi</h1>
                        <p>самая вкусная пицца во вселенной</p>
                    </div>
                </div>
                <div class="header__cart">
                    <a class="button button--cart" href="/cart.html">
                        <span>{{ price }} ₽</span>
                        <div class="button__delimiter"></div>
                        <svg fill="none" height="18" viewBox="0 0 18 18" width="18" xmlns="http://www.w3.org/2000/svg">
                            <path
                                d="M6.33333 16.3333C7.06971 16.3333 7.66667 15.7364 7.66667 15C7.66667 14.2636 7.06971 13.6667 6.33333 13.6667C5.59695 13.6667 5 14.2636 5 15C5 15.7364 5.59695 16.3333 6.33333 16.3333Z"
                                stroke="white" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.8" />
                            <path
                                d="M14.3333 16.3333C15.0697 16.3333 15.6667 15.7364 15.6667 15C15.6667 14.2636 15.0697 13.6667 14.3333 13.6667C13.597 13.6667 13 14.2636 13 15C13 15.7364 13.597 16.3333 14.3333 16.3333Z"
                                stroke="white" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.8" />
                            <path
                                d="M4.78002 4.99999H16.3334L15.2134 10.5933C15.1524 10.9003 14.9854 11.176 14.7417 11.3722C14.4979 11.5684 14.1929 11.6727 13.88 11.6667H6.83335C6.50781 11.6694 6.1925 11.553 5.94689 11.3393C5.70128 11.1256 5.54233 10.8295 5.50002 10.5067L4.48669 2.82666C4.44466 2.50615 4.28764 2.21182 4.04482 1.99844C3.80201 1.78505 3.48994 1.66715 3.16669 1.66666H1.66669"
                                stroke="white" stroke-linecap="round" stroke-linejoin="round" stroke-width="1.8" />
                        </svg>
                        <span>{{ count }}</span>
                    </a>
                </div>
            </div>
        </div>
        <div class="content">
            <div class="container">
               
                <h2 class="content__title">Все пиццы</h2>
                <div class="content__items">
                    <pizza v-for="pizza in pizzas" :id="pizza.id" :key="pizza.id" :image="pizza.image" :price="pizza.price"
                        :title="pizza.title" @add-to-cart="addPizzaToCart"></pizza>
                </div>
            </div>
            
        </div>
    </div>
    
</template>
  
<script>
import Pizza from './Sort.vue'
import { ref } from 'vue'
import useCart from './UseCart'


export default {
    components: {
        Pizza,
    },

    setup() {
        const { count, price } = useCart()

        const pizzas = ref([
            {
                id: 1,
                title: 'Маргарита',
                price: 400,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/dd4b719911d048e0b05c3e4219880e64_366x366.jpeg',
            }, {
                id: 2,
                title: 'Четыре сезона',
                price: 350,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/ca0730a9b2d6457a899a41765555dc29_366x366.jpeg',
            }, {
                id: 3,
                title: 'Портофино',
                price: 420,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/0d5410630b5c4f9eba6e8607423a587a_366x366.jpeg',
            }, {
                id: 4,
                title: 'Мексиканская',
                price: 380,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/186dfa8511434e5eae09fc109b5a8498_366x366.jpeg',
            },
            {
                id: 5,
                title: 'Пицца из половинок',
                price: 640,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/3eb52fd02f0348df913beb28f77d766e_366x366.webp',
            },
            {
                id: 6,
                title: 'Ветчина и сыр',
                price: 590,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/cea570842b754c52b786c231c65bd2e2_366x366.webp',
            },
            {
                id: 7,
                title: 'Чоризо фреш',
                price: 289,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/02ca2561953b488993878d1f70e359de_366x366.webp',
            },
            {
                id: 8,
                title: 'Додо',
                price: 819,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/2676fc1086464a26801a852a702f5d78_366x366.webp',
            },
            {
                id: 9,
                title: 'Бургер-пицца',
                price: 629,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/1a9252b622b6494ebde59163374402a9_366x366.webp',
            },
            {
                id: 10,
                title: 'Гавайская',
                price: 419,
                image: 'https://dodopizza-a.akamaihd.net/static/Img/Products/9b0c599124a8414f89fd59967f3baa3d_366x366.webp',
            },
      
        ])

        return {
            pizzas,
            count,
            price
        }
    }
}
</script>