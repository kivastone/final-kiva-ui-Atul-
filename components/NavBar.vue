<template>
  <div class="relative">

    <div class="navigation" data-aos="fade-in"
              data-aos-offset="0"
              data-aos-delay="0"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true">

      <b-link href="/home">
        <img src="../static/kiva-white-logo-v2.png" class="margin-logo" />
      </b-link>
      <div class="links">
        <div class="ml-3 mr-3 hide-class">
          <b-link href="/home">HOME</b-link>
        </div>
        <div class="ml-3 mr-3 hide-class">
          <!-- <ul class="nav">
            <li class="nav-item b-nav-dropdown dropdown show" id="__BVID__12">
              <a role="button" class="nav-link dropdown-toggle nav-link-dropdown"><span>LIVE INVENTORY</span>
              </a>
              <ul v-if="show" tabindex="-1" class="dropdown-menu dropdown-menu-right show"
                aria-labelledby="__BVID__12__BV_toggle_" id="__BVID__12__BV_toggle_menu_"
                style="position: absolute; will-change: transform; top: 0px; left: 0px; transform: translate3d(15px, 14px, 0px);"
                x-placement="bottom-end">
                <li role="presentation" class="dropdown-nav-item"><a role="menuitem"
                    href="http://kivastonefl.stoneprofitsweb.com/" target="_self" class="dropdown-item">Florida</a></li>
                <li role="presentation" class="dropdown-nav-item"><a role="menuitem"
                    href="http://kivastone.stoneprofitsweb.com/" target="_self" class="dropdown-item">Dallas</a></li>
                <li role="presentation" class="dropdown-nav-item"><a role="menuitem"
                    href="http://kivastonech.stoneprofitsweb.com/" target="_self" class="dropdown-item">Chicago</a></li>
              </ul>
            </li>
          </ul> -->

          <b-dropdown class="nav-link dropdown-toggle nav-link-dropdown" text="LIVE INVENTORY">
            <b-link class="dropdown-item dropdown-nav-item" href="http://kivastonefl.stoneprofitsweb.com">Florida</b-link>
            <b-link class="dropdown-item dropdown-nav-item" href="http://kivastone.stoneprofitsweb.com">Dallas</b-link>
            <b-link class="dropdown-item dropdown-nav-item" href="http://kivastonech.stoneprofitsweb.com">Chicago</b-link>
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
    <MobileNavBar class="text-right" />
    </div>
</template>

<script>
export default {
  name: "Navbar"
};
</script>

<style scoped>
.shadow-div {
  display: block;
  position: absolute;
  left: 0;
  top: 0;
  background: linear-gradient(to top, rgba(255, 0, 0, 0) 20%, rgba(0, 0, 0, 0.5) 100%);
  height: 100px;
  width: 100%;
  z-index: -1;

}

.navigation {
  position: relative;
  align-items: center;
  display: flex;
  flex-direction: column;
  font-family: "Nexa";
  font-size: 11px;
  justify-content: center;
  left: 0;
  letter-spacing: 3px;
  margin-left: auto;
  margin-right: auto;
  position: absolute;
  right: 0;
  text-align: center;
  top: 60px;
  width: 100%;
  z-index: 2;

}

.relative {
  /* position: relative; */

  
}

.b-nav-dropdown {
  line-height: 0;
  padding: 0;
}

.links {
  align-items: center;
  display: flex;
}

.test a span,
a {
  color: #fff;
}

.nav-link-dropdown {
  color: #fff !important;
  margin-top: -2px;
}

.margin-logo {
  margin-bottom: 20px;
  margin-top: -20px;
  max-width: 160px;
}

.dropdown-toggle::after {
  display: none;
}

@media only screen and (max-width: 767px) and (min-width: 240px) {
  .hide-class {
    display: none;
  }

  .margin-logo {
    max-width: 120px;
    width: 100%;
  }
}
</style>
