<template>
  <div class="mob-nav">
    <b-button variant="link" :class="visible ? null : 'collapsed'" :aria-expanded="visible ? 'true' : 'false'"
      aria-controls="collapse-4" @click="visible = !visible">
      <i class="fa fa-bars"></i>
    </b-button>
    <b-collapse v-model="visible" id="collapse-3" class="collapse-item">
      <div class="row nav-box">
        <div class="col-12 mb-2 mt-2 text-center border-nav"><b-link href="/home">HOME</b-link></div>
        <div class="col-12 mb-2 mt-2 text-center border-nav">
          <b-dropdown class="nav-link dropdown-toggle nav-link-dropdown" text="LIVE INVENTORY">
            <b-link class="dropdown-item dropdown-nav-item" href="http://kivastonefl.stoneprofitsweb.com">Florida</b-link>
            <b-link class="dropdown-item dropdown-nav-item" href="http://kivastone.stoneprofitsweb.com">Dallas</b-link>
            <b-link class="dropdown-item dropdown-nav-item" href="http://kivastonech.stoneprofitsweb.com">Chicago</b-link>
            <b-link class="dropdown-item dropdown-nav-item" href="https://kivaohio.stoneprofitsweb.com/">Ohio</b-link>
          </b-dropdown>
        </div>
        <div class="col-12 mb-2 mt-2 text-center border-nav"> <b-link href="/inventory">COLLECTION</b-link></div>
        <div class="col-12 mb-2 mt-2 text-center border-nav"><b-link href="/experience">EXPERIENCE</b-link></div>
        <div class="col-12 mb-2 mt-2 text-center border-nav"><b-link href="/sourcing">SOURCING</b-link></div>
        <div class="col-12 mb-2 mt-2 text-center border-nav"><b-link href="/partner-program">PARTNER PROGRAM</b-link>
        </div>
        <div class="col-12 mb-2 mt-2 text-center border-nav"> <b-link href="/contact">CONTACT</b-link></div>
      </div>
    </b-collapse>
  </div>
</template>

<script>
export default {
  data() {
    return {
      visible: false
    }
  }
}
</script>

<style scoped>
.mob-nav {
  display: none;
  position: absolute;
  margin-top: -80px;
  z-index: 4;
  right: 20px;
}

.nav-link-dropdown .dropdown-toggle {
  font-size: 16px;
}

.collapse-item {
  margin-left: 40px;
}

.nav-box {
  background-color: rgb(103, 102, 102);
  border-radius: 8px;
  box-shadow: 2px 2px 2px 2px solid grey;
}

.border-nav a {
  color: white;
}

.btn-link {
  color: black !important;
  font-weight: 600;
}

@media only screen and (max-width: 767px) and (min-width: 240px) {
  .mob-nav {
    display: block;
  }
}
</style>