<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <div class="intro">
          <NavBar />

          <div class="header-logo">
            <img class="header-shadow" src="../../static/sha.png" />

            <div class="scroll-text">SCROLL</div>
            <div class="first-line scroll-line"></div>

            <!-- <img class="header-logo" src="../../static/contact/banner.png" /> -->
            <!-- <div class="contact-top-banner"></div> -->
            <div class="contact-container">
              <div class="row">
                <div class="col-sm-12 col-md-6">
                  <div class="contact-top-banner-span">
                    Reach out to us

                    <div
                      class="row"
                      data-aos="fade-up"
                      data-aos-offset="200"
                      data-aos-delay="0"
                      data-aos-duration="800"
                      data-aos-easing="ease-in-out"
                      data-aos-once="true"
                    >
                      <div class="col-sm-12 col-md-6">
                        <div class="contact-address">
                          <h2>Kiva Stone Dallas, Texas</h2>
                          11935 N Stemmons Fwy Suite 160, Dallas, TX 75234
                          United States <br /><br />+14699009008
                        </div>
                      </div>
                      <div class="col-sm-12 col-md-6">
                        <div class="contact-address">
                          <h2>Kiva Stone Chicago, Illinois</h2>
                          150 Innovation Dr Suite B, Elk Grove Village, IL
                          60007, United States <br /><br />+17739003919
                        </div>
                      </div>
                      <div class="col-sm-12 col-md-6">
                        <div class="contact-address">
                          <h2>Kiva Stone Deerfield Beach, Florida</h2>
                          600 SW 12th Ave, Deerfield Beach, FL 33442, United
                          States<br /><br />
                          +19548761235
                        </div>
                      </div>
                      <div class="col-sm-12 col-md-6">
                        <div class="contact-address">
                          <h2>Kiva Stone Solon, Ohio</h2>
                          5905 Harper Rd, Solon, OH 44139, United States<br /><br />
                          +14405084555
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
                <div class="col-sm-12 col-md-6">
                  <div class="contact-form-wrapper">
                    <div class="contact-form">
                      <div class="form-group contact-form-group-margins">
                        <div class="form-width">
                          <input
                            type="text"
                            v-model="form.name"
                            class="form-control"
                            id="fname"
                            placeholder="N A M E"
                            name="fname"
                            style="height: 50px"
                            required
                          />
                        </div>
                        <div class="form-width form-width-margin">
                          <input
                            type="email"
                            v-model="form.email"
                            class="form-control"
                            id="email"
                            placeholder="E M A I L"
                            name="email"
                            style="height: 50px"
                            required
                          />
                        </div>
                        <div class="form-group"></div>
                      </div>
                      <div class="form-group">
                        <div class="contact-form-textarea">
                          <textarea
                            class="form-control"
                            v-model="form.query"
                            rows="6"
                            id="comment"
                            placeholder="M E S S A G E"
                            required
                          ></textarea>
                        </div>
                      </div>
                      <div class="form-group form-footer">
                        <div class="">
                          <DropdownCustom
                            :options="['CHICAGO', 'TEXAS', 'FLORIDA', 'OHIO']"
                            default="CHOOSE LOCATION"
                            v-model="form.location"
                            required
                          />
                        </div>
                        <span
                          class="btn-submit-contact-form"
                          @click="submitForm"
                          >REQUEST CALL BACK</span
                        >
                      </div>
                      {{ this.message }}
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="container-fluid">
          <div class="row store">
            <div class="col-12 margin-main-content">
              <div class="carousel">
                <diV class="main-store">
                  <div class="main-flagship-content">OUR FLAGSHIP</div>
                  <div class="main-store-font">STORES</div>
                </diV>
                <VueSlickCarousel v-bind="settings">
                  <div
                    class="main-store-wrap"
                    data-aos="fade-up"
                    data-aos-offset="200"
                    data-aos-delay="0"
                    data-aos-duration="800"
                    data-aos-easing="ease-in-out"
                    data-aos-once="true"
                  >
                    <a
                      href="https://maps.app.goo.gl/2NYXUA2XU38vXbvKA?g_st=iw"
                      target="_blank"
                    >
                      <img
                        src="../../static/contact/DALLAS.png"
                        class="main-store-dallas"
                      />
                      <div class="store-text">DALLAS-TEXAS</div>
                    </a>
                  </div>
                  <div
                    class="main-store-wrap"
                    data-aos="fade-up"
                    data-aos-offset="200"
                    data-aos-delay="200"
                    data-aos-duration="800"
                    data-aos-easing="ease-in-out"
                    data-aos-once="true"
                  >
                    <a
                      href="https://maps.app.goo.gl/huCNPwJcB5k8xMQ6A?g_st=iw"
                      target="_blank"
                    >
                      <img src="../../static/contact/TEXAS.png" class="texas" />
                      <div class="store-text">DEERFIELD-FLORIDA</div>
                    </a>
                  </div>
                  <div
                    class="main-store-wrap"
                    data-aos="fade-up"
                    data-aos-offset="200"
                    data-aos-delay="400"
                    data-aos-duration="800"
                    data-aos-easing="ease-in-out"
                    data-aos-once="true"
                  >
                    <a
                      href="https://maps.app.goo.gl/m8ZQxcbJExt83MsPA?g_st=iw"
                      target="_blank"
                    >
                      <img
                        src="../../static/contact/DENVER.png"
                        class="denver"
                      />
                      <div class="store-text">CHICAGO-ILLINOIS</div>
                    </a>
                  </div>
                  <div
                    class="main-store-wrap"
                    data-aos="fade-up"
                    data-aos-offset="200"
                    data-aos-delay="600"
                    data-aos-duration="800"
                    data-aos-easing="ease-in-out"
                    data-aos-once="true"
                  >
                    <a
                      href="https://maps.app.goo.gl/7zFP1QupgnrWQQVH8?g_st=iw"
                      target="_blank"
                    >
                      <img src="../../static/ohio.png" class="newyork" />
                      <div class="store-text">SOLON-OHIO</div>
                    </a>
                  </div>
                </VueSlickCarousel>
              </div>

              <!-- <div class="wrap-store">
                <div class="main-store">
                  <div class="main-store-font">STORES</div>
                </div>
                <diV class="main-store-wrap">
                  <img src="../../static/contact/DALLAS.png" class="main-store-dallas" />
                  <div class="dstore-text">DALLAS</div>
                </div>
                <diV class="main-store-wrap">
                  <img src="../../static/contact/TEXAS.png" class="texas" />
                  <div class="store-text">TEXAS</div>
                </div>
                <diV class="main-store-wrap">
                  <img src="../../static/contact/DENVER.png" class="denver" />
                  <div class="dstore-text">DENVER</div>
                </div>
                <diV class="main-store-wrap">
                  <img src="../../static/contact/NEWYORK.png" class="newyork" />
                  <div class="nestore-text">NEW YORK</div>
                </div>
                <div class="main-store-wrap">
                  <img src="../../static/contact/VEGAS.png" class="vegas" />
                  <div class="store-text">VAGAS</div>
                </div>
              </div> -->
            </div>
          </div>
        </div>
      </div>
      <div
        class="locator"
        data-aos="fade-up"
        data-aos-offset="200"
        data-aos-delay="0"
        data-aos-duration="800"
        data-aos-easing="ease-in-out"
        data-aos-once="true"
      >
        <div class="locator-map">AREAS WE SERVE</div>
        <img src="../../static/contact-space.png" />
        <!-- <div class="btn-location">SEE LOCATIONS</div> -->
        <div class="location-text">
          <span>MICHIGAN</span>
          <span>INDIANA</span>
          <span>MINNEAPOLIS</span>
          <span>MILWAUKEE</span>
          <span>MADISON</span>
          <span>ORLANDO</span>
          <span>PALM BEACH</span>
          <span>TAMPA</span>
          <span>MIAMI</span>

          <span>COLUMBUS</span>

          <span>AUSTIN</span>
          <span>MISSOURI</span>
        </div>
      </div>
      <FooterSection />
    </div>
  </div>
