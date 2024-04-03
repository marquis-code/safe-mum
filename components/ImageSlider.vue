<template>
  <div class="relative overflow-hidden">
    <transition name="fade" @before-enter="beforeEnter" @enter="enter" @leave="leave">
      <img v-if="currentImage" :key="currentImage" :src="require(`@/assets/img/${currentImage}.png`)"
        alt="Slideshow Image" class="mx-auto w-full h-[500px] max-w-full drop-shadow-xl" />
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        'mobile1',
        'mobile2',
        'mobile3',
        'mobile4',
      ],
      currentIndex: 0,
    };
  },
  computed: {
    currentImage() {
      return this.images[this.currentIndex];
    },
  },
  mounted() {
    setInterval(this.nextImage, 5000); // Change image every 5000 milliseconds (5 seconds)
  },
  methods: {
    nextImage() {
      this.currentIndex = (this.currentIndex + 1) % this.images.length;
    },
    beforeEnter(el) {
      el.style.opacity = 0;
      el.style.transform = "scale(1.1)";
    },
    enter(el, done) {
      el.offsetWidth; // trigger reflow
      el.style.transition = "opacity 2s ease-in-out, transform 2s ease-in-out";
      el.style.opacity = 1;
      el.style.transform = "scale(1)";
      done();
    },
    leave(el, done) {
      el.style.transition = "opacity 2s ease-in-out, transform 2s ease-in-out";
      el.style.opacity = 0;
      el.style.transform = "scale(1.1)";
      done();
    },
  },
};
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 2s ease-in-out, transform 2s ease-in-out;
}

.fade-enter,
.fade-leave-to

/* .fade-leave-active in <2.1.8 */
  {
  opacity: 0;
  transform: scale(1.1);
}

.image-slider-container {
  height: 300px;
  /* Adjust based on your needs */
  position: relative;
}
</style>
