<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <NavBar />

        <!--
        <div class="scroll-text">SCROLL</div>
        <div class="first-line scroll-line"></div> -->
        <div class="intro">
          <img class="header-shadow" src="../../static/sha.png" />

          <div class="vertical-line-box">
            <div class="vertical-text">SCROLL</div>
            <div class="vertical-line"></div>
          </div>
          <div class="container-fluid">
            <div
              class="row"
              data-aos="fade-up"
              data-aos-offset="200"
              data-aos-delay="0"
              data-aos-duration="1000"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
            >
              <div class="nav-small-text col-12 mb-4 text-center">
                OUR EXQUISITE PORCELAIN COLLECTION
              </div>
              <div class="nav-experience-text col-12 text-center">
                SOURCED FROM THE FINEST QUARRIES AROUND THE WORLD
              </div>
            </div>
          </div>
          <div class="header-logo"></div>
        </div>
        <!-- <div class="second-line scroll-line"></div>
        <span class="dot dot-one-top"></span> -->

        <div class="blue-bg">
          <!-- <button class="btn design-button">SEE ALT DESIGN</button> -->
          <div class="line"></div>
          <img
            class="logo"
            src="../../static/i-logo.png"
            data-aos="fade-in"
            data-aos-offset="0"
            data-aos-delay="0"
            data-aos-duration="1000"
            data-aos-easing="ease-in-out"
            data-aos-once="true"
            height="100%"
          />
        </div>
        <div class="inventory-list container-fluid">
          <div class="row mb-5 slab-section">
            <div class="col-lg-3 px-5 d-none d-lg-block">
              <!-- <button class="view-slab-button">VIEW ALL SLABS</button> -->
              <div class="search-input">
                <div class="input-group">
                  <b-input
                    v-on:keyup.enter="submitSearch"
                    class="form-control py-2 border-right-0 border-top-0 border-left-0 border"
                    v-model="search"
                    placeholder="S E A R C H"
                  />
                  <span class="input-group-append" @click="submitSearch()">
                    <div
                      class="input-group-text bg-transparent border-right-0 border-top-0 border-left-0"
                    >
                      <i class="fa fa-search search-icon"></i>
                    </div>
                  </span>
                </div>
              </div>
              <Filters
                @callback-triggered="handleEvent"
                @callback-finish="handleFinish"
                :categoryCode="categoryCode"
              />
            </div>
            <div class="col-lg-9 col-md-12">
              <div class="row">
                <div v-if="tileList == null" class="preloader">
                  <img src="../../static/kiva-white-dark.gif" />
                </div>
                <div v-else-if="!tileList.length">No Results</div>
                <div
                  v-else
                  v-for="tile in tileList"
                  class="col-xl-4 col-lg-6 col-md-6 col-sm-12"
                >
                  <InventoryTile
                    :id="tile?.item_code"
                    :category_code="tile?.category_code"
                    :tileCode="tile?.item_code"
                    :tileName="tile?.title"
                    :imageUrl="tile?.slab_images"
                  />
                </div>
              </div>
              <div class="mt-5 pagination-wrapper">
                <div class="">
                  <div class="form-group form-inline per-page">
                    <!-- <span>SHOWING:</span> -->

                    <b-dropdown
                      toggle-class="dropdown-perpage"
                      variant="none"
                      id="dropdown"
                      class="page-list m-md-2"
                      :text="'SHOWING: ' + perPage"
                    >
                      <b-dropdown-item
                        v-for="option in perPageOption"
                        :selected="perPage"
                        :value="option.value"
                        @click="perPageChange(option.text)"
                        >{{ option.text }}
                      </b-dropdown-item>
                    </b-dropdown>
                  </div>
                </div>
                <div class="text-right">
                  <div class="pagination">
                    <span
                      class="fas fa-arrow-left arrow"
                      :class="parseInt(currentPage) === 1 ? 'not-active' : ''"
                      @click="page(-1)"
                    >
                    </span>
                    <span class="page-number" v-for="i in pageCount">
                      <p
                        :class="i !== parseInt(currentPage) ? 'not-active' : ''"
                        @click="changePage(i)"
                      >
                        {{ i }}
                      </p>
                    </span>
                    <span
                      class="fas fa-arrow-right button-arrow"
                      :class="
                        parseInt(currentPage) === pageCount ? 'not-active' : ''
                      "
                      @click="page(+1)"
                    >
                    </span>
                  </div>
                </div>
              </div>
            </div>
          </div>
          <div class="search-mobile-tab">
            <!-- <button class="view-slab-button-mob">VIEW ALL SLABS</button> -->
            <div class="search-input">
              <div class="input-group">
                <b-input
                  v-on:keyup.enter="submitSearch"
                  class="form-control py-2 border-right-0 border-top-0 border-left-0 border"
                  v-model="search"
                  placeholder="S E A R C H"
                />
                <span class="input-group-append" @click="submitSearch()">
                  <div
                    class="input-group-text bg-transparent border-right-0 border-top-0 border-left-0"
                  >
                    <i class="fa fa-search search-icon"></i>
                  </div>
                </span>
              </div>
            </div>
            <Filters
              @callback-triggered="handleEvent"
              @callback-finish="handleFinish"
              :categoryCode="categoryCode"
            />
          </div>
        </div>
        <div class="visualizatin-container">
          <VisualizeStone />
        </div>
        <ImperiaFooterSection />
      </div>
    </div>
  </div>
