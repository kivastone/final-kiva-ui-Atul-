<template>
  <div
    data-aos="zoom-in"
    data-aos-offset="200"
    data-aos-delay="0"
    data-aos-duration="600"
    data-aos-easing="ease-in-out"
    data-aos-once="true"
    class="tile-box text-center"
    @click="goToInventoryDetail(tileName + '/' + category_code)"
  >
    <div class="tile-name text-uppercase text-center">{{ tileName }}</div>
    <div class="tile-code text-uppercase text-center">{{ tileCode }}</div>
    <span class="image-top"><img class="tile-image" :src="imageUrl" /></span>
    <!-- <span class="circle">
      <i class="fa fa-expand see-image">
        <i class="fa fa-eye eye"></i>
      </i>
    </span> -->
  </div>
</template>
<script>
export default {
  props: ["id", "tileName", "tileCode", "imageUrl", "category_code"],
  methods: {
    goToInventoryDetail(id) {
      this.$router.push(`/inventory/${id}`);
    },
  },
};
</script>

<style scoped>
.tile-box {
  width: 231px;
  /* height: 300px; */
  background-color: #f6f6f6;
  padding-top: 25px;
  margin: auto;
  cursor: pointer;
  position: relative;
  margin-bottom: 20px;
  word-wrap: break-word;
}

.tile-box:hover {
  transform: scale(1.1);
  -webkit-transition: transform 0.4s ease-in-out;
}

.tile-image {
  width: 128%;
  margin: auto;
  margin-left: -13%;
}

.image-top:hover {
  transform: scale(1.1);
  -webkit-transition: transform 0.2s ease-in-out;
}

.tile-name {
  font-size: 13px;
  letter-spacing: 6px;
  font-weight: bold;
  font-family: Poppins;
}

.tile-code {
  font-size: 8px;
  font-weight: bold;
  color: #acacac;
}

.see-image {
  display: inline-block;
  position: absolute;
  font-size: 20px;
  top: 5px;
  right: -2px;
  color: rgb(221, 218, 218);
}

.see-image:hover {
  right: 100px !important;
}

.eye {
  position: relative;
  font-size: 13px;
  bottom: 23px;
}

.circle {
  width: 28px;
  height: 28px;
  border-radius: 50%;
  background-color: rgb(27, 25, 25);
  opacity: 0.6;
  position: relative;
  display: inline-block;
  bottom: 260px;
  left: 128px;
}

.image-top {
  width: calc(100% + 120px);
  margin-left: -60px;
  /* margin: auto; */
  /* left: 0; */
  /* right: 0; */
  overflow: hidden;
  display: inline-block;
}
</style>
