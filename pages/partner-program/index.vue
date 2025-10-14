<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <Banner
          title="OUR EXCLUSIVE PARTNER"
          description="PROGRAMME"
          banner="partner.png"
        />

        <div class="container-fluid">
          <div class="row flex-col">
            <div
              class="col-12 text-center our-sourcing"
              data-aos="fade-up"
              data-aos-offset="0"
              data-aos-delay="0"
              data-aos-duration="1000"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
            >
              Work with Kiva and discover an ocean of opportunities
            </div>
            <div
              class="col-12 text-center philosophy-context"
              data-aos="fade-up"
              data-aos-offset="0"
              data-aos-delay="0"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
            >
              We at Kiva stone source the finest and the most exquisite stones
              from around the world for you to curate your dream space. Quality
              and excellence is in our DNA and every slab that ships from our
              stores is a testament to the attention to detail of our curators.
            </div>
          </div>
        </div>

        <div
          class="banner"
          :style="{
            'background-image': `url(${require(`@/static/work.png`)})`,
          }"
        >
          <!-- <img class="header-banner" src="../../static/work.png" /> -->
          <div class="text-center legacy">
            See how it works
            <button class="btn explore-more-button" @click="pageView()">
              EXPLORE MORE
            </button>
          </div>
        </div>

        <div class="container-fluid">
          <div class="collabrate-container">
            <div class="row">
              <div class="col-12 text-center collabrate">
                We collabrate with
              </div>

              <div
                class="col-xs-12 col-sm-6 col-lg-4 mt-4 text-center"
                data-aos="fade-in"
                data-aos-offset="200"
                data-aos-delay="0"
                data-aos-duration="800"
                data-aos-easing="ease-in-out"
                data-aos-once="true"
              >
                <img src="../../static/partner/designer.jpg" />
                <div class="work-with-name text-center">DESIGNERS</div>
              </div>
              <div
                class="col-xs-12 col-sm-6 col-lg-4 mt-4 text-center"
                data-aos="fade-in"
                data-aos-offset="200"
                data-aos-delay="0"
                data-aos-duration="800"
                data-aos-easing="ease-in-out"
                data-aos-once="true"
              >
                <img src="../../static/partner/architech.jpg" />
                <div class="work-with-name">ARCHITECTS</div>
              </div>
              <div
                class="col-xs-12 col-sm-6 col-lg-4 mt-4 text-center"
                data-aos="fade-in"
                data-aos-offset="200"
                data-aos-delay="0"
                data-aos-duration="800"
                data-aos-easing="ease-in-out"
                data-aos-once="true"
              >
                <img src="../../static/partner/fabricator.jpg" />
                <div class="work-with-name">FABRICATORS</div>
              </div>

              <div
                class="col-xs-12 col-sm-6 col-lg-4 mt-4 text-center"
                data-aos="fade-in"
                data-aos-offset="200"
                data-aos-delay="0"
                data-aos-duration="800"
                data-aos-easing="ease-in-out"
                data-aos-once="true"
              >
                <img src="../../static/partner/retailor.jpg" />
                <div class="work-with-name">RETAILERS</div>
              </div>
              <div
                class="col-xs-12 col-sm-6 col-lg-4 mt-4 text-center"
                data-aos="fade-in"
                data-aos-offset="200"
                data-aos-delay="0"
                data-aos-duration="800"
                data-aos-easing="ease-in-out"
                data-aos-once="true"
              >
                <img src="../../static/partner/realtor.png" />
                <div class="work-with-name">REALTORS</div>
              </div>
              <div
                class="col-xs-12 col-sm-6 col-lg-4 mt-4 text-center"
                data-aos="fade-in"
                data-aos-offset="200"
                data-aos-delay="0"
                data-aos-duration="800"
                data-aos-easing="ease-in-out"
                data-aos-once="true"
              >
                <img src="../../static/partner/builder.jpg" />
                <div class="work-with-name">BUILDERS</div>
              </div>
            </div>
          </div>
        </div>
        <div class="container-fluid">
          <div class="row">
            <div class="col text-center sign-up">
              <div class="line"></div>
              <div class="sign-up-today">SIGN UP TODAY</div>
              <form @submit.prevent="submitForm">
                <div class="row mt-5">
                  <div class="col-12 col-md-3 label-text">
                    <label for="name">NAME</label>
                  </div>
                  <div class="col-12 col-md-8">
                    <b-input
                      class="input-field"
                      id="name"
                      v-model="form.name"
                    />
                  </div>
                </div>
                <div class="row mt-4">
                  <div class="col-12 col-md-3 label-text">
                    <label for="email">EMAIL</label>
                  </div>
                  <div class="col-12 col-md-8">
                    <b-input
                      class="input-field"
                      id="email"
                      v-model="form.email"
                    />
                  </div>
                </div>
                <div class="row mt-4">
                  <div class="col-12 col-md-3 label-text">
                    <label for="company">COMPANY</label>
                  </div>
                  <div class="col-12 col-md-8">
                    <b-input
                      class="input-field"
                      id="company"
                      v-model="form.company"
                    />
                  </div>
                </div>
                <div class="row mt-4">
                  <div class="col-12 col-md-3 label-text">
                    <label for="address">ADDRESS</label>
                  </div>
                  <div class="col-12 col-md-8">
                    <b-input
                      class="input-field"
                      id="address"
                      v-model="form.address"
                    />
                  </div>
                </div>
                <div class="row mt-4">
                  <div class="col-12 col-md-3 label-text">
                    <label for="phone">PHONE</label>
                  </div>
                  <div class="col-12 col-md-8">
                    <b-input
                      class="input-field"
                      id="phone"
                      v-model="form.phone"
                    />
                  </div>
                </div>
                <div class="row mt-4">
                  <div class="col-12 col-md-3 label-text">
                    <label for="role">ROLE</label>
                  </div>
                  <div class="col-12 col-md-8">
                    <b-input
                      class="input-field"
                      id="role"
                      v-model="form.role"
                    />
                  </div>
                </div>
                <div class="row">
                  <div class="col-12 text-center">
                    <button class="btn request-sign-up" type="submit">
                      REQUEST SIGN UP
                    </button>
                  </div>
                  <div class="col-12 text-center message">
                    {{ message }}
                  </div>
                </div>
              </form>
            </div>
          </div>
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
      title: "Kiva | Partner Program",
    };
  },
  data() {
    return {
      form: {
        name: "",
        email: "",
        company: "",
        address: "",
        phone: "",
        role: "",
      },
      message: "",
    };
  },
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
    async submitForm() {
      try {
        const headers = {
          Authorization: "Token " + this.token,
          "Content-Type": "application/json",
        };
        const response = await fetch(
          "https://api.kivastone.com/inventory/partner/add/",
          {
            method: "POST",
            headers,
            body: JSON.stringify(this.form),
          }
        );

        if (response.ok) {
          // Handle success, e.g., show a success message
          const responseData = await response.json();
          this.form = {
            name: "",
            email: "",
            company: "",
            address: "",
            phone: "",
            role: "",
          };
          console.log("Response:", responseData);
          this.message = responseData.message;
        } else {
          // Handle error, e.g., show an error message
          console.error("Error:", response.statusText);
          this.message = "Something Went Wrong!";
        }
        setTimeout(() => {
          this.message = "";
        }, 3000);
      } catch (error) {
        // Handle errors, e.g., show an error message
        console.error("Error:", error);
        this.message = "Something Went Wrong!";
        setTimeout(() => {
          this.message = "";
        }, 3000);
      }
    },
    pageView() {
      location.href = `/partner-program-working`;
    },
  },
};
</script>