</template>
<script>
import VueSlickCarousel from "vue-slick-carousel";
import DropdownCustom from "../../components/DropdownCustom.vue";

export default {
  layout: "default",
  head() {
    return {
      title: "Kiva | Contact",
    };
  },

  components: { VueSlickCarousel, DropdownCustom },
  created() {
    fetch("https://api.kivastone.com/" + "auth/login/token/", {
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
        this.token = data.records.token;
      });
  },
  methods: {
    submitForm() {
      if (
        !this.form.name ||
        !this.form.email ||
        !this.form.query ||
        !this.form.location
      ) {
        return null;
      }
      const headers = {
        Authorization: "Token " + this.token,
        "Content-Type": "application/json",
      };
      this.message = "";

      // Make the POST request using fetch API or Axios
      fetch("https://api.kivastone.com/inventory/lead/submit/", {
        method: "POST",
        headers,
        body: JSON.stringify(this.form),
      })
        .then((response) => {
          if (response.ok) {
            // Handle successful response
            this.form = {};
            this.message = "Request Recieved Successfully!";
            setTimeout(() => {
              this.message = "";
            }, 3000);
          } else {
            // Handle error response
            console.error("Form submission failed");
            this.message = "Something Went Wrong!";
          }
        })
        .catch((error) => {
          // Handle network errors
          console.error("Network error:", error);
        });
    },
  },
  data() {
    return {
      form: {
        name: "",
        email: "",
        query: "",
        location: "",
      },
      message: "",
      settings: {
        dots: true,
        arrows: false,
        focusOnSelect: true,
        infinite: false,
        speed: 500,
        slidesToScroll: 2,
        slidesToShow: 4,
        adaptiveHeight: true,
        // "adaptiveHeight": true,
        responsive: [
          {
            breakpoint: 1400,
            settings: {
              slidesToShow: 4,
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
      backImgs: [
        "/Users/avinashsingh/projects/kiva-ui/static/contact/banner.png",
        "../../static/contact/TEXAS.png",
        "../../static/contact/DENVER.png",
        "../../static/contact/NEWYORK",
        "../../static/contact/VEGAS.png",
      ],
    };
  },
};
</script>

<style scoped>
.contact-top-banner {
  font-family: Nexa;
  position: absolute;
  /* margin-top: -250px; */
  margin-left: 50px;
  font-size: 52px;
  color: white;
  line-height: 50px;
}

.contact-container {
  padding: 0 20px;
  padding-top: 320px;
  width: 100%;
}

.contact-address {
  background-color: #000000;
  padding: 15px 20px;
  font-size: 11px;
  margin-top: 10px;
  border-bottom: 4px solid #8b8b8b;
  color: #e9e9e9;
  line-height: 16px;
  min-height: 140px;
}

.contact-address h2 {
  font-family: "NexaBold";
  font-size: 14px;
  color: #e9e9e9;
  margin-bottom: 20px;
}

.store {
  margin-top: 180px;
}

.location-text {
  display: flex;
  max-width: 890px;
  width: 100%;
  margin: auto;
  /* left: 0;
  right: 0; */
  font-size: 12px;
  position: absolute;
  top: 35%;
  color: #fff;
  font-family: NexaBold;
  flex-wrap: wrap;
  justify-content: center;
  padding: 20px 10px;
}

.location-text span {
  padding: 5px 15px;
  letter-spacing: 10px;
}

.newyork img {
  height: 100% !important;
  width: none;
}

.store-text {
  position: absolute;
  width: calc(100% - 20px);
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  background-color: rgba(0, 0, 0, 0.8);
  text-align: center;
  color: #fff;
  display: flex;
  letter-spacing: 10px;
  font-size: 12px;
  font-size: NexaBold;
  align-items: center;
  justify-content: center;
  padding-top: 2px;
  padding-left: 12px;
}

.form-footer {
  display: flex;
  justify-content: space-between;
}

.header-logo {
  width: 100%;
  background-image: url("../../static/contact/banner.png");
  background-size: cover;
  background-position: center;
  height: 75vh;
  position: relative;
  z-index: 0;
}

.intro {
  min-height: 420px;
  position: relative;
}

.intro .header-logo {
  width: 100%;
}

.main-store-wrap {
  position: relative;
  display: inline-block;
  overflow: hidden;
  min-width: 120px;
  padding-right: 20px;
}

.main-store-wrap img {
  width: 100%;
  height: 100%;
}

.carousel {
  gap: 4px;
  padding: 0 80px;
}

.contact-top-banner-span {
  font-family: Nexa;
  /* position: absolute; */
  /* margin-top: -250px; */
  padding-left: 115px;
  font-size: 52px;
  color: white;
  line-height: 50px;
}

.wrap-store {
  display: flex;
  gap: 4px;
  align-self: auto;
}

.contact-form {
  padding: 20px 40px;
}

.contact-form-wrapper {
  background-color: #ffffff;
  /* margin-top: -200px; */
  /* position: relative; */
  border: solid 1px #dee5eb63;
  box-shadow: 1px 1px #959595;
}

.sub-heading {
  font-family: Nexa;
}

.heading {
  font-family: Madesaonara;
}

.contact {
  padding: 4%;
  height: 400px;
}

.col-md-3 {
  background: #ff9b00;
  padding: 4%;
  border-top-left-radius: 0.5rem;
  border-bottom-left-radius: 0.5rem;
}

.contact-form-group-margins {
  margin-top: 20px;
  display: flex;
}

.contact-form label {
  font-weight: 600;
}

.contact-form-textarea {
  width: 100%;
}

.contact-form-textarea textarea {
  padding-top: 12px;
  font-size: 12px;
}

.contact-form-textarea textarea::placeholder {
  color: 949494;
}

.form-width {
  width: 50%;
}

.form-width input {
  width: 100%;
  font-size: 12px;
}

.row-margin-top-200px {
  margin-top: 200px;
}

.form-width-margin {
  margin-left: 20px;
}

.btn-submit-contact-form {
  background-color: black;
  border-radius: 1px;
  color: white;
  display: block;
  /* width: 260px; */
  padding: 0 20px;
  height: 38px;
  /* padding: 13px 1px 0px 53px; */
  font-family: Nexa;
  text-align: center;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 12px;
  font-family: NexaBold;
  letter-spacing: 6px;
  border-radius: 2px;
  cursor: pointer;
}

.contact-form button {
  background: #25274d;
  color: #fff;
  font-weight: 600;
  width: 25%;
}

.contact-form button:focus {
  box-shadow: none;
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
  margin-left: 55px;
  bottom: 0;
}

.scroll-text {
  writing-mode: vertical-lr;
  letter-spacing: 5px;
  font-size: 10px;
  color: white;
  top: 280px;
  left: 49px;
  position: absolute;
  transform: rotate(180deg);
}

.header-shadow {
  position: absolute;
  width: 100%;
  top: 0;
  left: 0;
  /* height: 100%; */
  /* z-index: 1; */
}

.margin-main-content {
  /* padding-left: 230px; */
  padding: 0 40px;
  margin-top: 40px;
  margin-bottom: 100px;
}

.main-flagship {
  position: absolute;
  margin-top: -140px;
}

.main-flagship-content {
  font-size: 18px;
  letter-spacing: 9px;
  margin-bottom: -32px;
}

.main-store {
  /* position: absolute; */
  margin-bottom: -120px;
  z-index: 1;
  position: relative;
  font-family: "Nexa";
}

.main-store-font {
  font-size: 160px;
  font-family: "Madesaonara";
}

.main-store-dallas {
  height: 600px;
  width: 258px;
}

.locator {
  width: 100%;
  margin-bottom: -48px;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  min-height: 220px;
  justify-content: center;
  overflow: hidden;
}

.locator-map {
  position: absolute;
  color: #000;
  padding: 9px 16px 4px 0px;
  width: 100%;
  letter-spacing: 5px;
  font-size: 70px;
  font-family: Nexa;
  left: 0;
  top: 30%;
  transform: translateY(-50%);
  margin: auto;
  text-align: center;
  font-size: 32px;
  right: 0;
}

.btn-location {
  position: absolute;
  color: black;
  padding: 14px 25px 9px 44px;
  width: 240px;
  letter-spacing: 4px;
  font-size: 12px;
  background-color: white;
  font-family: Nexa-Trial;
  font-weight: bold;
  border-radius: 2px;
  top: 22%;
}

.locator img {
  width: 100%;
}

@media only screen and (max-width: 1384px) {
  .form-footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .form-footer div {
    margin-bottom: 10px;
    width: 100%;
  }
}

@media only screen and (min-width: 768px) and (max-width: 1120px) {
  .contact-container {
    padding: 0 20px;
    /* position: absolute; */
    padding-top: 280px;
    width: 100%;
  }

  .contact-top-banner-span {
    font-size: 40px;
  }
}

@media only screen and (max-width: 767px) and (min-width: 360px) {
  .store {
    margin-top: 260px;
  }

  .carousel {
    gap: 4px;
    padding: 0 20px;
  }

  .btn-submit-contact-form {
    font-size: 10px;
  }

  .main-store-font {
    font-size: 18vw;
    margin: 0;
  }

  .main-flagship-content {
    margin-bottom: 0;
  }

  .main-store {
    margin-bottom: -20px;
    text-align: center;
  }

  .scroll-text,
  .first-line {
    display: none;
  }

  .contact-top-banner-span {
    padding-left: 0;
    font-size: 32px;
    color: white;
    line-height: 53px;
  }

  .contact-container {
    padding: 0 20px;
    /* position: absolute; */
    padding-top: 220px;
    width: 100%;
  }

  .location-text {
    font-size: 10px;
  }

  .locator img {
    height: 420px;
    width: auto;
  }

  .store-text {
    font-size: 10px;
    text-align: center;
  }

  .margin-main-content {
    /* padding-left: 230px; */
    padding: 0 20px;
    margin-top: 488px;
    margin-bottom: 100px;
  }
}
</style>
