<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12">
        <NavBarDetail />
      </div>

      <div v-if="tileData" class="container-keva">
        <div class="all-stones mb-4">
          <a :href="'/inventory'">All stones</a>
          <div>>></div>
          <a :href="cateMap[tileData?.category_code]?.name">{{
            tileData?.category_code
          }}</a>
          <div>>></div>
          {{ tileData?.title }}
        </div>
        <div class="row">
          <div class="col-lg-7 col-md-12">
            <div class="row">
              <div class="col-12">
                <div class="name-wrap">
                  <div class="category hide-name-short">
                    Category : {{ tileData?.category_code }}
                  </div>
                  <div class="dover hide-name-short">{{ tileData?.title }}</div>
                  <div class="item-code hide-name-short">
                    ITEM CODE {{ tileData?.item_code }}
                  </div>
                </div>
              </div>
              <div
                class="col-12"
                data-aos="fade-up"
                data-aos-offset="0"
                data-aos-delay="0"
                data-aos-duration="800"
                data-aos-easing="ease-in-out"
                data-aos-once="true"
              >
                <img
                  v-if="space === true"
                  class="product-image"
                  :src="(tileData?.space_images || [])[0]"
                />
                <img
                  v-else
                  class="product-image"
                  :src="(tileData?.slab_images || [])[0]"
                />
              </div>
              <div class="col-12">
                <div class="slab-container">
                  <div class="slab">Slab</div>
                  <b-form-checkbox
                    v-if="(tileData?.space_images || []).length"
                    v-model="space"
                    name="check-button"
                    switch
                  >
                    <span class="space">Space</span>
                  </b-form-checkbox>
                </div>
              </div>
            </div>
          </div>
          <div class="col-lg-5 col-md-12 product-detail-section">
            <div class="category hide-name">
              Category : {{ tileData?.category_code }}
            </div>
            <div class="dover hide-name">{{ tileData?.title }}</div>
            <div class="item-code hide-name">
              ITEM CODE {{ tileData?.item_code }}
            </div>
            <div class="item-desc mt-4 hide-name">
              {{ tileData?.description }}
            </div>
            <a :href="tileData?.erp_link" target="_blank">
              <button class="btn find-dealer hide-name">Live Inventory</button>
            </a>
            <!-- <div class="favourite hide-name"> -->
            <!-- <img src="../../../../static/contact/heart.png" /> -->
            <!-- <i
                v-if="!heartStatus"
                class="fa-regular fa-heart"
                @click="setHeart(true)"
              ></i>
              <i v-else class="fa fa-heart" @click="setHeart(false)"></i>
              &nbsp;Add to favourites
            </div> -->

            <div class="share hide-name">
              Share<span class="ml-3"></span>
              <a
                :href="`https://www.facebook.com/sharer/sharer.php?u=https://kivastone.com/${$route.fullPath}&t=Kiva-stone`"
              >
                <i class="fab fa-facebook-f mr-3"></i>
              </a>
              <!-- <a
                :href="`https://www.instagram.com/?url=https://kivastone.com/${$route.fullPath}`"
                target="_blank"
                rel="noopener"
              >
                <i class="fab fa-instagram mr-3"></i>
              </a> -->
              <a
                :href="`whatsapp://send?text=${encodeURIComponent(
                  `https://kivastone.com/${$route.fullPath}`
                )}`"
                data-action="share/whatsapp/share"
                class="mobile-only"
              >
                <i class="fab fa-whatsapp"></i>
              </a>
            </div>
          </div>
        </div>
      </div>
      <div v-else class="container-keva">
        <div class="loader">
          <img src="../../../../static/kiva-white-dark.gif" />
        </div>
      </div>
      <div v-if="tileData" class="container-fluid container-res">
        <div class="row">
          <div class="col-lg-7 col-md-6 hide-on-large">
            <div class="slab-margin">
              <div class="item-desc-small-screen">
                <div class="item-desc">{{ tileData?.description }}</div>
                <a :href="tileData?.erp_link" target="_blank">
                  <button class="btn find-dealer">Live Inventory</button>
                </a>
                <!-- <div class="favourite">
                  <i
                    v-if="!heartStatus"
                    class="fa-regular fa-heart"
                    @click="setHeart(true)"
                  ></i>
                  <i v-else class="fa fa-heart" @click="setHeart(false)"></i>
                  &nbsp;Add to favourites
                </div> -->

                <div class="share">
                  Share<span class="ml-3"></span>
                  <a
                    :href="`https://www.facebook.com/sharer/sharer.php?u=https://kivastone.com/${$route.fullPath}&t=Kiva-stone`"
                  >
                    <i class="fab fa-facebook-f mr-3"></i>
                  </a>
                  <!-- <a
                    :href="`https://www.instagram.com/?url=https://kivastone.com/${$route.fullPath}`"
                    target="_blank"
                    rel="noopener"
                  >
                    <i class="fab fa-instagram mr-3"></i>
                  </a> -->
                  <a
                    :href="`whatsapp://send?text=${encodeURIComponent(
                      `https://kivastone.com/${$route.fullPath}`
                    )}`"
                    data-action="share/whatsapp/share"
                    class="mobile-only"
                  >
                    <i class="fab fa-whatsapp"></i>
                  </a>
                </div>
              </div>
            </div>
          </div>
          <!-- <div class="col-lg-2 col-md-1"></div> -->
          <div class="col-lg-5 col-md-6 mt-5 hide-small-screen">
            <div class="row">
              <div class="col-12 col-lg-4 mt-4">
                <div class="finish mb-2">Finish Available</div>
                <div class="row">
                  <div
                    v-for="finish in tileData?.finishes"
                    class="col-12 text-color text-margin"
                  >
                    {{ finish }}
                  </div>

                  <!-- <div class="col-4">
                    <span class="text-color">Slab</span>
                  </div>
                  <div class="col-4">
                    <span class="text-color">Space</span>
                  </div> -->
                </div>
              </div>
              <div class="col-12 col-lg-4 mt-4">
                <div class="finish mb-2">Sizes Available</div>
                <div class="row">
                  <!-- <div class="2"> -->
                  <div
                    v-for="(value, key) in (tileData?.stone_sizes || [])[0]"
                    class="col-12 text-color text-margin"
                  >
                    {{ value }}
                  </div>

                  <!-- </div> -->

                  <!-- <div class="col-4">
                    <span class="text-color">Slab</span>
                  </div>
                  <div class="col-4">
                    <span class="text-color">Space</span>
                  </div> -->
                </div>
              </div>
              <div class="col-12 col-lg-4 mt-4">
                <div class="thickness mb-2">Thickness</div>
                <div class="row">
                  <div
                    v-for="(value, key) in tileData?.thickness || []"
                    class="col-12"
                  >
                    <span class="line-thick">{{ value }}</span>
                  </div>
                  <!-- <div class="col-12">
                    <span class="line-thick">
                      <img src="../../../../static/contact/Rectangle-25.png" />
                      2.0cm</span
                    >
                  </div>
                  <div class="col-12">
                    <span class="line-thick"
                      ><img src="../../../../static/contact/Rectangle-26.png" />
                      3.0cm</span
                    >
                  </div> -->
                </div>
              </div>

              <div></div>
            </div>
          </div>
          <div class="col-lg-7 col-md-12 visualizer" @click="pageView()">
            <img
              src="../../../../static/contact/VISULASIER.png"
              class="visualizer-width"
            />
          </div>
          <!-- <div class="col-2 hide-small-screen"></div> -->
        </div>
      </div>
      <div v-else class="container-keva">
        <div class="loader">
          <img src="../../../../static/kiva-white-dark.gif" width="60" />
        </div>
      </div>
      <div class="container-fluid container-res">
        <div class="row">
          <div class="col-12 application">APPLICATIONS</div>

          <div
            v-for="imgo in backImgs"
            class="col-6 col-sm-3 mt-2"
            data-aos="fade-up"
            data-aos-offset="0"
            data-aos-delay="0"
            data-aos-duration="800"
            data-aos-easing="ease-in-out"
            data-aos-once="true"
          >
            <img class="section-image-v2" :src="imgo" />
          </div>
        </div>
      </div>
      <!-- <div class="visualizatin-container">
        <VisualizeStone />
      </div> -->

      <div v-if="tileData?.slab_horizontal_images" class="slab-wrap">
        <div class="slab-details">Slab Details</div>
        <div class="image-slab">
          <!-- <img class="image-slab" :src='(tileData?.slab_horizontal_images || [])[0]' /> -->
          <!-- <v-image-zoom regular='(tileData?.slab_horizontal_images || [])[0]'>
          </v-image-zoom> -->
          <Magnifier :imageUrl="(tileData?.slab_horizontal_images || [])[0]" />
        </div>
      </div>
      <FooterSection />
    </div>
  </div>
</template>

<script>
import { apiEndpoint } from "../../../../assets/utils";

export default {
  head() {
    return {
      title: "Kiva | Product",
    };
  },

  layout: "default",
  data() {
    return {
      heartStatus: false,
      tileData: null,
      space: false,
      backImgs: [],
      cateMap: {
        "GRANITES & DOLOMITES": {
          name: "/inventory/granite-dolomites",
          bannerImage: "granite.png",
          smallIntroText: "OUR FINEST",
          largeIntroText: "GRANITES",
        },
        PORCELAIN: {
          name: "/imperia",
          bannerImage: "granite.png",
          smallIntroText: "OUR FINEST",
          largeIntroText: "GRANITES",
        },
        QUARTZ: {
          name: "/levante",
          bannerImage: "granite.png",
          smallIntroText: "OUR FINEST",
          largeIntroText: "GRANITES",
        },
        QUARTZITE: {
          name: "/inventory/quartzite",
          bannerImage: "quarzite.png",
          smallIntroText: "OUR FINEST",
          largeIntroText: "QUARZITES",
        },
        MARBLE: {
          name: "/inventory/marble",
          bannerImage: "marble.png",
          smallIntroText: "OUR FINEST",
          largeIntroText: "MARBLES",
        },
        "SEMI PRECIOUS": {
          name: "/inventory/semi-precious",
          bannerImage: "precious.png",
          smallIntroText: "OUR EXQUISITE",
          largeIntroText: "SELECTION",
        },
      },
    };
  },
  asyncData({ route, params }) {
    if (process.server) {
      //use route object
      console.log(route.params.slug);
      //directly use params
      console.log(params.slug);
    }
  },
  methods: {
    pageView() {
      location.href = "/visualizer";
    },
    setHeart(status) {
      // const getHeartStatus = (localStorage.getItem('heartStatus')[this.tileData.item_code]);
      localStorage.setItem(
        "heartStatus",
        JSON.stringify({ [this.tileData?.item_code]: status })
      );
      this.heartStatus = status;
    },
  },
  created() {
    console.log(this.$route.params, "paams");
    const category_code = this.$route.params.category;
    console.log(category_code, "category_code");

    console.log(this.$route, "route");

    const stone_name = this.$route.params.id;
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
        fetch(
          apiEndpoint +
            `inventory/stone/v1?category_code=${category_code}&stone_name=${stone_name}`,
          {
            method: "GET",
            headers: {
              "Content-Type": "application/json",
              Authorization: "Token " + this.token,
            },
          }
        )
          .then((rest) => rest.json())
          .then((result) => {
            // store the posts in the reactive state

            this.tileData = result?.stones[0];
            this.backImgs = this.tileData?.application_images;
            console.log(this.tileData, "this.tileData");
            const getHeart = JSON.parse(localStorage.getItem("heartStatus"));
            console.log(getHeart, "here");
            if (!getHeart || !getHeart[this.tileData?.item_code]) {
              localStorage.setItem(
                "heartStatus",
                JSON.stringify({ [this.tileData?.item_code]: false })
              );
            }
            this.heartStatus = JSON.parse(localStorage.getItem("heartStatus"))[
              this.tileData?.item_code
            ];
          });
      });
  },
};
</script>

<style scoped>
.product-image {
  width: 100%;
  /* margin-left: 60px; */
  padding: 40px;
}

.mobile-only {
  display: none;
}

.hide-name {
  display: none;
}

a {
  color: inherit;
}

.hide-on-large {
  display: none;
}

.container-res {
  padding: 0 80px;
}

.slab-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.slab {
  margin-right: 6px;
}

.item-desc-small-screen {
  display: none;
}

.slab-margin {
  /* margin-left: 470px; */
}

.hide-name {
  display: block;
}

.hide-name-short {
  display: none;
}

.visualizatin-container {
  margin: auto;
  margin-bottom: 102px;
  width: 100%;
  margin-top: 100px;
}

.item-name-small-screen {
  display: none;
}

.hide-on-large {
  display: none;
}

.show-on-mobile {
  display: none;
}

.slab-wrap {
  margin: auto;
  width: 100%;
  padding: 0 80px;
}

.section-image {
  width: 100%;
}

.section-image-v2 {
  width: 100%;
}

.col-margin {
  /* margin-right: -20px; */
}

.slab-section {
  /* margin-left: 20%; */
}

.all-stones {
  /* margin-left: 40px; */
  margin-top: 140px;
  margin-bottom: -40px;
  color: #5d5d5d;
  gap: 16px;
  display: flex;
}

.product-detail-section {
  margin-top: 60px;
  /* margin-left: 10px; */
  padding: 10px 20px;
  padding-right: 80px;
}

.category {
  font-size: 12px;
  font-family: Nexa;
  color: #5d5d5d;
  margin-bottom: 10px;
}

.dover {
  font-size: 42px;
  font-family: Nexa;
  color: #212121;
  font-weight: bold;
  margin-bottom: 8px;
}

.item-code {
  font-size: 10px;
  font-family: Nexa;
  color: #acacac;
  /* margin-bottom: 40px; */
  font-weight: bold;
}

.loader {
  width: 100%;
  height: 500px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.loader img {
  width: 100px;
  height: auto;
  align-self: ;
}
.item-desc {
  font-size: 18px;
  font-family: Nexa;
  color: #474747;
}

.find-dealer {
  margin-top: 50px;
  background-color: black;
  color: white;
  padding-left: 70px;
  padding-right: 70px;
  padding-top: 10px;
  padding-bottom: 10px;
}

.favourite {
  font-family: Nexa;
  font-family: 12px;
  margin-top: 50px;
}

.share {
  margin-top: 60px;
  color: #bebebe;
  font-size: 14px;
  font-family: NexaLight;
  text-align: right;
}

.slab {
  /* margin-left: -80px; */
  display: inline-block;
  /* position: absolute; */
  font-size: 14px;
  color: #2a2a2a;
  font-family: Nexa;
}

.space {
  font-size: 14px;
  color: #b5b5b5;
  font-family: Nexa;
}

.finish-section {
  text-align: center;
  margin-top: 60px;
}

.margin-thick {
  margin-left: 200px;
}

.finish {
  font-size: 14px;
  font-weight: bold;
  font-family: Nexa;
  /* margin-right: 240px; */
}

.thickness {
  font-size: 14px;
  font-weight: bold;
  font-family: Nexa;
}

.text-color {
  color: #2a2a2a;
  font-size: 12px;
  font-family: Nexa;
}

.text-margin {
  margin-right: 70px;
}

.line-thick {
  color: #707070;
  /* margin-left: 300px; */
  font-size: 12px;
}

.visualizer {
  margin-top: 50px;
  cursor: pointer;
}

.application {
  font-size: 88px;
  font-family: Madesaonara;
  margin-top: 100px;
}

.slab-details {
  font-size: 22px;
  font-weight: bold;
  font-family: Nexa;
  margin-top: 80px;
  margin-bottom: 40px;
}

.image-slab {
  width: 100%;
  max-height: 380px;
  overflow: hidden;
}

.image-slab img {
  width: 100%;
}

@media only screen and (max-width: 1800px) and (min-width: 1500px) {
  .visualizer-width {
    width: 100%;
    /* margin-left: 120px; */
  }

  .slab-margin {
    margin-left: 370px;
  }

  .image-slab {
    /* width: 94%; */
    /* margin-left: -50px; */
  }

  .section-image {
    width: 97%;
    margin-left: -50px;
  }
}

@media only screen and (max-width: 1499px) and (min-width: 1280px) {
  .visualizer-width {
    width: 100%;

    /* margin-left: 200px; */
  }

  .slab-margin {
    /* margin-left: 330px; */
  }

  .image-slab {
    /* width: 120%;
    margin-left: -190px; */
  }

  .section-image {
    width: 130%;
    margin-left: -80px;
  }

  .col-margin {
    margin-right: 40px;
  }

  .application {
    /* margin-left: -80px; */
  }

  .slab-details {
    /* margin-left: 80px; */
    margin-bottom: 20px;
  }

  .product-detail-section {
    margin-top: 20px;
    /* margin-left: 10px; */
  }
}

@media only screen and (max-width: 1279px) and (min-width: 1024px) {
  .margin-thick {
    margin-left: 200px;
  }

  .slab-margin {
    /* margin-left: 270px; */
  }

  .product-detail-section {
    /* margin-left: 30px; */
    margin-top: -30px;
  }

  .all-stones {
    /* margin-left: 40px; */
  }

  .visualizer {
    /* margin-left: 20px; */
  }

  .visualizer-width {
    /* width: 198%; */
    width: 100%;
    /* margin-left: 0px; */
  }

  .image-slab {
    /* width: 110%;
    margin-left: -60px; */
  }

  .slab-image {
    /* padding: 10px; */
    max-height: 480px;
    overflow: hidden;
  }

  .col-margin {
    margin-right: 5px;
  }

  .section-image {
    width: 120%;
    margin-left: 40px;
  }

  .application {
    /* margin-left: 125px; */
  }

  .slab-details {
    /* margin-left: 80px; */
  }
}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .margin-thick {
    margin-left: 300px;
    margin-top: -220px !important;
  }

  .slab-margin {
    /* margin-left: 170px; */
  }

  .product-detail-section {
    /* margin-left: 100px; */
    margin-top: -30px;
  }

  .all-stones {
    /* margin-left: 40px; */
  }

  .visualizer {
    margin-left: 20px;
  }

  .visualizer-width {
    width: 100%;
    margin-left: 0px;
  }

  .image-slab {
    /* width: 120%;
    margin-left: 80px; */
  }

  .col-margin {
    margin-right: 5px;
  }

  .slab-details {
    margin-left: 0;
  }

  .application {
    /* margin-left: 80px; */
    font-size: 49px;
  }

  .section-image {
    width: 130%;
    margin-left: 80px;
  }

  .item-name-small-screen {
    display: block;
    margin-left: 140px;
    margin-top: 70px;
    margin-bottom: -100px;
  }

  .hide-on-large {
    display: block;
  }

  .item-desc-small-screen {
    display: block;
    /* margin-left: -80px; */
    margin: auto;
    position: relative;
    margin-top: 70px;
  }

  .hide-name {
    display: none;
  }

  .hide-name-short {
    display: block;
  }
}

@media only screen and (max-width: 767px) and (min-width: 320px) {
  .mobile-only {
    display: inline-block;
  }
  .margin-thick {
    margin-left: 0px;
    margin-top: 0px !important;
  }

  .slab-wrap {
    margin: auto;
    width: 100%;
    padding: 0 20px;
  }

  .product-image {
    /* margin-left: 4px; */
    padding: 20px 0;
  }

  .slab-margin {
    margin: auto;
    width: 100%;
  }

  .product-detail-section {
    /* margin-left: 100px; */
    margin-top: -30px;
  }

  .all-stones {
    /* margin-left: 80px; */
    margin-top: 0;
  }

  .dover {
    font-size: 22px;
    font-family: Nexa;
    color: #212121;
    font-weight: bold;
    margin-bottom: 8px;
  }

  .visualizer {
    margin-left: 20px;
  }

  .visualizer-width {
    width: 100%;
    margin-left: 0px;
  }

  .image-slab {
    /* width: 120%; */
    /* margin-left: 60px; */
    /* margin-top: -20px;
    height: 300px; */
  }

  .slab-details {
    /* margin-left: 80px; */
    margin-top: 200px;
    margin-bottom: 20px;
  }

  .application {
    /* margin-left: 80px; */
    font-size: 38px;
  }

  .item-name-small-screen {
    display: block;
    margin-left: 90px;
    margin-top: 70px;
    margin-bottom: -60px;
  }

  .all-stones {
    display: none;
  }

  .item-desc-small-screen {
    display: block;
    /* margin-left: -120px; */
    margin-top: 0px;
  }

  .hide-on-large {
    display: block;
  }

  .item-desc {
    font-size: 12px;
    margin-right: 50px;
  }

  .hide-small-screen {
    display: none;
  }

  .slab-details {
    text-align: center;
    padding-left: 0;
    margin-left: 0;
  }

  .show-on-mobile {
    display: block;
    margin-top: 60px;
    margin-left: 120px;
  }

  .hide-on-large {
    display: block;
  }

  .container-res {
    padding: 0 20px;
  }

  .share {
    margin-left: 180px;
    margin-top: -25px;
  }

  .hide-name-short {
    display: block;
  }

  .hide-name {
    display: none;
  }

  .name-wrap {
    padding-left: 20px;
  }

  .all-stones {
    display: none;
  }

  .slab-image {
    /* padding: 10px; */
    max-height: auto;
    overflow: hidden;
  }
}
</style>
