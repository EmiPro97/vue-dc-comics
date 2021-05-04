<template>
    <header>
        <div class="container flex space-between a-items-center">
            <a class="img-wrap" href="#"><img src="../assets/img/dc-logo.png" alt="logo-dc"></a>
            <nav>
                <ul class="flex">
                    <li v-for="(link, index) in navLinks"
                        :key="index"
                    >
                        <a :href="link.url"
                            :class="{active: link.active}"
                            @click="toggleActive(index)"
                        >{{link.text}}</a>
                        <div class="line" :class="{active: link.active}"></div>
                    </li>
                </ul>
            </nav>
        </div>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data() {
        return {
            navLinks: [
                {text: 'characters', url: '#', active: false},
                {text: 'comics', url: '#', active: true},
                {text: 'movies', url: '#', active: false},
                {text: 'tv', url: '#', active: false},
                {text: 'games', url: '#', active: false},
                {text: 'collectibles', url: '#', active: false},
                {text: 'videos', url: '#', active: false},
                {text: 'fans', url: '#', active: false},
                {text: 'news', url: '#', active: false},
                {text: 'shop', url: '#', active: false},
            ],
        }
    },
    methods: {
        toggleActive(index) {
            this.navLinks.forEach(element => {
                if (element.active === true) {
                    element.active = false;
                }
            });
            this.navLinks[index].active = !this.navLinks[index].active;
        }
    },
}
</script>

<style scoped>
/* General */
header{
    height: 120px;
}

/* Img */
.img-wrap{
    width: 70px;
    height: 70px;
}

.img-wrap img{
    width: 100%;
    height: 100%;
}

/* Nav */
ul li{
    margin-right: 35px;
    line-height: 120px;
    position: relative;
    transition: color 0.4s;
}

ul li:last-child{
    margin-right: 0;
}

ul li .line{
    position: absolute;
    bottom: 0;
    left: 0;
    width: 0%;
    height: 5px;
    background: dodgerblue;
    transition: width 0.4s ease-out;
}


ul li .line.active{
    width: 100%;
}

li a{
    text-transform: uppercase;
    font-weight: 700;
    color: #464646;
}

li a.active{
    color: dodgerblue;
}
</style>