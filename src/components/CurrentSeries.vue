<template>
   <!-- Current Series -->
    <section class="series-content">
        <div class="container">
            <div class="series-title-wrap"><h2 class="text-uppercase">current series</h2></div>
            <div class="comics-wrap flex">
                <ComicCard v-for="(card, index) in cards" :key="index" :details="card" />
            </div>
            <div class="btn-wrap"><a class="btn text-uppercase" href="#">load more</a></div>
        </div>
    </section>
</template>

<script>
import ComicCard from '@/components/ComicCard.vue';
import DCcomics from '@/data/dc-comics.js';

export default {
    name: 'CurrentSeries',
    components: {
        ComicCard,
    },
    data() {
        return {
            cards: DCcomics,
        };
    },
}
</script>

<style scoped lang="scss">
// Variables
@import '../styles/vars';

// Current Series
.series-content{
    background: #1c1c1c;
    .series-title-wrap{
        display: inline-block;
        transform: translateY(-50%);
        background: $dodger;
        padding: 12px 30px;
        margin-bottom: 30px;
    }
    .comics-wrap{
        flex-wrap: wrap;
    }
    a{
        transition: transform 0.3s ease-out;
        &:hover{transform: scale(1.1);}
    }
    .btn-wrap{
        text-align: center;
        .btn{
            display: inline-block;
            background: $dodger;
            padding: 12px 50px;
            margin: 30px 0 25px 0;
            font-weight: 500;
            &:active{position: relative; top: 4px;}
        }
    }
}
</style>