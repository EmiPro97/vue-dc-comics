<template>
    <footer>
        <!-- Footer Links -->
        <section class="footer-links">
            <div class="container flex">
                <div>
                    <!-- DC-comics -->
                    <h3 class="text-uppercase">dc comics</h3>
                    <ul>
                        <li><a href="#">Characters</a></li>
                        <li><a href="#">Comics</a></li>
                        <li><a href="#">Movies</a></li>
                        <li><a href="#">TV</a></li>
                        <li><a href="#">Games</a></li>
                        <li><a href="#">Videos</a></li>
                        <li><a href="#">News</a></li>
                    </ul>
                    <!-- Shop -->
                    <h3 class="text-uppercase">shop</h3>
                    <ul>
                        <li><a href="#">Shop DC</a></li>
                        <li><a href="#">Shop DC Collectibles</a></li>
                    </ul>

                </div>
                <div>
                    <!-- DC -->
                    <h3 class="text-uppercase">dc</h3>
                    <ul>
                        <li><a href="#">Terms Of Use</a></li>
                        <li><a href="#">Privacy policy (New)</a></li>
                        <li><a href="#">Ad Choices</a></li>
                        <li><a href="#">Advertising</a></li>
                        <li><a href="#">Jobs</a></li>
                        <li><a href="#">Subscriptions</a></li>
                        <li><a href="#">Talent Workshops</a></li>
                        <li><a href="#">CPSC Certificates</a></li>
                        <li><a href="#">Ratings</a></li>
                        <li><a href="#">Shop Help</a></li>
                        <li><a href="#">Contact Us</a></li>
                    </ul>
                </div>
                <div>
                    <!-- Sites -->
                    <h3 class="text-uppercase">sites</h3>
                    <ul>
                        <li><a href="#">DC</a></li>
                        <li><a href="#">MAD Magazine</a></li>
                        <li><a href="#">DC Kids</a></li>
                        <li><a href="#">DC Universe</a></li>
                        <li><a href="#">DC Power Visa</a></li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Footer-socials -->
        <section class="footer-socials">
            <div class="container flex space-between a-items-center">
                <a class="btn text-uppercase" href="#">sign-up now!</a>
                <div class="flex a-items-center">
                    <h3 class="text-uppercase">follow us</h3>
                    <ul class="flex">
                        <li class="social" v-for="(social,index) in socials"
                            :key="index"
                        >
                            <a href="#"><img :src="social.path" :alt="social.name"></a>
                        </li>
                    </ul>
                </div>
            </div>
        </section>
    </footer>
</template>

<script>
export default {
    name: 'Footer',
    data() {
        return {
            socials: [
                {name: 'facebook', path: require('../assets/img/footer-facebook.png')},
                {name: 'twitter', path: require('../assets/img/footer-twitter.png')},
                {name: 'youtube', path: require('../assets/img/footer-youtube.png')},
                {name: 'pinterest', path: require('../assets/img/footer-pinterest.png')},
                {name: 'periscope', path: require('../assets/img/footer-periscope.png')},
            ],
        }
    },
}
</script>

<style scoped lang="scss">
// Variables
@import '../styles/vars';

// Footer
footer{
    // Footer links
    .footer-links{
        position: relative;
        height: 370px;
        padding-top: 35px;
        background-image: url('../assets/img/footer-bg.jpg');
        background-repeat: no-repeat;
        background-size: cover;
        &::after{
            content: '';
            position: absolute;
            bottom: 0;
            top: 0;
            left: 50%;
            right: 0;
            background: url('../assets/img/dc-logo-bg.png');
            background-repeat: no-repeat;
            background-position: 20% center;
        }
        & .container div{
            margin-right: 40px;
            & h3{margin-bottom: 10px;}
            & li{line-height: 22px;}
            & li:last-child{margin-bottom: 15px}
            & a{font-size: 14px; color: #959595; transition: color 0.4s;}
            & a:hover{color: #fff;}
        } 
    }

    // Footer socials
    .footer-socials{
        height: 110px;
        background: #303030;
        & h3{margin-right: 20px; color: $dodger;}
        & .social{padding-left: 20px;}
        & a{display: inline-block; transition: transform 0.3s ease-out;}
        & a:hover{transform: scale(1.1);}
        & img{vertical-align: middle;}
    }

    .btn{
        padding: 12px 15px;
        font-weight: 500;
        border: 2px solid $dodger;
        &:active{position: relative; top: 4px;}
    }
}
</style>