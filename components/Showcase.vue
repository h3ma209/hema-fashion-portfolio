<template>
    <div class="container ">
        <div class="number text-5xl font-normal" data-scroll :data-scroll-speed='speed.number' :data-scroll-delay='delay.numbar'>{{number}}</div>

        <img class="img-cover rounded-lg h-4/4 lg:max-w-sm object-contain" rel="preload" data-scroll :src="src" :data-scroll-speed='speed.img' :data-scroll-delay='delay.img'>


        <div class="caption text-5xl font-bold" data-scroll :data-scroll-speed='speed.caption' :data-scroll-delay='delay.caption'>
            {{caption}}
        </div>
    </div>
</template>

<script>
export default {
    setup() {

    },
    props: {
        src: String,
        caption: String,
        number: String,

        // speed: {
        //     img: String,
        //     number: String,
        //     caption: String
        // }
        speed: {
            type: Object,
            default: undefined
        },
        delay: Object,
    }
}
</script>

<style lang="scss" scoped>
.container {
    position: relative;
    display: grid;
    background: red;
    max-height: 300;
    .number {
        position: absolute;
        align-self: start;
        justify-self: end;
        right: 10vh;
    }
    .caption {
        position: absolute;
        align-self: center;
        justify-self: end;
        right: 3vh;
        display: none;
    }
    .img-cover {
        align-self: center;
        justify-self: center;
        transition: box-shadow 0.3s cubic-bezier(0.86, 0, 0.07, 1);
    }
    .img-cover:hover{
        box-shadow: rgba(100, 100, 111, 0.5) 0px 7px 29px 0px;
    }
}
</style>