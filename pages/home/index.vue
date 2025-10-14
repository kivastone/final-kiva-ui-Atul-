<template>
  <u-animate-container>
    <div class="x-hidden">
      <NavBar />
      <img class="header-shadow" src="../../static/sha.png" />

      <!-- <video autoplay width="320" height="240" controls>
        <source src="../../static/video.mp4" type="video/mp4" />
      </video> -->

      <div class="scroll-text">SCROLL</div>
      <div class="first-line scroll-line"></div>
      <!-- <img class="header-logo" src="../../static/banner1.png" /> -->
      <!-- <div class="video-container">

      <video src="video_mob.mp4" class="video-desktop" autoplay="true" muted="true" controls="false" loop="true"></video>
      <video src="video_mob.mp4" class="video-mobile" autoplay="true" muted="true" controls="false" loop="true"></video>
    </div> -->
      <div class="video-container video-desktop">
        <iframe
          src="https://www.youtube.com/embed/o3m0qvFAfd4?playlist=o3m0qvFAfd4&modestbranding=1&autohide=1&autoplay=1&controls=0&showinfo=0&mute=1&loop=1&rel=0&frameborder=0"
          allowfullscreen
        ></iframe>
      </div>
      <div class="video-container video-mobile">
        <iframe
          src="https://www.youtube.com/embed/ULR3rxkdxyY?playlist=ULR3rxkdxyY&modestbranding=1&autohide=1&autoplay=1&controls=0&showinfo=0&mute=1&loop=1&rel=0&frameborder=0"
          allowfullscreen
        ></iframe>
      </div>

      <div class="second-line scroll-line"></div>
      <span class="dot dot-one-top"></span>
      <!-- <div class="row mb-4">
        <TypeTile tileName="Quartz" imageUrl="https://i.ibb.co/4K4jf1W/f.png" url="quarzites" />
        <TypeTile tileName="Porcelain" imageUrl="https://i.ibb.co/TMQYXRD/b.png" url="quarzites" />
        <TypeTile tileName="Semi Precious" imageUrl="https://i.ibb.co/dsvh9jn/e.png" url="semi-precious" />
        <TypeTile tileName="Granites & Dolomites" imageUrl="https://i.ibb.co/pQvWM5Y/c.png" url="granite" />
        <TypeTile tileName="Quartzite" imageUrl="https://i.ibb.co/DtWN22R/a.png" url="quarzites" />
        <TypeTile tileName="Marble" imageUrl="https://i.ibb.co/dsvh9jn/e.png" url="marbles" />
      </div> -->
      <div
        class="carousel"
        data-aos="fade-up"
        data-aos-offset="0"
        data-aos-delay="100"
        data-aos-duration="800"
        data-aos-easing="ease-in-out"
        data-aos-once="true"
      >
        <VueSlickCarousel v-bind="settings">
          <TypeTile
            tileName="Quartz"
            imageUrl="https://i.ibb.co/4K4jf1W/f.png"
            url="levante"
          />
          <TypeTile
            tileName="Porcelain"
            imageUrl="https://i.ibb.co/TMQYXRD/b.png"
            url="imperia"
          />
          <TypeTile
            tileName="Semi Precious"
            imageUrl="https://i.ibb.co/DtWN22R/a.png"
            url="inventory/semi-precious"
          />
          <TypeTile
            tileName="Granites & Dolomites"
            imageUrl="https://i.ibb.co/pQvWM5Y/c.png"
            url="inventory/granite-dolomites"
          />
          <TypeTile
            tileName="Quartzite"
            imageUrl="quartzite.png"
            url="inventory/quartzite"
          />
          <TypeTile
            tileName="Marble"
            imageUrl="https://i.ibb.co/dsvh9jn/e.png"
            url="inventory/marble"
          />
        </VueSlickCarousel>
      </div>
      <div class="third-line scroll-line"></div>
      <div class="inspiration mt-4">
        <InspirationSection
          isHome="true"
          mainText="Space"
          firstText="Find your"
        />
      </div>
      <span class="dot dot-two-top"></span>
      <div class="fourth-line scroll-line"></div>
      <div class="container-fluid">
        <div class="collection-container mt-5 mb-5">
          <div class="collection-title">
            <div
              class="featured col ml-2"
              data-aos="fade-up"
              data-aos-offset="0"
              data-aos-delay="0"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
            >
              FEATURED
            </div>

            <div
              class="col collection"
              data-aos="fade-up"
              data-aos-offset="0"
              data-aos-delay="0"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
            >
              COLLECTION
            </div>
          </div>
          <div class="collection-list desktop">
            <div v-for="tile in featuredListFirstRowDesktop">
              <Tile
                :id="tile?.item_code"
                :category_code="tile?.category_code"
                :tileCode="tile?.item_code"
                :tileName="tile?.title"
                :imageUrl="tile?.slab_images"
              />
            </div>
          </div>
          <div class="collection-list desktop">
            <div v-for="tile in featuredListSecondRowDesktop">
              <Tile
                :id="tile?.item_code"
                :category_code="tile?.category_code"
                :tileCode="tile?.item_code"
                :tileName="tile?.title"
                :imageUrl="tile?.slab_images"
              />
            </div>
          </div>

          <div class="collection-list mobile">
            <Tile
              id="1"
              tileCode="Item code #ABC1275"
              tileName="Blue Deep"
              imageUrl="bluedeep.png"
              category_code="QUARTZITE"
            />
            <Tile
              id="2"
              tileCode="Item code #34567"
              tileName="Venatino"
              imageUrl="venatino.png"
              category_code="QUARTZ"
            />
          </div>
          <div class="collection-list mobile">
            <Tile
              id="3"
              tileCode="Item code #34569"
              tileName="Calacatta Michelangelo"
              imageUrl="Michelangelo.png"
              category_code="PORCELAIN"
              class="uneven"
            />
            <Tile
              id="4"
              tileCode="Item code #34511"
              tileName="Explosion"
              imageUrl="explosion.png"
              category_code="QUARTZITE"
            />
          </div>
          <div class="collection-list mobile">
            <Tile
              id="5"
              tileCode="Item code #34522"
              tileName="Pompeii"
              imageUrl="https://i.ibb.co/yy2skRp/5.png"
              category_code="PORCELAIN"
            />
            <Tile
              id="6"
              tileCode="Item code #23410"
              tileName="Calacatta ORO"
              imageUrl="https://i.ibb.co/ChGG9Gg/6.png"
              category_code="PORCELAIN"
            />
          </div>
        </div>
      </div>
      <OurCollection
        collectionText="Our signature quartz collection"
        imageUrl1="l-logo.png"
        imageUrl2="pexel.jpg"
        url="levante"
      />
      <OurCollection
        collectionText="Our signature collection"
        imageUrl1="i-logo.png"
        imageUrl2="imperia-1.png"
        url="imperia"
      />
      <span class="dot dot-three-top"></span>

      <div class="visualizatin-container">
        <div class="fifth-line scroll-line"></div>
        <VisualizeStone />
      </div>
      <div
        class=""
        data-aos="fade-up"
        data-aos-offset="200"
        data-aos-delay="0"
        data-aos-duration="1000"
        data-aos-easing="ease-in-out"
        data-aos-once="true"
      >
        <VisitShowRoom />
      </div>

      <FooterSection />
    </div>
  </u-animate-container>
