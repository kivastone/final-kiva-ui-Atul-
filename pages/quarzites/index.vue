
<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <NavBar />
        <div class="nav-small-text">OUR FINEST</div>
        <div class="nav-experience-text">QUARZITES</div>

        <img class="header-shadow" src="../../static/sha.png" />
        <div class="header-logo">
          <div class="scroll-text">SCROLL</div>
          <div class="first-line scroll-line"></div>
        </div>
        <div class="carousel">
          <VueSlickCarousel v-bind="settings">
            <TypeTile tileName="Quartz" imageUrl="https://i.ibb.co/4K4jf1W/f.png" url="levante" />
            <TypeTile tileName="Porcelain" imageUrl="https://i.ibb.co/TMQYXRD/b.png" url="imperia" />
            <TypeTile tileName="Semi Precious" imageUrl="https://i.ibb.co/DtWN22R/a.png" url="semi-precious" />
            <TypeTile tileName="Granites & Dolomites" imageUrl="https://i.ibb.co/pQvWM5Y/c.png" url="granite" />
            <TypeTile tileName="Quartzite" imageUrl="quartzite.png" url="quartzite" />
            <TypeTile tileName="Marble" imageUrl="https://i.ibb.co/dsvh9jn/e.png" url="marbles" />
          </VueSlickCarousel>
        </div>
      </div>
      <div class="inventory-list container-fluid">
        <div class="row mb-5 slab-section">
          <div class="col-lg-3 	d-none d-lg-block">
            <div class="ml-5">
              <!-- <button class="view-slab-button">VIEW ALL SLABS</button> -->
              <div class="search-input">
                <div class="input-group">
                  <b-input class="form-control py-2 border-right-0 border-top-0 border-left-0 border" v-model="search"
                    placeholder="SEARCH" />
                  <span class="input-group-append">
                    <div class="input-group-text bg-transparent border-right-0 border-top-0 border-left-0">
                      <i class="fa fa-search search-icon"></i>
                    </div>
                  </span>
                </div>
              </div>
              <Filters @callback-triggered="handleEvent" @callback-finish="handleFinish" />

            </div>
          </div>
          <div class="col-lg-9 col-md-12">
            <div class="row">
              <div v-if="tileList == null">Loading</div>
              <div v-else-if="!tileList.length">No Results</div>
              <div v-else v-for="tile in tileList" class="col-xl-4 col-lg-6 col-md-6 col-sm-12">
                <InventoryTile :id="tile.item_code" :category_code="tile.category_code"
                    :tileCode="tile.item_code" :tileName="tile.title" :imageUrl="tile.slab_images" />
              </div>
            </div>
            <div class="row mt-5">
              <div class="col-lg-3 col-md-4">
                <div class="form-group form-inline per-page">
                  <span>SHOWING:</span>
                  <span class="page-list">{{ perPage }}</span>
                  <b-dropdown toggle-class="dropdown-perpage" variant="none" id="dropdown" class="m-md-2">
                    <b-dropdown-item v-for="option in perPageOption" :selected="perPage" :value="option.value"
                      @click="perPageChange(option.text)">{{ option.text }}
                    </b-dropdown-item>
                  </b-dropdown>
                </div>
              </div>
              <div class="col-lg-8 col-md-7 pr-0 text-right">
                <div class="pagination">
                  <span class='fas fa-arrow-left arrow' :class="parseInt(currentPage) === 1 ? 'not-active' : ''"
                    @click="page(-1)">
                  </span>
                  <span class="page-number" v-for="(item, i) in filter">
                    <p :class="i + 1 !== parseInt(currentPage) ? 'not-active' : ''" @click="changePage(i)">
                      {{ i + 1 }}
                    </p>
                  </span>
                  <span class='fas fa-arrow-right button-arrow'
                    :class="parseInt(currentPage) === filter.length ? 'not-active' : ''" @click="page(+1)">
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
              <b-input class="form-control py-2 border-right-0 border-top-0 border-left-0 border" v-model="search"
                placeholder="S E A R C H" />
              <span class="input-group-append">
                <div class="input-group-text bg-transparent border-right-0 border-top-0 border-left-0">
                  <i class="fa fa-search search-icon"></i>
                </div>
              </span>
            </div>
          </div>
          <Filters @callback-triggered="handleEvent" @callback-finish="handleFinish" />

        </div>
      </div>

      <div class="visualizatin-container">
        <VisualizeStone />
      </div>
      <FooterSection />
    </div>
  </div>
</template>

<script>
import internal from 'stream';
import VueSlickCarousel from 'vue-slick-carousel'
import {apiEndpoint} from '../../assets/utils';

