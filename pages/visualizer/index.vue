<template>
  <div class="wrapper">
    <div class="header-logo"></div>
    <div class="desktop">
      <div class="row">
        <div class="col-xs-10 col-sm-8">
          <div class="intro">
            <div>
              <div>
                <img
                  src="../../static/kiva-white-logo-v2.png"
                  width="140"
                  class=""
                  @click="pageView('home')"
                />
              </div>
              <div class="online mt-4">Online Visualizer</div>
              <br />
              <div class="space">
                See your spaces come to life with our online visualizer. Try a
                slab of your choice and<br />
                ideate your next dream space.
              </div>
              <div class="show-form-in form-position-in">
                <!-- <div class="row">
                <div role="group" class="mr-2">
                  <label for="ambient" class="label-text">Ambient</label>
                  <b-form-input
                    id="ambient"
                    v-model="ambient"
                    class="input-ambient"
                  ></b-form-input>
                </div>
                <div role="group" class="">
                  <label for="country" class="label-text">Country</label>
                  <b-form-input
                    id="country"
                    v-model="country"
                    class="input-ambient"
                  ></b-form-input>
                </div>
              </div> -->
              </div>
            </div>
            <div>
              <div class="footer-logo">
                <a
                  target="_blank"
                  href="https://www.linkedin.com/company/kiva-stone/"
                >
                  <i class="fab fa-linkedin mr-3"></i>
                </a>
                <a
                  target="_blank"
                  href="https://www.facebook.com/kivastonedallas"
                >
                  <i class="fab fa-facebook-f mr-3"></i>
                </a>
                <a
                  target="_blank"
                  href="https://www.instagram.com/kivastonedallas/ "
                >
                  <i class="fab fa-instagram"></i>
                </a>
              </div>
              <div class="row">
                <div class="col-4 info-text">
                  <i class="fa fa-home mr-2"></i>
                  marketing@kivastone.com
                </div>
                <div class="col-8 info-text">
                  <i class="fa fa-phone-volume mr-2"></i>
                  +17739003919
                </div>
              </div>
              <div class="row">
                <div v-for="pageName in info" class="mb-5">
                  <div
                    class="col-1 mt-5 text-uppercase footer-text"
                    @click="pageView(pageName?.toLowerCase())"
                  >
                    {{ pageName }}
                  </div>
                </div>
                <div v-for="name in locations" class="col-12 mb-4 footer-text">
                  <div @click="toUrl(name.url)">{{ name.name }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="col-xs-2 col-sm-4">
          <div class="right-vis">
            <div
              class="enter-btn"
              @click="toUrl('https://visualizer.kivastone.com/')"
            >
              ENTER
            </div>

            <div class="copyright">@ Copyright 2022. Bluedrop</div>

            <!-- <div class="row">
            <div role="group">
              <label for="ambient" class="label-text">Ambient</label>
              <b-form-input
                id="ambient"
                v-model="ambient"
                class="input-ambient"
              ></b-form-input>
            </div>
            <div role="group" class="ml-4">
              <label for="country" class="label-text">Country</label>
              <b-form-input
                id="country"
                v-model="country"
                class="input-ambient"
              ></b-form-input>
            </div>
          </div> -->
          </div>
        </div>
      </div>
    </div>
    <div class="mobile">
      <div class="intro black-wrap">
        <div>
          <img
            src="../../static/kiva-white-logo-v2.png"
            width="140"
            class=""
            @click="pageView('home')"
          />
        </div>
        <div class="text-online">Online Visualizer</div>
        <div
          class="enter-btn"
          @click="toUrl('https://visualizer.kivastone.com/')"
        >
          ENTER
        </div>
        <p>
          See your spaces come to life with our online visualizer. Try a slab of
          your choice and ideate your next dream space.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import { runInContext } from "vm";

export default {
  head() {
    return {
      title: "Kiva | Visualizer",
    };
  },
  data() {
    return {
      locations: [
        {
          name: "Texas",
          url: `
          http://kivastone.stoneprofitsweb.com/`,
        },
        {
          name: "Florida",
          url: `
          http://kivastonefl.stoneprofitsweb.com/`,
        },
        {
          name: "Illinois",
          url: `http://kivastonech.stoneprofitsweb.com/`,
        },

        {
          name: "Ohio",
          url: `https://kivaohio.stoneprofitsweb.com/`,
        },
      ],
      info: ["About", "Stories", "Blog", "Contact"],
      ambient: "",
      country: "",
    };
  },
  methods: {
    pageView(page) {
      location.href = `/${page === "about" ? "experience" : page}`;
    },
    toUrl(url) {
      window.open(url, "_blank");
    },
  },
};
</script>

<style scoped>
.wrapper {
  height: 100vh;
  width: 100%;
  overflow-x: hidden;
}

.form-position-in {
  display: flex;
  padding: 10px;
  margin-top: 40px;
  color: #fff;
}

.black-wrap {
  position: relative;
  z-index: 10;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #fff;
  gap: 20px;
  margin-top: 80px;
}
.black-wrap p {
  text-align: center;
}

.header-logo {
  width: 100%;
  background-image: url("../../static/visulaizer.png");
  background-size: cover;
  background-position: center;
  position: fixed;
  left: 0;
  top: 0;
  min-height: 100vh;
  height: 100%;
}

.text-online {
  font-size: 23px;
  font-family: "NexaLight";
  margin: 20px 0;
}
.sadow-image {
  position: absolute;
  height: 1075px;
}

.margin-logo {
  position: absolute;
  margin-top: 40px;
  margin-left: 100px;
}

.intro {
  background-color: rgba(0, 0, 0, 0.6);
  padding: 30px 20px 20px 40px;
  display: flex;
  justify-content: space-between;
  flex-direction: column;
  align-items: space-between;
  min-height: 100vh;
  height: 100%;
}

.intro img {
  cursor: pointer;
}

.desktop {
  display: block;
}
.mobile {
  display: none;
}

.position-text {
  position: absolute;
  margin-top: 180px;
  margin-left: 100px;
}

.online {
  font-size: 60px;
  font-family: NexaLight;
  letter-spacing: 6px;
  color: white;
}

@media only screen and (max-width: 767px) {
  .online {
    font-size: 24px;
    font-family: Nexa;
    letter-spacing: 6px;
    color: white;
  }
  .desktop {
    display: none;
  }
  .mobile {
    display: block;
  }
  .enter-btn {
    position: relative !important;
    z-index: 100;
    top: auto !important;
    right: auto !important;
  }
  .intro {
    height: 100%;
    min-height: 100%;
  }
}

.show-form {
  display: none;
}

.show-form-in {
  display: block;
}

@media only screen and (min-width: 1120px) {
  .show-form {
    display: block;
  }

  .show-form-in {
    display: none;
  }
}

.space {
  font-size: 14px;
  font-family: Nexa;
  color: white;

  display: inline-block;
}

.footer-logo {
  font-size: 21px;
  margin-top: 120px;
  color: white;
  margin-bottom: 50px;
}

.footer-logo a {
  text-decoration: none;
  color: #fff;
}

.black-wrap p {
  margin-top: 40px;
}

.footer-text {
  font-size: 8px;
  font-family: Nexa;
  color: #e2e2e2;
  letter-spacing: 5px;
  font-weight: lighter;
  cursor: pointer;
}

.form-position {
  /* margin-top: -160px; */
  margin-left: auto;
  /* left: 1400px; */
  z-index: 1;
  padding-top: 120px;
}

.input-ambient {
  width: 150px;
}

.label-text {
  font-size: 14px;
  font-family: Nexa;
  font-weight: 600;
  margin-bottom: 2px;
}

.enter-btn {
  position: absolute;
  padding: 8px 52px;
  top: calc(100vh - 120px);
  margin: auto;
  background: #0f0f0d;
  color: #fff;
  font-family: "Nexa";
  font-size: 12px;
  right: 40px;
  cursor: pointer;
  letter-spacing: 8px;
}

.info-text {
  font-size: 13px;
  font-family: Nexa;
  color: white;
}

.right-vis {
  position: relative;
}

.copyright {
  font-family: DMSans-Regular;
  font-size: 14px;
  position: absolute;
  top: calc(100vh - 40px);
  right: 40px;
  text-align: right;

  color: white;
}
</style>
