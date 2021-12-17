<template>
  <div class="custom-cursor">
    <div class="custom-cursor__circle"  ref="customCursorCircle"></div>
    <!-- <div class="custom-cursor__dot" :style="dotStyle" ref="customCursorDot"></div> -->
  </div>
</template>

<script>
export default {
  name: "CustomCursor",
  
  data() {
    return {
      scale: 1,
      x: null,
      y: null,
      circlePosX: null,
      circlePosY: null,
      
    };
  },
  methods: {
    customCursor(e) {
      this.x = e.clientX;
      this.y = e.clientY;
      const circle = this.$refs.customCursorCircle;
      this.circlePosX = this.x - circle.clientWidth / 2;
      this.circlePosY = this.y - circle.clientWidth / 2;
      circle.style.transform = `translate(${this.circlePosX}px,${this.circlePosY}px) scale(${this.scale})`;
    
    }
  },
  mounted() {
    window.addEventListener("mousemove", this.customCursor);
  }
};
</script>

<style lang="scss" scoped>
$ease: cubic-bezier(0.23, 1, 0.32, 1);
.custom-cursor {
  cursor: none;
  pointer-events: none;
}
.custom-cursor__circle {
  position: fixed;
  cursor: none;
  top: 0;
  left: 0;
  width: 50px;
  height: 50px;
  border: 2px solid $secondary;
  border-radius: 50%;
  transform: translate(-100%, -100%);
  transition: transform 0.4s $ease;
  z-index: 99999;
}

</style>