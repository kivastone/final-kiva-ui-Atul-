<template>
  <div>
    <div class="navigation navigation-dark container-fluid">
      <div class="row text-center">
        <div class="col-12 mb-4">
          <b-link href="/home">
            <img
              src="../static/kiva-black.png"
              class="margin-logo"
              data-aos="fade-in"
              data-aos-offset="200"
              data-aos-delay="0"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true"
            />
          </b-link>
        </div>
        <!-- <div class="col-lg-1 hide-class"></div> -->
        <div class="col-12">
          <div class="nav-links" data-aos="fade-in"
          data-aos-offset="200"
          data-aos-delay="0"
          data-aos-duration="800"
          data-aos-easing="ease-in-out"
          data-aos-once="true">
            <div class="ml-3 mr-3 hide-class">
              <b-link href="/home">HOME</b-link>
            </div>
            <div class="ml-3 mr-3 hide-class">
              <b-dropdown
                class="nav-link dropdown-toggle nav-link-dropdown"
                text="LIVE INVENTORY"
              >
                <b-link
                  class="dropdown-item dropdown-nav-item"
                  href="http://kivastonefl.stoneprofitsweb.com"
                  >Florida</b-link
                >
                <b-link
                  class="dropdown-item dropdown-nav-item"
                  href="http://kivastone.stoneprofitsweb.com"
                  >Dallas</b-link
                >
                <b-link
                  class="dropdown-item dropdown-nav-item"
                  href="http://kivastonech.stoneprofitsweb.com"
                  >Chicago</b-link
                >
            <b-link class="dropdown-item dropdown-nav-item" href="https://kivaohio.stoneprofitsweb.com/">Ohio</b-link>

              </b-dropdown>
            </div>
            <div class="ml-3 mr-3 hide-class">
              <b-link href="/inventory">COLLECTION</b-link>
            </div>
            <div class="ml-3 mr-3 hide-class">
              <b-link href="/experience">EXPERIENCE</b-link>
            </div>
            <div class="ml-3 mr-3 hide-class">
              <b-link href="/sourcing">SOURCING</b-link>
            </div>
            <div class="ml-3 mr-3 hide-class">
              <b-link href="/partner-program">PARTNER PROGRAM</b-link>
            </div>
            <div class="ml-3 mr-3 hide-class">
              <b-link href="/contact">CONTACT</b-link>
            </div>
          </div>
        </div>
      </div>
    </div>
    <detailMobileNavBar class="col-12 text-right" />
  </div>
</template>

<script>
export default {
  name: "Navbar",
};
</script>

<style scoped>
.navigation {
  margin-top: 60px;
  font-size: 11px;
  font-family: Poppins;
  display: flex;
  letter-spacing: 3px;
  justify-content: center;
  /* margin-left: 110px; */
  z-index: 1;
  position: relative;
}

.nav-links {
  display: flex;
  width: 100%;
  margin: auto;
  position: relative;
  justify-content: center;
  align-items: center;
}

a {
  color: black;
  font-weight: bolder;
  font-size: 12px;
}

.nav-link-dropdown {
  color: black !important;
  /* margin-top: -2px; */
}
.margin-logo {
  margin-top: -20px;
  margin-bottom: 20px;
  width: 160px;
}

@media only screen and (max-width: 1399px) and (min-width: 1280px) {
  .navigation {
  }
}

@media only screen and (max-width: 1279px) and (min-width: 1024px) {
  .navigation {
    /* left: 1%; */
  }
}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .navigation {
    /* left: -12%; */
    width: 100%;
  }

  a {
    font-size: 10px;
  }
}

@media only screen and (max-width: 767px) and (min-width: 240px) {
  .hide-class {
    display: none;
  }

  .margin-logo {
    width: 100%;
    max-width: 120px;
  }
}
</style>
