<template>
  <footer>
      <div class="container flex a-items-center">
        <ul class="flex space-between">
            <li v-for="(link, index) in buyLinks"
                :key="index"
            >
                <a class="flex a-items-center" href="link.href">
                    <div class="img-wrap"><img :src="link.url" :alt="link.text"></div>
                    {{link.text}}
                </a>
            </li>
        </ul>
      </div>
  </footer>
</template>

<script>
export default {
    name: 'Footer',
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
footer{
    height: 155px;
    background: dodgerblue;
}

.container{
    padding: 0 40px;
}

ul{
    width: 100%;
}

ul li{
    margin-right: 90px;
}

ul li:last-child{
    margin-right: 0;
}

li a{
    height: 100%;
    text-transform: uppercase;
    transition: transform 0.3s;
}

li a:hover{
    transform: scale(1.05);
}

.img-wrap{
    height: 50px;
    margin-right: 10px;
}

li:last-child .img-wrap{
    height: 35px;
}

.img-wrap img{
    height: 100%;
}
</style>