export default {
  layout: "default",
  components: {VueSlickCarousel},
  data() {
    return {
      tileList: null,
      settings: {
        "dots": true,
        "arrows": false,
        "focusOnSelect": true,
        "infinite": false,
        "speed": 500,

        "slidesToScroll": 2,
        "slidesToShow": 6,
        "adaptiveHeight": true,
        // "adaptiveHeight": true,
        responsive: [
          {
            "breakpoint": 1400,
            "settings": {
              "slidesToShow": 5,
              "dots": true
            }
          },
          {
            "breakpoint": 1160,
            "settings": {
              "slidesToShow": 4,
              "dots": true
            }
          },
          {
            "breakpoint": 930,
            "settings": {
              "slidesToShow": 3,
              "dots": true
            }
          },
          {
            "breakpoint": 680,
            "settings": {
              "slidesToShow": 2,
              "dots": true
            }
          },
        ]
      },

      search: "",
      currentPage: "1",
      perPage: "2",
      pageList: [],
      perPageOption: [
        {value: 2, text: "2"},
        {value: 50, text: "50"},
        {value: 100, text: "100"},
      ],
      filter: [
        {name: "Quartz", quantity: 40},
        {name: "Granite", quantity: 60},
        {name: "Quartz", quantity: 80},
        {name: "Marble", quantity: 70},
        {name: "Quartz", quantity: 76},
        {name: "Dolomite", quantity: 90},
      ],
    };
  },
  created() {
    fetch(apiEndpoint+'auth/login/token/', {
      method: "POST",
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({"username": process.env.account, "password": process.env.password})
    })
      .then((res) => res.json())
      .then((data) => {
        // store the posts in the reactive state
        this.token = data.records.token;
        fetch(apiEndpoint+'inventory/stone/v1?category_code=Quartzites', {
          method: "GET",
          headers: {
            'Content-Type': 'application/json',
            'Authorization': 'Token ' + this.token
          },
        })
          .then((rest) => rest.json())
          .then((result) => {
            // store the posts in the reactive state
            this.tileList = result.stones
            this.filter = result.category_stats;
          })
      })

  },
  methods: {
    handleFinish(finish) {
      this.tileList = [];
      // store the posts in the reactive state
      fetch(apiEndpoint + 'inventory/stone/v1?finish_type=' + finish, {
        method: "GET",
        headers: {
          'Content-Type': 'application/json',
          'Authorization': 'Token ' + this.token
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
            this.perPageOption = [
              {value: 0, text: "0"}

            ]
            this.perPage = 0
          } else {
            if (this.fullTileList.length > 36) {
              this.perPageOption = [
                {value: 12, text: "12"},
                {value: 24, text: "24"},
                {value: 36, text: "36"}
              ]
            } else if (this.fullTileList.length > 24) {
              this.perPageOption = [
                {value: 12, text: "12"},
                {value: 24, text: "24"}
              ]
            } else {
              this.perPageOption = [
                {value: 12, text: "12"},

              ]
            }

            for (let i = 0; i < this.perPage; i++) {

              this.tileList.push(this.fullTileList[i])
            }


            this.pageCount = Math.ceil(this.fullTileList?.length / this.perPage)
          }
          // console.log(tileList, 'tileList')
          this.filter = result.category_stats;
        })
    },
    handleEvent(color) {
      this.tileList = [];
      // store the posts in the reactive state
      fetch(apiEndpoint + 'inventory/stone/v1?color_code=' + color, {
        method: "GET",
        headers: {
          'Content-Type': 'application/json',
          'Authorization': 'Token ' + this.token
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
            this.perPageOption = [
              {value: 0, text: "0"}

            ]
            this.perPage = 0
          } else {
            if (this.fullTileList.length > 36) {
              this.perPageOption = [
                {value: 12, text: "12"},
                {value: 24, text: "24"},
                {value: 36, text: "36"}
              ]
            } else if (this.fullTileList.length > 24) {
              this.perPageOption = [
                {value: 12, text: "12"},
                {value: 24, text: "24"}
              ]
            } else {
              this.perPageOption = [
                {value: 12, text: "12"},

              ]
            }

            for (let i = 0; i < this.perPage; i++) {

              this.tileList.push(this.fullTileList[i])
            }


            this.pageCount = Math.ceil(this.fullTileList?.length / this.perPage)
          }
          // console.log(tileList, 'tileList')
          this.filter = result.category_stats;
        })
    },
    perPageChange(value) {
      this.perPage = value;
    },
    changePage(pageNo) {
      this.currentPage = pageNo + 1
    },
    page(increaseOrDecrease) {
      let page = parseInt(this.currentPage) + increaseOrDecrease
      if (page <= 1) {
        this.currentPage = 1
      } else if (page >= this.filter.length) {
        this.currentPage = this.filter.length
      } else {
        this.currentPage = page
      }
    }
  },
};
</script>

<style scoped>
.header-logo {
  width: 100%;
  background-image: url("../../static/quarzite.png");
  background-size: cover;
  background-position: center;
  height: 75vh;
  position: relative;
}



.carousel {
  margin-top: -40px;
  width: 100%;
  padding-left: 50px;
}

.search-icon {
  transform: rotate(90deg);
  color: #707070;
  cursor: pointer;
}

.search-mobile-tab {
  display: none;
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

.slick-prev,
.slick-next {
  display: none;
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

.visualizatin-container {
  margin: auto;
  margin-bottom: 102px;
  width: 100%;
  margin-top: 100px;
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
  color: #707070;
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

.view-slab-button-mob {
  font-size: 12px;
  letter-spacing: 5px;
  border: 1px solid rgb(197, 197, 197);
  padding-top: 8px;
  padding-bottom: 5px;
  padding-left: 20px;
  padding-right: 20px;
  background-color: #6c6c6c;
  margin-bottom: 20px;
  color: white;
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
}

.search-input input::placeholder {
  font-size: 12px;
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
  background-color: #4CAF50;
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

.header-shadow {
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
}

@media only screen and (max-width: 1399px) and (min-width: 1280px) {
  .header-shadow {
    width: 100%
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
    width: 100%
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
    width: 100%
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


}

@media only screen and (max-width: 767px) and (min-width: 360px) {
  .header-shadow {
    width: 100%;
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
}
</style>
