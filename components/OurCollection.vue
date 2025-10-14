<template>
  <div class="mb-5 click-style" @click="pageView(url)">
    <div class="collection-text text-uppercase">{{ collectionText }}</div>
    <div class="collection-box">
      <div class="color-box" :class="url === 'levante' ? 'lav' : 'imp'">
        <img
          class="logo"
          :src="imageUrl1"
          data-aos="fade-in"
          data-aos-offset="200"
          data-aos-delay="0"
          data-aos-duration="1000"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        />
        <div class="line"></div>
      </div>
      <div class="collection-stone-second">
        <img class="" :src="imageUrl2" />
        <!-- <button class="btn know-more-button">KNOW MORE</button> -->
        <div
          :class="url === 'levante' ? 'know-more know-more-dark' : 'know-more'"
        >
          KNOW MORE
          <div class="horizontle-line">
            <span class="dot-white"></span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: ["collectionText", "imageUrl1", "imageUrl2", "url"],
  methods: {
    pageView(page) {
      location.href = `/${page}`;
    },
  },
};
</script>

<style scoped>
.collection-text {
  margin-left: 100px;
  font-family: "Nexa";
  letter-spacing: 4px;
  margin-bottom: 12px;
}

.collection-box {
  display: flex;
  flex: 1 1;
  cursor: pointer;
}

.line {
  position: absolute;
  display: none;
  width: 100%;
  height: 4px;
  bottom: 10px;
  background-image: linear-gradient(to right, #e0b87b, #8a643d);
}

.collection-stone-second {
  position: relative;
  width: 100%;
}

.collection-stone-second img {
  width: 100%;
}

.color-box {
  /* width: 100%; */
  background-color: #27150a;
  position: relative;
  z-index: 1;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}

.color-box img {
  width: 50%;
}

.imp {
  /* width: 100%; */
  background-color: #101c32;
  z-index: 1;
}

.know-more {
  position: absolute;
  bottom: 20px;
  right: 0;
  background-color: #101c32;
  display: flex;
  align-items: center;
  padding: 4px 4px 4px 60px;
  width: calc(100% - 100px);
  color: #fff;
  font-family: "Nexa";
  letter-spacing: 4px;
}

.know-more-dark {
  background-color: #27150a;
}

.horizontle-line {
  width: calc(100% - 240px);
  height: 1px;
  position: absolute;
  right: 0;
  background-color: #fff;
}

.dot-white {
  position: absolute;
  margin-top: -4px;
  background-color: #fff;
  border-radius: 50%;
  width: 8px;
  height: 8px;
}

@media only screen and (max-width: 780px) {
  .collection-box {
    flex-direction: column;
  }

  .line {
    display: block;
  }

  .color-box {
    min-height: 320px;
  }

  .know-more {
    background-color: #e0b87b;
    top: 50%;
    transform: translateY(-50%);
    width: 240px;
    padding: 5px 20px;
    margin: auto;
    left: 0;
    right: 0;
    text-align: center;
    height: auto;
    bottom: auto;
    justify-content: center;
    color: #27150a;
  }

  .horizontle-line,
  .dot {
    display: none;
  }

  .collection-text {
    margin-left: 0;
    text-align: center;
  }
}
</style>
