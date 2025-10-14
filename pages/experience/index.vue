<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <Banner title="THE KIVA" description="EXPERIENCE" banner="ex.png" />
        <div class="container-fluid">
          <div
            class="row"
            data-aos="fade-up"
            data-aos-offset="200"
            data-aos-delay="0"
            data-aos-duration="800"
            data-aos-easing="ease-in-out"
            data-aos-once="true"
          >
            <div class="col-12 text-center our-philosophy">Our Philosophy</div>
            <div class="col-12 text-center">
              <div class="philosophy-context">
                We at Kiva stone source the finest and the most exquisite
                stones from around the world for you to curate your dream space.
                Quality and excellence is in our DNA and every slab that ships
                from our stores is a testament to the attention to detail of our
                curators.
              </div>
            </div>
            <div
              data-aos="fade-up"
              data-aos-offset="0"
              data-aos-delay="100"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
              class="col-md-6 col-lg-4 col-sm-12 text-center text-lg-center text-md-right quality"
            >
              QUALITY AND EXCELLENCE
            </div>
            <div
              data-aos="fade-up"
              data-aos-offset="0"
              data-aos-delay="250"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
              class="col-md-6 col-lg-4 col-sm-12 text-center text-lg-center text-md-left quality"
            >
              PATNERSHIP & COLLABORATION
            </div>
            <div
              data-aos="fade-up"
              data-aos-offset="0"
              data-aos-delay="500"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
              class="col-md-12 col-lg-4 col-sm-12 text-center text-lg-center text-md-center quality"
            >
              FINEST MATERIALS
            </div>
          </div>
        </div>
        <div
          class="banner"
          data-aos="fade-up"
          data-aos-offset="200"
          data-aos-delay="0"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        >
          <img class="header-banner desktop" src="../../static/raj.png" />
          <img
            class="header-banner header-banner-short mobile"
            src="../../static/pixel.png"
          />
          <div class="text-center legacy">
            The Legacy of Kiva
            <button class="btn explore-more-button" @click="pageView('legacy')">
              EXPLORE MORE
            </button>
          </div>
        </div>
        <InspirationSection mainText="Living" firstText="Transform Your" />

        <div
          class="banner top-margin"
          data-aos="fade-up"
          data-aos-offset="200"
          data-aos-delay="0"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        >
          <img class="header-banner" src="../../static/wash.png" />

          <div class="text-center legacy">
            Download our catalogue

            <button class="btn explore-more-button">DOWNLOAD</button>
          </div>
        </div>
        <div class="visualizatin-container">
          <VisualizeStone />
        </div>
        <FooterSection />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "default",
  head() {
    return {
      title: "Kiva | Experience",
    };
  },
  methods: {
    pageView(page) {
      location.href = `/${page}`;
    },
  },
};
</script>

<style scoped>
.header-logo {
  width: 100%;
  background-image: url("../../static/ex.png");
  background-size: cover;
  background-position: center;
  height: 75vh;
  position: relative;
}

.header-banner {
  width: 100%;
}

.desktop {
  display: block;
}

.mobile {
  display: none;
}

.banner {
  position: relative;
  margin-top: 80px;
}

.visualizatin-container {
  margin: auto;
  margin-bottom: 102px;
  width: 100%;
  margin-top: 100px;
}

.scroll-text {
  writing-mode: vertical-lr;
  letter-spacing: 5px;
  font-size: 10px;
  color: white;
  bottom: 190px;
  left: 35px;
  position: absolute;
  transform: rotate(180deg);
}

.first-line {
  border-left: 2px solid rgb(229, 229, 229);
  margin-top: 365px;
}

.scroll-line {
  height: 11.2em;
  position: absolute;
  margin-left: 40px;
  bottom: 0;
}

.visualizatin-container {
  margin: auto;
  margin-bottom: 102px;
  width: 100%;
  margin-top: 100px;
}

.nav-small-text {
  position: absolute;
  margin-top: 300px;
  margin-left: 210px;
  font-family: Nexa;
  font-size: 22px;
  letter-spacing: 10px;
  color: white;
  z-index: 1;
}

.nav-experience-text {
  position: absolute;
  margin-top: 280px;
  margin-left: 190px;
  font-family: Madesaonara;
  font-size: 150px;
  color: white;
  z-index: 1;
}

.our-philosophy {
  font-size: 50px;
  font-family: Nexa;
  margin-top: 80px;
}

.philosophy-context {
  max-width: 720px;
  margin-left: auto;
  font-family: NexaLight;
  margin-right: auto;
  left: 0;
  right: 0;
  margin-bottom: 80px;
  margin-top: 20px;
}

.quality {
  font-size: 14px;
  font-family: NexaBold;
  margin-bottom: 20px;
}

.top-margin {
  margin-top: 100px;
}