</template>

<script>
import VueSlickCarousel from "vue-slick-carousel";
// import
import Vue from "vue";
import VueWow from "vue-wow";

// mount with global
Vue.use(VueWow);

// mount with component
import { UAnimateContainer, UAnimate } from "vue-wow";
import { apiEndpoint } from "../../assets/utils";

export default {
  head() {
    return {
      title: "Kiva | Home",
    };
  },
  layout: "default",
  components: { VueSlickCarousel, UAnimateContainer, UAnimate },
  data() {
    return {
      featuredList: null,
      featuredListFirstRowDesktop: [],
      featuredListSecondRowDesktop: [],
      settings: {
        dots: true,
        arrows: false,
        focusOnSelect: true,
        infinite: false,
        speed: 500,
        dotsClass: "slick-dots slickdots",
        slidesToScroll: 2,
        slidesToShow: 6,
        adaptiveHeight: true,
        // "adaptiveHeight": true,
        responsive: [
          {
            breakpoint: 1400,
            settings: {
              slidesToShow: 5,
              dots: true,
            },
          },
          {
            breakpoint: 1160,
            settings: {
              slidesToShow: 4,
              dots: true,
            },
          },
          {
            breakpoint: 930,
            settings: {
              slidesToShow: 3,
              dots: true,
            },
          },
          {
            breakpoint: 680,
            settings: {
              slidesToShow: 2,
              dots: true,
            },
          },
        ],
      },
    };
  },
  created() {
    fetch(apiEndpoint + "auth/login/token/", {
      method: "POST",
      headers: {
        "Content-Type": "application/json",
      },
      body: JSON.stringify({
        username: process.env.account,
        password: process.env.password,
      }),
    })
      .then((res) => res.json())
      .then((data) => {
        // store the posts in the reactive state
        this.token = data.records.token;
        fetch(apiEndpoint + "inventory/stone/v1?featured=true", {
          method: "GET",
          headers: {
            "Content-Type": "application/json",
            Authorization: "Token " + this.token,
          },
        })
          .then((rest) => rest.json())
          .then((result) => {
            console.log(result, "result");
            // store the posts in the reactive state
            this.featuredList = result.stones;
            for (let i = 0; i < this.featuredList.length; i++) {
              if (i < 3) {
                this.featuredListFirstRowDesktop.push(this.featuredList[i]);
              }
            }
            for (let i = 3; i < this.featuredList.length; i++) {
              this.featuredListSecondRowDesktop.push(this.featuredList[i]);
            }
          });
      });
  },
};
</script>

