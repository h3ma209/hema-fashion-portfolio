<template>
    <div class="container" id="scroll" data-scroll-container>
        <div class="landing" data-scroll-section>

            <div class="name mx-7 font-bold text-9xl" data-scroll data-scroll-speed='1.3'>
                H
            </div>
            <div class="name mx-7 font-bold text-9xl" data-scroll data-scroll-speed='1.6'>
                E
            </div>
            <div class="name mx-7 font-bold text-9xl" data-scroll data-scroll-speed='1.8'>
                M
            </div>
            <div class="name mx-7 font-bold text-9xl" data-scroll data-scroll-speed='2'>
                A
            </div>
        </div>

        <div class="about" data-scroll-section>
            <div class="flex h-full">
                <div class="grid grid-cols-1  place-items-center left" data-scroll data-scroll-speed='-0.8'>
                    <img class="object-cover h-3/5 rounded-lg " src="https://images.pexels.com/photos/157675/fashion-men-s-individuality-black-and-white-157675.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260" alt="" srcset="">
                </div>
                <div class="grid w-4/5 content-center right p-4">
                    <div class="font-bold text-9xl" data-scroll data-scroll-speed='1'>
                        About Me
                    </div>
                    <div class="my-6">
                    </div>
                    <div class="font-normal text-3xl desc" data-scroll data-scroll-speed='1.2'>
                        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Deleniti eius, labore harum consectetur, deserunt totam omnis enim est velit veritatis quos voluptas. Commodi veniam
                    </div>
                </div>
            </div>
        </div>
        <div class="portfolio" data-scroll-section>
            <div class="grid grid-rows-3 grid-flow-col gap-4 place-items-center">
                <div class="grid place-items-center row-start-2 row-span-2 ..."><img height="50%" width="40%" class="rounded-lg " src="https://images.pexels.com/photos/157675/fashion-men-s-individuality-black-and-white-157675.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260" alt="" srcset=""></div>
                <div class="grid place-items-center row-end-3 row-span-1 ..."><img height="50%" width="40%" class="rounded-lg " src="https://images.pexels.com/photos/157675/fashion-men-s-individuality-black-and-white-157675.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260" alt="" srcset=""></div>
                <div class="grid place-items-center row-start-2 row-span-2 ..."><img height="50%" width="40%" class="rounded-lg " src="https://images.pexels.com/photos/157675/fashion-men-s-individuality-black-and-white-157675.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260" alt="" srcset=""></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    mounted() {
        this.lmS = new this.LocomotiveScroll({
            el: document.querySelector("#scroll"),
            smooth: true,
            direction: 'vertical'
        });
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
    background: $primary;
    color: $secondary;
    .landing {
        height: 100vh;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;

        // .name {
        //     transition: all 0.7s cubic-bezier(0.86, 0, 0.07, 1);
        // }
        // .name:hover {
        //     transform: scale(1.4);
        // }
    }
    .about {
        height: 100vh;
        width: 100%;

        .right {
            .desc {
                color: $primarySm !important;
            }
        }
    }
    .portfolio {
        height: 150vh;
        width: 100%;
    }
}
</style>
