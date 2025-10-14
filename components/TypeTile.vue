<template>
  <div class="" @click="pageView(url)">
    <div class="type-tile-box text-center">
      <div class="tile-name text-uppercase"> {{ tileName }}</div>
      <img class="tile-image" :src="imageUrl" />
    </div>

  </div>
</template>
<script>
export default {
  props: ['tileName', 'imageUrl', 'url'],
  methods: {
    pageView(page) {
      location.href = `/${page}`
    }
  }
};
</script>

<style scoped>
.type-tile-box {
  border: 1px;
  background-color: rgb(250, 249, 249);
  /* margin-top: -80px; */
  /* width: 200px; */
  /* height: 240px; */
  max-width: 200px;
  margin: 0 20px;
  cursor: pointer;
  position: relative;
  text-align: center;
}

.tile-name {
  top: 20px;
  font-size: 12px;
  font-family: Nexa;
  letter-spacing: 4px;
  position: absolute;
  text-align: center;
  margin: auto;
  left: 0;
  right: 0;

}

.tile-image {
  /* margin-left: -30px; */
  /* width: 260px; */
  position: relative;
  /* top: -30px; */
  margin-left: -30px;
  width: calc(100% + 30px);
}

/* @media only screen and (max-width: 1629px) and (min-width: 1400px) {
  .type-tile-box {
    border: 1px;
    background-color: rgb(250, 249, 249);
    margin-top: -80px;
    width: 170px;
    margin-left: 106px;
    height: 330px;
    padding: 3px;
    cursor: pointer;
  }

  .tile-image {
    margin-left: -30px;
    width: 195px;
    position: relative;
    top: -30px;
  }

}

@media only screen and (max-width: 1399px) and (min-width: 1280px) {
  .type-tile-box {
    border: 1px;
    background-color: rgb(250, 249, 249);
    margin-top: -80px;
    width: 140px;
    margin-left: 106px;
    height: 190px;
    padding: 3px;
    cursor: pointer;
  }

  .tile-image {
    margin-left: -30px;
    width: 165px;
    position: relative;
    top: -30px;
  }

}

@media only screen and (max-width: 1279px) and (min-width: 1024px) {
  .type-tile-box {
    border: 1px;
    background-color: rgb(250, 249, 249);
    margin-top: -50px;
    width: 95px;
    margin-left: 106px;
    height: 150px;
    padding: 3px;
    cursor: pointer;
  }

  .tile-image {
    margin-left: -30px;
    width: 122px;
    position: relative;
    top: -30px;
  }

  .tile-name {
    position: relative;
    top: 10px;
    font-size: 10px;
    font-family: Poppins;
    letter-spacing: 4px;
  }

}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .type-tile-box {
    border: 1px;
    background-color: rgb(250, 249, 249);
    margin-top: -50px;
    width: 65px;
    margin-left: 92px;
    height: 100px;
    padding: 3px;
    cursor: pointer;
  }

  .tile-image {
    margin-left: -30px;
    width: 92px;
    position: relative;
    top: -30px;
  }

  .tile-name {
    position: relative;
    top: 10px;
    font-size: 7px;
    font-family: Poppins;
    letter-spacing: 4px;
  }

}

@media only screen and (max-width: 767px) and (min-width: 360px) {
  .type-tile-box {
    border: 1px;
    background-color: rgb(250, 249, 249);
    margin-top: -50px;
    width: 45px;
    margin-left: 55px;
    height: 60px;
    padding: 3px;
    cursor: pointer;
  }

  .tile-image {
    margin-left: -30px;
    width: 72px;
    position: relative;
    top: -20px;
  }

  .tile-name {
    position: relative;
    top: 10px;
    font-size: 4px;
    font-family: Poppins;
    letter-spacing: 4px;
  }

} */
</style>