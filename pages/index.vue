<template>
    <div class="container" id="scroll">
        <div class="landing">

            <div class="name mx-7 font-bold text-9xl">
                H
            </div>
            <div class="name mx-7 font-bold text-9xl">
                E
            </div>
            <div class="name mx-7 font-bold text-9xl">
                M
            </div>
            <div class="name mx-7 font-bold text-9xl">
                A
            </div>

        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        // this.lmS = new this.LocomotiveScroll({
        //     el: document.querySelector("#scroll"),
        //     smooth: true,
        //     direction: 'vertical'
        // });
    }
}
</script>

<style lang='scss' scoped>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
    margin: 0 auto;
    min-height: 100%;
    .landing {
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;

        .name{
            transition: all 0.7s cubic-bezier(0.86, 0, 0.07, 1);
        }
        .name:hover{
            transform: scale(1.4);
        }
    }
}
</style>
