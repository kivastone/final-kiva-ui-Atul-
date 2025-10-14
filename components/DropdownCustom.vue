<template>
  <div class="custom-select" :tabindex="tabindex" @blur="open = false">
    <div class="selected" :class="{ open: open }" @click="open = !open">
      {{ selected }}
    </div>
    <div class="items" :class="{ selectHide: !open }">
      <div v-for="(option, i) of options" :key="i" @click="
        selected = option;
      open = false;
      $emit('input', option);
      ">
        {{ option }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    options: {
      type: Array,
      required: true,
    },
    default: {
      type: String,
      required: false,
      default: null,
    },
    tabindex: {
      type: Number,
      required: false,
      default: 0,
    },
  },
  data() {
    return {
      selected: this.default
        ? this.default
        : this.options.length > 0
          ? this.options[0]
          : null,
      open: false,
    };
  },
  mounted() {
    this.$emit("input", this.selected);
  },
};
</script>

<style scoped>
.custom-select {
  position: relative;
  width: 100%;
  text-align: left;
  outline: none;
  height: 38px;
  line-height: 38px;
  position: relative;
  width: 280px;
  border: 0;
  border-radius: 2px;
  text-align: center;
  letter-spacing: 6px;
  font-size: 12px;
}

@media only screen and (max-width: 767px) {
  .custom-select {

  font-size: 10px;
}

}

.custom-select:active,
.custom-select:focus {
  outline: none;
  box-shadow: none;
}

.custom-select .selected {
  background-color: #B5B5B5;
  border-radius: 6px;
  border: 1px solid #B5B5B5;
  color: #fff;
  /* padding-left: 1em; */
  cursor: pointer;
  user-select: none;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  border-radius: 2px;
}

.custom-select .selected.open {
  border: 1px solid #B5B5B5;
  border-radius: 6px 6px 0px 0px;
  outline: none;
}

.custom-select .selected:after {
  position: absolute;
  content: "";
  top: 22px;
  /* right: 1em; */
  width: 0;
  height: 0;
  border: 5px solid transparent;
  border-color: #fff transparent transparent transparent;
  display: none;
}

.custom-select .items {
  color: #fff;
  border-radius: 0px 0px 6px 6px;
  overflow: hidden;
  border-right: 1px solid #B5B5B5;
  border-left: 1px solid #B5B5B5;
  border-bottom: 1px solid #B5B5B5;
  position: absolute;
  background-color: #B5B5B5;
  left: 0;
  right: 0;
  z-index: 1;
}

.custom-select .items div {
  color: #fff;
  /* padding-left: 1em; */
  cursor: pointer;
  user-select: none;
  font-family: NexaBold;
}

.custom-select .items div:hover {
  background-color: #D3D3D3;
  margin: 0 10px;

  color: #000000;
}

.selectHide {
  display: none;
}
</style>