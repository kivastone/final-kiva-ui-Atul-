<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-12 px-0">
        <NavBar />
        <img class="header-shadow" src="../static/sha.png" />
        <div class="header-logo">
          <div class="coming">COMING SOON</div>
          <div class="coming-btn"  @click="pageView('home')">BACK TO HOME</div>
        </div>
        <FooterSection />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  layout: "default",
  methods: {
    pageView(page) {
      location.href = `/${page}`;
    },
  },
};
</script>

<style scoped>
.header-logo {
  width: 100%;
  background-size: cover;
  background-position: center;
  height: 75vh;
  position: relative;
  text-align: center;
  justify-content: center;
  display: flex;
  align-items: center;
  margin-bottom: -48px;
}
.coming {
  padding: 20px;
  justify-content: center;
  display: flex;
  align-items: center;
  z-index: 100;
  position: absolute;
  margin-top: 60px;
  color: #fff;
  font-size: 35px;
  letter-spacing: 12px;
  font-family: "Nexa";
}
.coming-btn {
  padding: 5px 20px;
  background: #fff;
  color: #000000;
  position: relative;
  z-index: 1;
  display: inline-block;
  margin-top: 240px;
  font-size: 10px;
  cursor: pointer;
  font-family: "Nexa";
}
.header-shadow {
  position: absolute;
  left: 0;
  top: 0;
  z-index: 1;
  width: 100%;
}
.header-logo {
  background-image: url("../static/coming-soon.png");
}

@media only screen and (max-width: 480px) {
  .coming {
    font-size: 20px;
  }
}
</style>
