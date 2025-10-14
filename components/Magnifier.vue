<template>
  <div class="image-magnifier">
    <div class="magnifier-container" @mousemove="handleMouseMove" @mouseenter="showMagnifier = true"
      @mouseleave="hideMagnifier">
      <img :src="imageUrl" class="original-image" />
      <div class="magnifier" :style="{
        backgroundImage: 'url(' + imageUrl + ')',
        backgroundSize: zoomedWidth + 'px ' + zoomedHeight + 'px',
        transform: 'translate(' + magX + 'px,' + magY + 'px)',
        backgroundPosition: '-' + (magX * zoomFactor) + 'px -' + (magY * zoomFactor) + 'px',
      }" v-show="showMagnifier"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    imageUrl: String,
    zoomFactor: {type: Number, default: 2},
  },
  data() {
    return {
      showMagnifier: false,
      magnifierSize: 150,
      zoomedWidth: 0,
      zoomedHeight: 0,
      magX: 0,
      magY: 0,
    };
  },
  methods: {
    handleMouseMove(event) {
      const rect = this.$el.getBoundingClientRect(); // Component's bounding rect
      const offsetX = event.clientX - rect.left;
      const offsetY = event.clientY - rect.top;

      const imgWidth = rect.width;
      const imgHeight = rect.height;

      const xPercent = (offsetX / imgWidth) * 100;
      const yPercent = (offsetY / imgHeight) * 100;

      const magX = offsetX - this.magnifierSize / 2;
      const magY = offsetY - this.magnifierSize / 2;

      const zoomedWidth = imgWidth * this.zoomFactor;
      const zoomedHeight = imgHeight * this.zoomFactor;

      this.magX = Math.min(Math.max(0, magX), imgWidth - this.magnifierSize);
      this.magY = Math.min(Math.max(0, magY), imgHeight - this.magnifierSize);

      this.zoomedWidth = zoomedWidth;
      this.zoomedHeight = zoomedHeight;
    },
    hideMagnifier() {
      this.showMagnifier = false;
    },
  },
};
</script>

<style scoped>
.image-magnifier {
  position: relative;
}

.magnifier-container {
  position: relative;
  overflow: hidden;
}

.original-image {
  display: block;
  max-width: 100%;
  height: auto;
}

.magnifier {
  position: absolute;
  width: 140px;
  height: 140px;
  border: 2px solid #fff;
  border-radius: 50%;
  cursor: none;
  transform: translate(-50%, -50%);
  pointer-events: none;
  opacity: 0.8;
  top: 0;
}
</style>
