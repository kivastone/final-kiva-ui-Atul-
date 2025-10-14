<template>
  <div class="intro" :style="{ backgroundImage: `url(${require(`@/static/${banner}`)})` }">
    <NavBar />
    <div class="intro-text" data-aos="fade-up"
              data-aos-offset="0"
              data-aos-delay="0"
              data-aos-duration="800"
              data-aos-easing="ease-in-out"
              data-aos-once="true">
      <div class="nav-small-text">{{ title }}</div>
      <div class="nav-experience-text">{{ description }}</div>
    </div>
    <img class="header-shadow" src="../static/sha.png" />
    <div class="header-logo">
      <div class="scroll-text">SCROLL</div>
      <div class="first-line scroll-line"></div>
    </div>
  </div>
</template>

<script>


export default {
  props: ['title', 'description', 'banner'],

};
</script>

<style scoped>
.intro {
  min-height: 80vh;
  background-size: cover;
  background-position: center;
  width: 100%;
  background-repeat: no-repeat;
  display: flex;
  align-items: flex-end;
  padding-top: 180px;
  padding-bottom: 120px;
  position: relative;
}

.intro-text {
  padding: 10px 40px 10px 120px;
  color: #fff;
  font-family: Madesaonara;
  z-index: 1;
}

.header-shadow {
  position: absolute;
  width: 100%;
  top: 0;
  left: 0;
  height: 50%;
}

.nav-experience-text {
  font-size: 10.5vw;
  line-height: 9vw;
}

.nav-small-text {
  font-size: 1.2vw;
  letter-spacing: 12px;
  font-family: Nexa;
}

.header-logo {
  position: absolute;
  bottom: 0;
  display: flex;
  align-items: center;
  justify-content: center;
}

.intro-text {
  position: relative;
}

.scroll-text {
  writing-mode: vertical-lr;
  letter-spacing: 5px;
  font-size: 10px;
  color: white;
  bottom: 190px;
  /* left: 35px; */
  position: absolute;
  transform: rotate(180deg);
  /* bottom: 0; */
}


.scroll-line {
  border-left: 2px solid rgb(229, 229, 229);
  height: 11.2em;
  position: absolute;
  /* margin-left: 40px; */
  bottom: 0;
}

.header-logo {
  padding-left: 40px;
}

@media only screen and (max-width: 1020px) {


  .header-logo {
    padding-left: 30px;
  }
}

@media only screen and (max-width: 767px) {
  .intro-text {
    padding: 0 40px;
    color: #fff;
    font-family: Madesaonara;
  }

  .nav-small-text {
    letter-spacing: 7px;
    font-size: 9px;
  }

  .intro {
    min-height: 60vh;
    padding-bottom: 72px;

  }

  .header-logo {
    display: none;
  }

}
</style>