</template>

<script>
import { apiEndpoint } from "../../assets/utils";
import ImperiaFooterSection from "../../components/ImperiaFooterSection.vue";

export default {
  layout: "default",
  head() {
    return {
      title: "Kiva | Imperia",
    };
  },
  data() {
    return {
      categoryCode: "Porcelain",
      tileList: null,
      search: "",
      currentPage: 1,
      perPage: 12,
      pageList: [],
      pageCount: 0,
      fullTileList: [],
      perPageOption: [],
      filter: [],
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
        fetch(apiEndpoint + "inventory/stone/v1?category_code=Porcelain", {
          method: "GET",
          headers: {
            "Content-Type": "application/json",
            Authorization: "Token " + this.token,
          },
        })
          .then((rest) => rest.json())
          .then((result) => {
            // store the posts in the reactive state
            this.fullTileList = result.stones;

            // this.tileList = [...this.fullTileList]
            // console.log(this.tileList, this.fullTileList, "fullTileList")
            this.tileList = [];
            if (!this.fullTileList || this.fullTileList?.length === 0) {
              this.perPageOption = [{ value: 0, text: "0" }];
              this.perPage = 0;
            } else {
              if (this.fullTileList.length > 36) {
                this.perPage = 12;
                this.perPageOption = [
                  { value: 12, text: "12" },
                  { value: 24, text: "24" },
                  { value: 36, text: "36" },
                ];
              } else if (this.fullTileList.length > 24) {
                this.perPageOption = [
                  { value: 12, text: "12" },
                  { value: 24, text: "24" },
                ];
              } else {
                this.perPageOption = [{ value: 12, text: "12" }];
              }

              for (let i = 0; i < this.perPage; i++) {
                console.log(this.fullTileList[i], "srrerer");

                this.tileList.push(this.fullTileList[i]);
              }

              this.pageCount = Math.ceil(
                this.fullTileList?.length / this.perPage
              );
            }
            this.filter = result.category_stats;
          });
      });
  },
  methods: {
    handleFinish(finish) {
      this.tileList = null;
      // store the posts in the reactive state
      fetch(
        apiEndpoint +
          "inventory/stone/v1?category_code=" +
          "Porcelain" +
          "&finish_type=" +
          finish,
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
          this.fullTileList = result.stones;

          // this.tileList = [...this.fullTileList]
          // console.log(this.tileList, this.fullTileList, "fullTileList")
          this.tileList = [];
          if (!this.fullTileList || this.fullTileList?.length === 0) {
            this.perPageOption = [{ value: 0, text: "0" }];
            this.perPage = 0;
          } else {
            if (this.fullTileList.length > 36) {
              this.perPage = 12;
              this.perPageOption = [
                { value: 12, text: "12" },
                { value: 24, text: "24" },
                { value: 36, text: "36" },
              ];
            } else if (this.fullTileList.length > 24) {
              this.perPageOption = [
                { value: 12, text: "12" },
                { value: 24, text: "24" },
              ];
            } else {
              this.perPageOption = [{ value: 12, text: "12" }];
            }

            for (let i = 0; i < this.perPage; i++) {
              this.tileList.push(this.fullTileList[i]);
            }

            this.pageCount = Math.ceil(
              this.fullTileList?.length / this.perPage
            );
          }
          // console.log(tileList, 'tileList')
          this.filter = result.category_stats;
        });
    },
    handleEvent(color) {
      this.tileList = null;
      // store the posts in the reactive state
      fetch(
        apiEndpoint +
          "inventory/stone/v1?category_code=" +
          "Porcelain" +
          "&color_code=" +
          color,
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
          this.fullTileList = result.stones;

          // this.tileList = [...this.fullTileList]
          // console.log(this.tileList, this.fullTileList, "fullTileList")
          this.tileList = [];
          if (!this.fullTileList || this.fullTileList?.length === 0) {
            this.perPageOption = [{ value: 0, text: "0" }];
            this.perPage = 0;
          } else {
            if (this.fullTileList.length > 36) {
              this.perPage = 12;
              this.perPageOption = [
                { value: 12, text: "12" },
                { value: 24, text: "24" },
                { value: 36, text: "36" },
              ];
            } else if (this.fullTileList.length > 24) {
              this.perPageOption = [
                { value: 12, text: "12" },
                { value: 24, text: "24" },
              ];
            } else {
              this.perPageOption = [{ value: 12, text: "12" }];
            }

            for (let i = 0; i < this.perPage; i++) {
              this.tileList.push(this.fullTileList[i]);
            }

            this.pageCount = Math.ceil(
              this.fullTileList?.length / this.perPage
            );
          }
          // console.log(tileList, 'tileList')
          this.filter = result.category_stats;
        });
    },
    perPageChange(value) {
      this.perPage = value;
      this.currentPage = 1;
      this.tileList = [];
      this.pageCount = Math.ceil(this.fullTileList?.length / this.perPage);
      for (let i = 0; i < this.perPage; i++) {
        this.tileList.push(this.fullTileList[i]);
      }
    },
    searchChange(val) {
      this.search = val.target.value;
    },
    submitSearch() {
      if (!this.search || !this.search.trim()) {
        this.tileList = [];
        for (let i = 0; i < this.perPage; i++) {
          console.log(this.fullTileList[i], "srrerer");
          this.tileList.push(this.fullTileList[i]);
        }
        this.pageCount = Math.ceil(this.fullTileList?.length / this.perPage);
      } else {
        this.tileList = [];
        this.currentPage = 1;
        this.perPage = 12;
        for (let i = 0; i < this.fullTileList.length; i++) {
          if (
            this.fullTileList[i].title
              .toLowerCase()
              ?.trim()
              .includes(this.search.toString()?.toLowerCase()?.trim())
          ) {
            this.tileList.push(this.fullTileList[i]);
          }
        }
        this.pageCount = Math.ceil(this.tileList?.length / this.perPage);
      }
    },
    changePage(pageNo) {
      this.currentPage = pageNo;
      this.tileList = [];
      for (
        let i = this.perPage * (this.currentPage - 1);
        i < this.perPage * this.currentPage;
        i++
      ) {
        console.log(i);
        if (this.fullTileList[i]) this.tileList.push(this.fullTileList[i]);
      }
    },
    page(increaseOrDecrease) {
      let pageCheck = this.currentPage + increaseOrDecrease;
      if (pageCheck >= 1 && pageCheck <= this.pageCount) {
        this.currentPage = this.currentPage + increaseOrDecrease;
        this.tileList = [];

        for (
          let i = this.perPage * (this.currentPage - 1);
          i < this.perPage * this.currentPage;
          i++
        ) {
          console.log(i);
          if (this.fullTileList[i]) this.tileList.push(this.fullTileList[i]);
        }
      }
    },
  },
  components: { ImperiaFooterSection },
};
</script>

