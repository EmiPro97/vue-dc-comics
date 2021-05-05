<template>
    <main>
        <!-- Jumbotron -->
        <section class="jumbotron"></section>

        <!-- Current Series -->
        <CurrentSeries/>

        <!-- Buy section -->
        <section class="buy-section">
            <div class="container flex a-items-center">
                 <ul class="flex space-between">
                    <li v-for="(link, index) in buyLinks"
                        :key="index"
                    >
                        <a class="flex a-items-center text-uppercase" href="link.href">
                            <div class="img-wrap"><img :src="link.url" :alt="link.text"></div>
                            {{link.text}}
                        </a>
                    </li>
                </ul>
            </div>
         </section>
    </main>
</template>

<script>
import CurrentSeries from '@/components/CurrentSeries.vue';

export default {
    name: 'Main',
    components: {
        CurrentSeries,
    },
    data() {
        return {
            buyLinks: [
                {text: 'digital comics', url: require('../assets/img/buy-comics-digital-comics.png'), href: '#'},
                {text: 'merchandise', url: require('../assets/img/buy-comics-merchandise.png'), href: '#'},
                {text: 'subscription', url: require('../assets/img/buy-comics-subscriptions.png'), href: '#'},
                {text: 'comic shop locator', url: require('../assets/img/buy-comics-shop-locator.png'), href: '#'},
                {text: 'dc power visa', url: require('../assets/img/buy-comics-power-visa.png'), href: '#'},
            ],
        }
    },
}
</script>

<style scoped lang="scss">
// Variables
@import '../styles/vars';

// Main content
main{
    // Jumbotron
    .jumbotron{
        height: 400px;
        background: url('../assets/img/jumbotron.jpg');
    }

    // Buy section
    .buy-section{
        height: 155px;
        background: $dodger;
        .container{padding: 0 40px;}
        ul{
            width: 100%;
            & li{
                margin-right: 90px;
                &:last-child{margin-right: 0;}
                & a{
                    height: 100%;
                    transition: transform 0.3s;
                    &:hover{transform: scale(1.05);}
                }
            }
            
            .img-wrap{
                height: 50px;
                margin-right: 10px;     
                & img{height: 100%;}
            }
         
            li:last-child .img-wrap{
                height: 35px;
            }
        }
    }
}

</style>