<style>
.header-logo {
  width: inherit;
}

.slickdots {
  bottom: -40px;
}

/* .video-container {
  position: relative;
  padding-bottom: 56.25%;
  /* 16:9 */
/* overflow: hidden;
  height: 0;
  z-index: -1; */
/* } */

.video-container {
  /* height: 100vh; */
  background-color: black;
  position: relative;
  padding-bottom: 56.25%;
  /* 16:9 */
  /* padding-top: 25px; */
  width: 300%;
  /* enlarge beyond browser width */
  left: -100%;
  height: 0;
  position: relative;
  padding-bottom: 56.25%;

  /* 16:9 */
  overflow: hidden;
  height: 0;
  z-index: -1;
  /* center */
}

.x-hidden {
  overflow-x: hidden;
}

.header-shadow {
  position: absolute;
  width: 100%;
  top: 0;
  left: 0;
  /* height: 100%; */
}

.video-container iframe {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  z-index: -1;
}

/* .video-container iframe{
  position: absolute;
  top: -60px;
  left: 0;
  width: 100%;
  height: calc(100% + 120px);
} */
.video-foreground {
  pointer-events: none;
}

.video-desktop {
  display: block;
}

.video-mobile {
  display: none;
}

.ytp-chrome-top .ytp-show-cards-title,
.ytp-title-channel,
iframe .ytp-chrome-top-buttons {
  display: none !important;
}

.slick-prev,
.slick-next {
  display: none;
}

.collection-list {
  display: flex;
  gap: 40px;
  padding: 0 20px;
  justify-content: space-around;
  align-items: center;
}

.mobile {
  display: none;
}

.desktop {
  display: flex;
}

.collection-title {
  padding: 40px;
  padding-left: 60px;
}

.carousel {
  margin-top: -180px;
  width: 100%;
  padding-left: 50px;
}

.collection-container {
  padding: 0 40px;
}

.visualizatin-container {
  margin-top: 100px;
  position: relative;
}

.space-container {
  margin-top: 200px;
}

.text-space {
  margin-left: 100px;
  margin-bottom: 20px;
}

.featured {
  margin-bottom: -60px;
  color: rgb(180, 180, 180);
  letter-spacing: 12px;
  font-size: 18px;
  font-family: Nexa;
  /* margin-left: 20px; */
}

.collection {
  font-size: 180px;
  font-family: Madesaonara;
  color: rgb(10, 10, 10);
  margin-bottom: 20px;
}

