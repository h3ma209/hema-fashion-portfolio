<template>
  <div class="container" id="scroll" data-scroll-container>
    <div class="landing" data-scroll-section>
      <div
        class="name mx-7 font-bold text-5xl lg:text-9xl"
        data-scroll
        data-scroll-speed="-1.3"
      >
        H
      </div>
      <div
        class="name mx-7 font-bold text-5xl lg:text-9xl"
        data-scroll
        data-scroll-speed="-1.6"
      >
        E
      </div>
      <div
        class="name mx-7 font-bold text-5xl lg:text-9xl"
        data-scroll
        data-scroll-speed="-1.8"
      >
        M
      </div>
      <div
        class="name mx-7 font-bold text-5xl lg:text-9xl"
        data-scroll
        data-scroll-speed="-1"
      >
        A
      </div>
    </div>
    <whitespace></whitespace>
    <div class="about" data-scroll-section>
      <div class="flex flex-col sm:flex-row h-full">
        <div
          class="grid grid-cols-1 place-items-center left"
          data-scroll
          data-scroll-speed="-0.8"
        >
          <img
            class="object-cover h-3/5 rounded-lg"
            src="/IMG_2821.JPG"
            alt=""
            srcset=""
          />
        </div>
        <div class="grid lg:w-4/5 lg:content-center sm:items-center right p-4">
          <div
            class="font-bold text-5xl lg:text-9xl"
            data-scroll
            data-scroll-speed="2.5"
          >
            About Me
          </div>
          <div class="my-6"></div>
          <div
            class="font-normal text-xl lg:text-3xl desc"
            data-scroll
            data-scroll-speed="2.7"
          >
            Lorem, ipsum dolor sit amet consectetur adipisicing elit. Deleniti
            eius, labore harum consectetur, deserunt totam omnis enim est velit
            veritatis quos voluptas. Commodi veniam
          </div>
        </div>
      </div>
    </div>
    <whitespace></whitespace>

    <div class="portfolio p-6" data-scroll-section>
      <div class="grid sm:grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
        <!-- <img height="50%" width="40%" class="rounded-lg " src="https://images.pexels.com/photos/157675/fashion-men-s-individuality-black-and-white-157675.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260" alt="" srcset=""> -->
        <showcase
          v-for="(dt, i) in gallery"
          :key="i"
          :number="'0' + (i + 1)"
          :src="dt.src"
          :caption="dt.caption"
          :speed="dt.speed"
          :delay="dt.delay"
          class="p-2 m-3"
        ></showcase>
      </div>
    </div>
    <Whitespace></Whitespace>
    <Whitespace></Whitespace>
  </div>
</template>

<script>
import Showcase from "../components/Showcase.vue";
import Whitespace from "../components/Whitespace.vue";

export default {
  components: {
    Showcase,
    Whitespace,
  },
  mounted() {
    setTimeout(() => {
      this.lmS = new this.LocomotiveScroll({
        el: document.querySelector("#scroll"),
        smooth: true,
        getDirection: true,
        getSpeed: true,
        mobile: {
          smooth: true,
        },
        tablet: {
          smooth: true,
        },
        // direction: 'vertical'
      });
    }, 5000);
  },
  data() {
    return {
      gallery: [
        {
          caption: "H E M A",
          speed: { img: "4", caption: "3", number: "3" },
          delay: { img: "", caption: "", number: "" },
          src: "IMG_2271.JPEG",
        },
        {
          caption: "H E M A",
          speed: { img: "5", caption: "4", number: "4" },
          delay: { img: "", caption: "", number: "" },
          src: "IMG_2760.JPEG ",
        },
        {
          caption: "H E M A",
          speed: { img: "6", caption: "5", number: "5" },
          delay: { img: "", caption: "", number: "" },
          src: "IMG_2845.JPEG",
        },
        {
          caption: "H E M A",
          speed: { img: "6", caption: "5", number: "5" },
          delay: { img: "", caption: "", number: "" },
          src: "IMG_2834.JPEG",
        },
        {
          caption: "H E M A",
          speed: { img: "6", caption: "5", number: "5" },
          delay: { img: "", caption: "", number: "" },
          src: "IMG_2789.JPEG",
        },
        {
          caption: "H E M A",
          speed: { img: "6", caption: "5", number: "5" },
          delay: { img: "", caption: "", number: "" },
          src: "IMG_2712.JPEG",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
/* Sample `apply` at-rules with Tailwind CSS
.container {
@apply min-h-screen flex justify-center items-center text-center mx-auto;
}
*/
.container {
  margin: 0 auto;
  min-height: 100%;
  min-width: 100%;
  max-width: 100%;
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
    height: auto;
    width: 100%;
  }
}
</style>