<style scoped>
.brown-lav {
  width: 99.2%;
  height: 230px;
}

.pagination-wrapper {
  align-items: center;
  display: flex;
  justify-content: space-between;
}

.vertical-line-box {
  transform: rotate(90deg);
  position: absolute;
  bottom: 100px;
  display: flex;
  align-items: center;
  /* top: -10px; */
  left: -80px;
  font-family: NexaLight;
  color: #fff;
  letter-spacing: 8px;
  gap: 10px;
  font-size: 10px;
}

.preloader {
  width: 100%;
  height: 120px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.preloader img {
  width: 100px;
}

.vertical-text {
  transform: rotate(180deg);
  left: 20px;
}

.vertical-line {
  width: 200px;
  height: 2px;
  background-color: #fff;
}

.search-mobile-tab {
  display: none;
  width: 100%;
  padding: 40px;
}

input:focus {
  outline: none;
  box-shadow: none;
}

.view-slab-button-mob {
  font-size: 12px;
  letter-spacing: 5px;
  border: 1px solid rgb(197, 197, 197);
  padding-top: 5px;
  padding-bottom: 5px;
  padding-left: 20px;
  padding-right: 20px;
  background-color: #6c6c6c;
  margin-bottom: 20px;
  color: white;
  font-family: Nexa;
}

.search-icon {
  transform: rotate(90deg);
  color: #7a86a1;
  cursor: pointer;
}

.visualizatin-container {
  margin: auto;
  margin-bottom: 102px;
  width: 100%;
  margin-top: 100px;
}

.intro {
  position: relative;
  min-height: 75vh;
}

.header-logo {
  width: 100%;
  background-image: url("../../static/imperiaa.png");
  background-size: cover;
  background-position: center;
  height: 75vh;
}

.blue-bg {
  position: relative;
  z-index: 1;
  width: 100%;
  height: 280px;
  padding: 10px 40px;
  background-color: #101c32;
}

.blue-bg img {
  height: 100%;
}

.first-line {
  border-left: 2px solid rgb(229, 229, 229);
  margin-top: 365px;
}

.scroll-line {
  height: 17.2em;
  position: absolute;
  margin-left: 40px;
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

.visualizer-image {
  width: 1000px;
  margin-left: 120px;
}

.visualizatin-container {
  margin-top: 100px;
}

.visualize-text {
  font-size: 60px;
  letter-spacing: 30px;
  position: absolute;
}

.form-control-feedback {
  position: absolute;
  text-align: end;
  z-index: 2;
  display: inline-block;
  width: 2.375rem;
  height: 2.375rem;
  line-height: 2.375rem;
  text-align: center;
  pointer-events: none;
  color: #aaa;
}

.view-slab-button {
  font-size: 12px;
  letter-spacing: 5px;
  border: 1px solid rgb(197, 197, 197);
  padding-top: 5px;
  padding-bottom: 5px;
  padding-left: 20px;
  padding-right: 20px;
  background-color: white;
  margin-bottom: 20px;
  color: #707070;
  font-family: Nexa;
}

.search-input {
  width: 100%;
  margin-bottom: 20px;
  border-top: none;
  color: #999999;
  font-size: 10px;
  letter-spacing: 3px;
  padding-left: 0;
}

input {
  padding-left: 0;
  font-family: NexaLight;
  width: 100%;
}

.search-input::placeholder {
  font-size: 10px;
  letter-spacing: 3px;
}

.pagination li {
  display: inline;
  color: #6c58bf;
}

.dropdown-perpage {
  border: none;
  background-color: white;
}

.per-page {
  color: #7a86a1;
  font-size: 18px;
  font-family: Nexa;
}

.page-list {
  margin-left: 10px;
  margin-right: -5px;
}

.know-more {
  height: 30px;
  padding-left: 60px;
  letter-spacing: 6px;
  font-size: 20px;
  background-color: rgb(33, 10, 10);
  width: 180%;
  color: white;
  margin-top: -60px;
  position: relative;
}

.horizontle-line {
  border-bottom: 1px solid rgb(243, 240, 240);
  line-height: 1px;
  margin-left: 400px;
  bottom: 15px;
  position: relative;
}

.dot-one {
  height: 10px;
  width: 10px;
  background-color: rgb(255, 255, 255);
  border-radius: 50%;
  display: inline-block;
  margin-left: 50px;
  margin-bottom: 2px;
}

.slab-section {
  margin-top: 100px;
}

.pagination {
  display: inline-block;
  margin-top: 15px;
}

.pagination span {
  color: black;
  float: left;
  padding: 10px;
  margin-left: 5px;
  text-decoration: none;
}

.pagination span:hover {
  cursor: pointer;
}

.pagination span.active {
  background-color: #4caf50;
  color: white;
}

.button-arrow {
  box-shadow: 2px 5px 8px 3px rgb(235, 234, 234);
  border-radius: 6px;
  padding: 5px;
  font-size: 13px;
}

.page-number {
  display: inline-flex;
  font-size: 15px;
  font-weight: bold;
  position: relative;
  bottom: 4px;
}

.not-active {
  color: rgb(217, 217, 217) !important;
}

.arrow {
  font-size: 13px;
}

.nav-small-text {
  position: absolute;
  margin-top: 320px;
  font-family: Nexa;
  font-size: 45px;
  letter-spacing: 10px;
  color: white;
  font-weight: bold;
}

.nav-experience-text {
  position: absolute;
  margin-top: 420px;
  font-family: NexaBold;
  font-size: 14px;
  color: white;
  letter-spacing: 6px;
}

.line {
  margin-top: -20px;
  border-bottom: 2px solid #e0bb7b;
  position: absolute;
  bottom: 10px;
  z-index: 2;
  height: 4px;
  width: 100%;
  left: 0;
}

.logo {
  /* margin-left: 80px; */
}

.design-button {
  color: #707070;
  position: absolute;
  margin-top: -220px;
  background-color: transparent;
  padding: 6px;
  width: 220px;
  border: 1px solid #707070;
  border-radius: 0px;
  font-size: 12px;
  font-family: Nexa;
  letter-spacing: 3px;
  right: 60px;
  bottom: 40px;
}

.header-shadow {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
}

@media only screen and (max-width: 1399px) and (min-width: 1280px) {
  .nav-small-text {
    margin-top: 280px;
    font-size: 28px;
  }

  .nav-experience-text {
    margin-top: 340px;
    font-size: 9px;
  }

  .first-line {
    border-left: 2px solid rgb(229, 229, 229);
    margin-top: 200px;
  }

  .scroll-line {
    height: 15.2em;
    margin-left: 40px;
  }

  .scroll-text {
    top: 120px;
    left: 49px;
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

  .nav-small-text {
    margin-top: 240px;
    font-size: 28px;
  }

  .nav-experience-text {
    margin-top: 300px;

    font-size: 9px;
  }

  .first-line {
    border-left: 2px solid rgb(229, 229, 229);
    margin-top: 365px;
  }

  .scroll-line {
    height: 17.2em;
    position: absolute;
    margin-left: 40px;
  }

  .first-line {
    border-left: 2px solid rgb(229, 229, 229);
    margin-top: 175px;
  }

  .scroll-line {
    height: 11.2em;
    margin-left: 40px;
  }

  .scroll-text {
    top: 100px;
    left: 49px;
  }
}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .search-mobile-tab {
    display: block;
  }

  .nav-small-text {
    margin-top: 270px;
    font-size: 16px;
  }

  .nav-experience-text {
    margin-top: 310px;

    font-size: 7px;
  }

  .first-line {
    margin-top: 270px;
  }

  .scroll-line {
    height: 8.2em;
    margin-left: 30px;
  }

  .scroll-text {
    top: 200px;
    left: 40px;
    font-size: 8px;
  }

  .logo {
    /* margin-left: 80px; */
  }
}

@media only screen and (max-width: 767px) and (min-width: 360px) {
  .vertical-line-box {
    display: none;
  }

  .search-mobile-tab {
    display: block;
    /* margin-left: 10px; */
  }

  .nav-small-text {
    margin-top: 220px;
    font-size: 14px;
  }

  .nav-experience-text {
    margin-top: 290px;
    font-size: 8px;
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
    /* display: none; */
  }

  .per-page {
    display: flex;
    justify-content: center;
  }

  .brown-lav {
    width: 96.4%;
    height: 280px;
  }

  .blue-bg {
    text-align: center;
  }

  .design-button {
    left: 120px;
  }

  .intro {
    position: relative;
    min-height: 50vh;
  }

  .header-logo {
    width: 100%;
    background-image: url("../../static/imperiaa.png");
    background-size: cover;
    background-position: center;
    height: 50vh;
  }

  .blue-bg {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .blue-bg img {
    max-width: 280px;
    height: auto;
  }

  .visualizatin-container {
    padding: 0 40px;
  }

  .pagination-wrapper {
    flex-direction: column;
  }
}
</style>