.first-line {
  border-left: 2px solid #fff;
  margin-top: calc(65vh + 90px);
  /* top: calc(65vh + 100px); */
}

.scroll-line {
  height: 100%;
  position: absolute;
  margin-left: 40px;
}

.second-line {
  border-left: 2px solid rgb(227, 227, 227);
}

.third-line {
  border-left: 2px solid rgb(227, 227, 227);
  height: 100em;
}

.fourth-line {
  border-left: 2px solid rgb(227, 227, 227);
  height: 140em;
}

.fifth-line {
  border-left: 2px solid rgb(227, 227, 227);
  height: 52.6em;
  top: -190px;
}

.dot,
.dot-white {
  height: 15px;
  width: 15px;
  background-color: rgb(255, 255, 255);
  border-radius: 50%;
  border: 1px solid black;
  display: inline-block;
  margin-bottom: 2px;
  position: relative;
  margin-left: 34px;
  z-index: 1;
}

.dot-white {
  margin-left: 0;
}

.dot-one-top {
  top: 332px;
}

.dot-two-top {
  top: 180px;
}

.dot-three-top {
  top: 160px;
}

.scroll-text {
  writing-mode: vertical-lr;
  letter-spacing: 5px;
  font-size: 10px;
  color: #fff;
  top: 65vh;
  left: 34px;
  font-family: NexaLight;
  position: absolute;
  transform: rotate(180deg);
}

.horizontle-line {
  border-bottom: 1px solid rgb(243, 240, 240);
  line-height: 1px;
  margin-left: 400px;
  bottom: 15px;

  position: relative;
}

@media only screen and (max-width: 1399px) and (min-width: 1280px) {
  .featured {
    font-size: 15px;
    margin-bottom: -50px;
  }

  .first-line {
    /* margin-top: 565px; */
  }

  .scroll-text {
    /* top: 480px; */
  }

  .collection {
    font-size: 150px;
  }

  .fifth-line {
    border-left: 2px solid rgb(227, 227, 227);
    height: 43em;
  }
}

@media only screen and (max-width: 1279px) and (min-width: 1024px) {
  .featured {
    font-size: 16px;
    margin-bottom: -40px;
  }

  .first-line {
    /* margin-top: 400px; */
  }

  .scroll-text {
    /* top: 320px; */
  }

  .collection {
    font-size: 130px;
  }

  .fifth-line {
    border-left: 2px solid rgb(227, 227, 227);
    height: 42.4em;
  }

  .fourth-line {
    border-left: 2px solid rgb(227, 227, 227);
    height: 120em;
  }
}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .mobile {
    display: flex;
  }

  .carousel {
    margin-top: -140px;
    width: 100%;
    padding-left: 50px;
  }

  .desktop {
    display: none;
  }

  .featured {
    margin-top: 100px;
    font-size: 10px;
    margin-bottom: -30px;
  }

  .first-line {
    /* margin-top: 340px; */
  }

  .scroll-text {
    /* top: 250px; */
  }

  .collection {
    font-size: 90px;
  }

  .fifth-line {
    border-left: 2px solid rgb(227, 227, 227);
    height: 46.6em;
  }

  .fourth-line {
    border-left: 2px solid rgb(227, 227, 227);
    height: 160em;
  }
}

@media only screen and (max-width: 767px) {
  .video-desktop {
    display: none;
  }

  .video-mobile {
    display: block;
    height: 100vh;
  }

  .carousel {
    padding-left: 0px;
  }

  .collection-list {
    flex-direction: column;
  }

  .collection-title {
    padding: 20px;
  }

  .collection {
    margin-bottom: 0;
  }

  .featured {
    /* margin-top: 100px; */
    font-size: 8px;
    margin-bottom: -10px;
  }

  .collection-container {
    padding: 0;
  }

  .collection-title {
    padding: 0;
  }

  .first-line {
    display: none;
  }

  .scroll-text {
    display: none;
  }

  .collection {
    font-size: 48px;
  }

  .fifth-line {
    display: none;
  }

  .fourth-line {
    display: none;
  }

  .header-logo {
    width: 100%;
  }

  .scroll-line {
    display: none;
  }

  .dot {
    display: none;
  }
}
</style>
