<template>
  <div class="click-feature container-fluid" @click="toUrl('https://visualizer.kivastone.com')">
    <div
      class="visualize-text mt-5"
      data-aos="fade-up"
      data-aos-offset="200"
      data-aos-delay="0"
      data-aos-duration="800"
      data-aos-easing="ease-in-out"
      data-aos-once="true"
    >
      <div>VISUALIZE</div>
      <div>YOUR</div>
      <div>STONE</div>
    </div>
    <img class="visualizer-image" src="../static/3dvisualizer.png" />
    <button class="btn know-more-button">ENTER VISUALIZER</button>
    <div class="row">
      <div class="col-lg-6 col-md-3 hide-mobile"></div>
      <div class="know-more col-lg-6 col-md-9 hide-mobile">
        ENTER 3D VISUALIZER
        <span class="dot-one"></span>
        <div class="horizontle-line"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  methods: {
    pageView() {
      location.href = "https://visualizer.kivastone.com/";
    },
    toUrl(url) {
      window.open(url, "_blank");
    },
  },
};
</script>

<style scoped>
.visualize-text {
  font-size: 40px;
  letter-spacing: 38px;
  font-weight: 500;
  position: absolute;
  font-family: NexaBold;
  padding-left: 40px;
}

.know-more-button {
  display: none;
}

.hide-mobile {
  display: block;
}

.know-more {
  height: 30px;
  padding-left: 60px;
  letter-spacing: 7px;
  background-color: #4d4d4d;
  width: 100%;
  color: white;
  margin-top: -60px;
  position: relative;
  font-weight: bold;
  font-size: 14px;
  border-left: 5px solid #fff;
  font-family: NexaBold;
  padding-right: 0;
  /* padding-top: 6px; */
}

.visualizer-image {
  width: 980px;
  margin-left: 200px;
}

.dot-one {
  height: 10px;
  width: 10px;
  background-color: rgb(255, 255, 255);
  border-radius: 50%;
  display: inline-block;
  margin-left: 36px;
  bottom: 8px;
  margin-top: 10px;
}

.horizontle-line {
  border-bottom: 1px solid rgb(243, 240, 240);
  line-height: 1px;
  margin-left: 346px;
  bottom: 11px;
  position: relative;
}

.click-feature {
  cursor: pointer;
  padding-left: 120px;
  /* position: relative; */
}

@media only screen and (max-width: 1399px) and (min-width: 1280px) {
  .visualizer-image {
    width: 860px;
    margin-left: 0px;
  }

  .know-more {
    width: 60%;
  }

  .visualize-text {
    margin-left: -60px;
  }
}

@media only screen and (max-width: 1279px) and (min-width: 1024px) {
  .visualizer-image {
    width: 660px;
    margin-left: 0px;
  }

  .know-more {
    font-size: 14px;
  }

  .visualize-text {
    margin-left: -40px;
  }

  .dot-one {
    margin-left: 36px;
    margin-top: 8px;
  }

  .horizontle-line {
    border-bottom: 1px solid rgb(243, 240, 240);
    line-height: 1px;
    margin-left: 348px;
    bottom: 12px;
    position: relative;
  }
}

@media only screen and (max-width: 767px) {
  .visualizer-image {
    margin-left: -127%;
    height: 100%;
  }

  .click-feature {
    margin-bottom: -160px;
    text-align: center;
    width: 280px;
    overflow: hidden;
    padding-left: 0;
  }

  .know-more {
    font-size: 10px;
  }

  .visualize-text {
    margin-left: -70px;
    font-size: 22px;
    letter-spacing: 22px;
    margin-top: -50px !important;
    text-align: left;
  }

  .dot-one {
    margin-left: 36px;
    margin-top: 10px;
  }

  .horizontle-line {
    border-bottom: 1px solid rgb(243, 240, 240);
    line-height: 1px;
    margin-left: 290px;
    bottom: 12px;
    position: relative;
  }

  .hide-mobile {
    display: none;
  }

  .know-more-button {
    display: block;
    position: absolute;
    border: 1px solid white;
    font-size: 7px;
    font-family: Poppins;
    letter-spacing: 5px;
    padding-left: 40px;
    padding-right: 40px;
    padding-top: 10px;
    padding-bottom: 10px;
    border-radius: 0px;
    background-color: black;
    color: white;
    margin-top: -120px;
    left: 0;
    right: 0;
    margin-left: auto;
    margin-right: auto;
    width: 226px;
    margin-top: -120px;
  }
}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .visualizer-image {
    width: 540px;
    margin-left: 0px;
    height: 400px;
  }

  .know-more {
    font-size: 14px;
  }

  .dot-one {
    margin-left: 36px;
    margin-top: 8px;
  }

  .horizontle-line {
    border-bottom: 1px solid rgb(243, 240, 240);
    line-height: 1px;
    margin-left: 340px;
    bottom: 12px;
    position: relative;
  }

  .visualize-text {
    margin-top: -60px !important;
  }
}

@media only screen and (min-width: 1440px) {
  .visualizer-image {
    width: 50%;
  }
}

@media only screen and (max-width: 359px) {
  .visualize-text {
    margin-left: -32px;
    font-size: 18px;
    letter-spacing: 22px;
    margin-top: -50px !important;
    text-align: left;
  }
}

</style>
