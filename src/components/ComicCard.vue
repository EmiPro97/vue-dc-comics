<template>
    <div class="flex flex-column">
        <a href="#"><img :src="details.thumb" :alt="details.series"></a>
        <a href="#"><span class="text-uppercase">{{details.series}}</span></a>
    </div>
</template>

<script>
export default {
    name: 'ComicCard',
    props: {
        details: Object,
    },
}
</script>

<style scoped lang="scss">
div{
    align-items: flex-start;
    width: calc(100% / 6 - 30px);
    margin: 0 15px 50px 15px;
    a:first-child{
        width: 100%;
        height: 190px;
        transition: transform 0.3s ease-out;
        &:hover{transform: scale(1.1);}
    }
    a:last-child{
        margin-top: 20px;
    }
    img{
        width: 100%;
        height: 100%;
        object-fit: cover;
        object-position: top;
    }
}
</style>