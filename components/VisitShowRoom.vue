<template>
  <div class="container-fluid visit">
    <div class="row">
      <div class="visit-showroom">
        <div
          class="visit-our"
          data-aos="fade-up"
          data-aos-offset="0"
          data-aos-delay="0"
          data-aos-duration="1000"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        >
          VISIT OUR
        </div>
        <div
          class="showroom text-center"
          data-aos="fade-up"
          data-aos-offset="0"
          data-aos-delay="0"
          data-aos-duration="1000"
          data-aos-easing="ease-in-out"
          data-aos-once="true"
        >
          SHOWROOM
        </div>
      </div>
      <img class="image-showroom" src="../static/showroom.png" />
    </div>
  </div>
</template>

<style scoped>
.visit {
  position: relative;
  z-index: 1;
}
.visit-showroom {
  width: 100%;
  height: 500px;
  background-color: rgb(47, 47, 47);
  color: white;
  margin-top: 150px;
  /* z-index: 1; */
  text-align: center;
}

.image-showroom {
  margin-top: -340px;
  width: 1100px;
  margin-left: auto;
  margin-right: auto;
  left: 0;
  right: 0;
}

.showroom {
  font-size: 220px;
  position: relative;
  margin-top: -80px;
  font-family: Madesaonara;
}

.visit-our {
  margin-top: 60px;
  text-align: center;
  margin-right: 63%;
  font-size: 22px;
  /* margin-left: 90px; */
  font-family: NexaLight;
  letter-spacing: 10px;
  width: 100%;
  /* text-align: left; */
}

@media only screen and (max-width: 1399px) and (min-width: 1280px) {
  .image-showroom {
    width: 900px;
  }

  .showroom {
    font-size: 190px;
    margin-top: -64px;
  }

  .visit-our {
    margin-top: 60px;
    /* margin-right: 63%; */
    font-size: 22px;
    /* margin-left: 90px; */
  }
}

@media only screen and (max-width: 1279px) and (min-width: 1024px) {
  .image-showroom {
    width: 700px;
  }

  .showroom {
    font-size: 140px;
    margin-top: -40px;
  }

  .visit-our {
    margin-top: 70px;
    /* margin-right: 63%; */
    font-size: 24px;
    /* margin-left: 90px; */
  }
}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .image-showroom {
    margin-top: -180px;
    width: 500px;
  }

  .showroom {
    font-size: 90px;
    margin-top: -30px;
  }

  .visit-our {
    margin-top: 60px;
    /* margin-right: 63%; */
    font-size: 10px;
    /* margin-left: 120px; */
  }

  .visit-showroom {
    height: 300px;
  }
}

@media only screen and (max-width: 767px) {
  .image-showroom {
    margin-top: -180px;
    width: 93.6%;
    height: 300px;
    margin-bottom: -50px;
  }

  .showroom {
    font-size: 55px;
    margin-top: -10px;
  }

  .visit-our {
    margin-top: 70px;
    font-size: 8px;
    /* margin-left: 70px; */
  }

  .visit-showroom {
    height: 300px;
  }
}

@media only screen and (max-width: 359px) {
 
  .showroom {
    font-size: 46px;
    margin-top: -10px;
  }
}
</style>
