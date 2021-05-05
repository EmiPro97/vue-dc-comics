<template>
    <main>
        <!-- Main content -->
        <section class="content">
            <div class="container flex a-items-center">
                <h1>Content goes here...</h1>
            </div>
        </section>

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
export default {
    name: 'Main',
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

<style scoped>
main .content{
    height: 130px;
    background: #1c1c1c;
}

.content h1{
    font-size: 35px;
}

main .buy-section{
    height: 155px;
    background: dodgerblue;
}

main .buy-section .container{
    padding: 0 40px;
}

.buy-section ul{
    width: 100%;
}

.buy-section ul li{
    margin-right: 90px;
}

.buy-section ul li:last-child{
    margin-right: 0;
}

.buy-section li a{
    height: 100%;
    transition: transform 0.3s;
}

.buy-section li a:hover{
    transform: scale(1.05);
}

.buy-section .img-wrap{
    height: 50px;
    margin-right: 10px;
}

.buy-section li:last-child .img-wrap{
    height: 35px;
}

.buy-section .img-wrap img{
    height: 100%;
}
</style>