.legacy {
  font-size: 70px;
  font-family: Nexa;
  position: absolute;
  color: white;
  top: 50%;
  transform: translateY(-50%);
  margin: auto;
  left: 0;
  right: 0;
  display: flex;
  flex-direction: column;
}

.explore-more-button {
  color: white;
  /* position: absolute; */
  /* margin-top: -200px; */
  background-color: none;
  padding: 10px;
  width: 220px;
  /* margin-left: -100px; */
  border: 1px solid white;
  font-size: 12px;
  font-family: Nexa;
  letter-spacing: 3px;
  margin: auto;
  left: 0;
  right: 0;
  margin-top: 10px;
  /* top: 120px; */
}

.header-shadow {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
}

@media only screen and (max-width: 1399px) and (min-width: 1280px) {
  .header-shadow {
    width: 100%;
  }

  .nav-small-text {
    margin-top: 240px;
    margin-left: 210px;
    font-size: 16px;
  }

  .nav-experience-text {
    margin-top: 240px;
    margin-left: 190px;
    font-size: 100px;
  }

  .first-line {
    border-left: 2px solid rgb(229, 229, 229);
    margin-top: 200px;
  }

  .scroll-line {
    margin-left: 40px;
  }

  .scroll-text {
    top: 120px;
    left: 35px;
  }
}

@media only screen and (max-width: 1279px) and (min-width: 1024px) {
  .dot-one {
    margin-left: 40px;
    margin-top: 8px;
  }

  .horizontle-line {
    border-bottom: 1px solid rgb(243, 240, 240);
    line-height: 1px;
    margin-left: 290px;
    bottom: 12px;
    position: relative;
  }

  .header-shadow {
    width: 100%;
  }

  .nav-small-text {
    margin-top: 220px;
    margin-left: 120px;
    font-size: 12px;
  }

  .nav-experience-text {
    margin-top: 210px;
    margin-left: 110px;
    font-size: 70px;
  }

  .first-line {
    border-left: 2px solid rgb(229, 229, 229);
    margin-top: 365px;
  }

  /* .scroll-line {
    height: 17.2em;
    position: absolute;
    margin-left: 40px;
  } */

  .first-line {
    border-left: 2px solid rgb(229, 229, 229);
    margin-top: 175px;
  }

  /* .scroll-line {
    height: 11.2em;
    margin-left: 40px;
  } */

  .scroll-text {
    top: 100px;
    left: 35px;
  }
}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .header-shadow {
    width: 100%;
  }

  .our-philosophy {
    font-size: 38px;
  }

  .philosophy-context {
    margin-top: 32px;
  }

  .search-mobile-tab {
    display: block;
  }

  .nav-small-text {
    margin-top: 220px;
    margin-left: 120px;
    font-size: 5px;
  }

  .nav-experience-text {
    margin-top: 210px;
    margin-left: 110px;
    font-size: 79px;
  }

  .first-line {
    margin-top: 270px;
  }

  .scroll-line {
    margin-left: 30px;
  }

  .scroll-text {
    top: 200px;
    left: 26px;
    font-size: 8px;
  }

  .left-element {
    padding-left: 0;
  }

  .legacy {
    font-size: 42px;
  }

  .right-elemet {
    padding-left: 0;
  }
}

@media only screen and (max-width: 767px) {
  .header-shadow {
    width: 100%;
  }

  .banner {
    overflow: hidden;
    text-align: center;
  }

  .header-banner {
    height: 320px;
    width: auto;
    text-align: center;
    overflow: hidden;
    margin: auto;
    left: 0;
    right: 0;
    position: relative;
  }

  .legacy {
    font-size: 30px;
  }

  .explore-more-button {
    top: 45px;
  }

  .carousel {
    margin-top: -40px;
    width: 100%;
    padding-left: 20px;
  }

  .search-mobile-tab {
    display: block;
  }

  .nav-small-text {
    margin-top: 220px;
    margin-left: 47px;
    font-size: 9px;
  }

  .nav-experience-text {
    margin-top: 220px;
    margin-left: 40px;
    font-size: 55px;
  }

  .first-line {
    display: none;
  }

  .scroll-line {
    display: none;
  }

  .scroll-text {
    display: none;
  }

  .pagination {
    display: none;
  }

  .per-page {
    display: none;
  }

  .left-element {
    padding: 10px;
  }

  .right-elemet {
    padding: 10px;
  }
}

@media only screen and (max-width: 480px) and (min-width: 360px) {
  .header-banner-short {
    width: 100%;
    height: auto;
  }

  .mobile {
    display: block;
  }

  .desktop {
    display: none;
  }

  .explore-more-button {
    background-color: #000;
    color: #fff;
    margin-top: 10px;
  }

  .our-philosophy {
    font-size: 24px;
  }
}
</style>
