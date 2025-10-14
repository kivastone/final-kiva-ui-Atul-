<template>
  <div>
    <div class="text-box">
      <div
        class="text-uppercase find-text"
        data-aos="fade-up"
        data-aos-offset="0"
        data-aos-delay="0"
        data-aos-duration="800"
        data-aos-easing="ease-in-out"
        data-aos-once="true"
      >
        {{ firstText }}
      </div>
      <div
        class="text-uppercase space-text"
        data-aos="fade-up"
        data-aos-offset="0"
        data-aos-delay="0"
        data-aos-duration="800"
        data-aos-easing="ease-in-out"
        data-aos-once="true"
      >
        {{ mainText }}
      </div>
      <div
        class="decription-text"
        data-aos="fade-up"
        data-aos-offset="0"
        data-aos-delay="100"
        data-aos-duration="800"
        data-aos-easing="ease-in-out"
        data-aos-once="true"
      >
        Find your inspiration with Kiva stone. We have the perfect collection
        of ideas and inspiration from all the spaces that we have transformed
        over the years. Transform your next dream home with Kiva
      </div>
    </div>
    <div v-if="isHome" class="section image-margin-home">
      <div class="image-margin" v-for="imgage in backImgs">
        <img
          class="section-image"
          :src="imgage"
          data-aos="zoom-in"
          data-aos-offset="400"
          data-aos-delay="200"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        />
      </div>
    </div>
    <div v-else class="section">
      <div class="image-margin">
        <img
          class="section-image"
          src="../static/p5.png"
          data-aos="zoom-in"
          data-aos-offset="400"
          data-aos-delay="200"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        />
      </div>
      <div class="image-margin">
        <img
          class="section-image"
          src="../static/p2.png"
          data-aos="zoom-in"
          data-aos-offset="400"
          data-aos-delay="200"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        />
      </div>
      <div class="image-margin">
        <img
          class="section-image"
          src="../static/p10.png"
          data-aos="zoom-in"
          data-aos-offset="400"
          data-aos-delay="200"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        />
      </div>
      <div class="image-margin">
        <img
          class="section-image"
          src="../static/partner/retailor.jpg"
          data-aos="zoom-in"
          data-aos-offset="400"
          data-aos-delay="200"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        />
      </div>
      <div class="image-margin">
        <img
          class="section-image"
          src="../static/p6.png"
          data-aos="zoom-in"
          data-aos-offset="400"
          data-aos-delay="200"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        />
      </div>
      <div class="image-margin">
        <img
          class="section-image"
          src="../static/p7.png"
          data-aos="zoom-in"
          data-aos-offset="400"
          data-aos-delay="200"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        />
      </div>
    </div>
    <div
      class="decription-text-mobile"
      data-aos="fade-up"
      data-aos-offset="0"
      data-aos-delay="400"
      data-aos-duration="800"
      data-aos-easing="ease-in-out"
      data-aos-once="true"
    >
      Find your inspiration with Kiva stone. We have the perfect collection of
      ideas and inspiration from all the spaces that we have transformed over
      the years. Transform your next dream home with Kiva
    </div>

    <!-- <div class="section-mobile">
      <div v-for="imgo in backImgsMobile" class="image-margin">
        <img class="section-image-mobile" :src="imgo" />
      </div>
    </div> -->
  </div>
</template>

<script>
export default {
  props: ["firstText", "mainText", "isHome"],
  data() {
    return {
      backImgs: [
        "https://i.ibb.co/m0D51xQ/k.png",
        "https://i.ibb.co/M19h238/l.png",
        "https://i.ibb.co/ZX7RdJG/m.png",
        "https://i.ibb.co/fNfCLnS/o.png",
        "https://i.ibb.co/P1TqNPy/p.png",
        "https://i.ibb.co/F0MCdyw/q.png",
      ],
      backImgsMobile: [
        "https://i.ibb.co/m0D51xQ/k.png",
        "https://i.ibb.co/M19h238/l.png",
        "https://i.ibb.co/ZX7RdJG/m.png",
        "https://i.ibb.co/fNfCLnS/o.png",
        "https://i.ibb.co/P1TqNPy/p.png",
        "https://i.ibb.co/F0MCdyw/q.png",
      ],
    };
  },
};
</script>

<style scoped>
.find-text {
  text-align: left;
  letter-spacing: 14px;
  font-size: 18px;
  font-family: Nexa;
  color: rgb(180, 180, 180);
  top: 0;
  width: 100%;

  color: rgb(180, 180, 180);
  letter-spacing: 12px;
  font-size: 18px;
  font-family: Nexa;
}

.text-box {
  position: absolute;
  /* top: -132px; */
  z-index: 1;
  margin-left: 120px;
  /* left: -212px; */
  margin-top: -123px;
}

.section {
  position: relative;
}

.section-mobile {
  display: none;
}

.space-text {
  font-size: 160px;
  font-family: Madesaonara;
  line-height: 160px;
}

.decription-text,
.decription-text-mobile {
  bottom: 880px;
  font-family: NexaBold;
  font-size: 15px;
  text-align: left;
  margin-top: 50px;
  width: 420px;
  word-wrap: break-word;
}

.decription-text-mobile {
  margin-left: 122px;
  display: none;
  max-width: 320px;
  width: 100%;
}

.section-image {
  width: 100%;
}

.section {
  display: grid;
  column-gap: 15px;
  row-gap: 15px;
  grid-template-columns: auto auto auto;
  position: relative;
  margin-top: 220px;
  max-width: 720px;
  margin-left: auto;
  margin-right: auto;
}

@media only screen and (max-width: 1280px) {
  .space-text {
    font-size: 120px;
    line-height: 120px;
  }

  .text-box {
    z-index: 1;
    /* margin-left: 122px; */
    margin-top: -100px;
  }

  .decription-text-mobile {
    margin-left: 122px;
  }
}

@media only screen and (max-width: 640px) {
  /* .section-mobile{
    display: block;
  } */
  /* .section {
    display: none;
  } */
  .space-text {
    font-size: 80px;
    line-height: 80px;
  }

  .decription-text {
    display: none;
  }

  .decription-text-mobile {
    display: block;
  }

  .section {
    display: grid;
    column-gap: 15px;
    row-gap: 15px;
    grid-template-columns: auto auto;
    position: relative;
    margin-top: 220px;
    max-width: 720px;
    margin-left: auto;
    margin-right: auto;
    padding: 20px;
  }

  .text-box {
    z-index: 1;
    margin-left: 40px;
    margin-top: -48px;
  }

  .decription-text-mobile {
    margin-left: 0;
    max-width: none;
    padding: 0 20px;
    max-width: 540px;
  }

  .section {
    display: grid;
    column-gap: 15px;
    row-gap: 15px;
    grid-template-columns: auto;
    position: relative;
    margin-top: 140px;
    max-width: 720px;
    margin-left: auto;
    margin-right: auto;
  }

  .find-text {
    font-size: 8px;
  }

  .image-margin-home {
    grid-template-columns: auto auto;
  }
}
@media only screen and (max-width: 359px) {
  .space-text {
    font-size: 60px;
    line-height: 80px;
  }
}
</style>