<style scoped>
.header-logo {
  width: 100%;
  background-image: url("../../static/partner.png");
  background-size: cover;
  background-position: center;
  height: 75vh;
  position: relative;
}

img {
  width: 100%;
}

.flex-col {
  flex-direction: column;
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

.collabrate-container {
  position: relative;
  margin: auto;
  max-width: 1120px;
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

.header-banner {
  width: 100%;
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

.banner {
  position: relative;
  margin-top: 40px;
  background-size: cover;
  width: 100%;
  height: 320px;
  background-position: center;
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
  margin-top: 200px;
  margin-bottom: 50px;
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

.our-sourcing {
  font-size: 50px;
  margin: auto;
  font-family: NexaLight;
  margin-top: 60px;
  line-height: 60px;
  max-width: 980px;
}

.philosophy-context {
  max-width: 980px;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
}

.philosophy-context {
  font-size: 16px;
  font-family: NexaLight;
  margin-top: 50px;
  margin-bottom: 50px;
}

.view-slab-button {
  color: rgb(142, 140, 140);
  background-color: none;
  padding: 5px;
  width: 220px;
  margin-left: -20px;
  margin-top: 80px;
  border: 1px solid rgb(142, 140, 140);
  font-size: 12px;
  font-family: Nexa;
  letter-spacing: 3px;
}

.title {
  font-size: 50px;
  font-family: Nexa;
  font-weight: bold;
  margin-top: 60px;
  letter-spacing: 30px;
}

.content {
  font-size: 16px;
  font-family: Nexa;
  margin-top: 30px;
  color: rgb(142, 140, 140);
}

.country-image {
  padding-left: 100px;
  height: 400px;
  width: 900px;
}

.country-two-image {
  padding-right: 100px;
  height: 400px;
  width: 900px;
}

.left-element {
  padding-left: 120px;
  padding-top: 20px;
}

.right-elemet {
  padding-left: 100px;
}

.top-margin {
  margin-top: 100px;
}

.legacy {
  font-size: 30px;
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

.message {
  color: #fff;
  margin-top: 10px;
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
  /* top: 120px; */
}

.collabrate {
  font-size: 50px;
  font-family: NexaLight;
  /* margin-bottom: 70px; */
  margin-top: 70px;
  margin-bottom: 40px;
}

.work-with-name {
  color: #a2a2a2;
  font-size: 18px;
  letter-spacing: 15px;
  margin-top: 30px;
}

.sign-up {
  background-color: #888888;
  border-top: 1px solid white;
  margin: auto;
  margin-top: 40px;
  margin-bottom: -48px;
  /* margin-left: 380px; */
  /* margin-right: 220px; */
  width: 100%;
  max-width: 780px;
  padding: 0 40px;
  padding-bottom: 100px;
}

.sign-up-today {
  font-size: 32px;
  font-family: NexaLight;
  color: white;
  letter-spacing: 10px;
  padding-top: 20px;
}

.line {
  margin-top: 10px;
  border-top: 2px solid white;
  /* margin-left: -20px; */
  /* margin-right: -20px; */
  margin-bottom: 20px;
}

.label-text {
  font-size: 22px;
  font-family: NexaLight;
  color: white;
  top: 6px;
  letter-spacing: 6px;
  text-align: left;
}

.input-field {
  background-color: #888888;
  border-right: none;
  border-left: none;
  border-top: none;
  border-radius: 0px;
  border-bottom: 1px solid #d2d2d2;
  color: #fff;
}

input.input-field:active,
input.input-field:focus {
  outline: none;
  box-shadow: none;
}

.request-sign-up {
  color: black;
  background-color: rgb(244, 244, 244);
  padding: 12px;
  width: 220px;
  margin-top: 40px;
  /* margin-left: -20px; */
  border: 1px solid rgb(142, 140, 140);
  font-size: 12px;
  font-family: Nexa;
  letter-spacing: 3px;
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

  .right-elemet {
    padding-left: 0;
  }
}

@media only screen and (max-width: 767px) {
  .header-shadow {
    width: 100%;
  }

  .collabrate {
    font-size: 30px;
  }

  .carousel {
    margin-top: -40px;
    width: 100%;
    padding-left: 20px;
  }

  .search-mobile-tab {
    display: block;
  }

  .our-sourcing {
    font-size: 26px;
    line-height: 32px;
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

  .label-text {
    font-size: 12px;
    font-family: NexaLight;
    color: white;
    top: 6px;
    letter-spacing: 6px;
    text-align: center;
  }

  .sign-up-today {
    font-size: 12px;
  }

  .left-element {
    padding: 10px;
  }

  .btn.request-sign-up {
    font-size: 12px;
  }

  .right-elemet {
    padding: 10px;
  }
}
</style>
