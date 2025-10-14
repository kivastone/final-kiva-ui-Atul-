<template>
  <div>
    <!-- Google Tag Manager (noscript) -->
    <noscript><iframe src="https://www.googletagmanager.com/ns.html?id=GTM-KSM2RMDD"
    height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
    <!-- End Google Tag Manager (noscript) -->
    <Nuxt />
  </div>
</template>
<script>
  export default {
    data () {
      return {
        gtm: '<iframe src="https://www.googletagmanager.com/ns.html?id=GTM-KSM2RMDD" height="0" width="0" style="display:none;visibility:hidden"></iframe>',
      };
    }
  }
</script>
<style>
body {
  overflow-x: hidden;
  font-family: "Nexa";
}
@media only screen and (max-width: 768px) {
  .aos-animate {
    -o-transition-property: none !important;
    -moz-transition-property: none !important;
    -ms-transition-property: none !important;
    -webkit-transition-property: none !important;
    transition-property: none !important;

    -o-transform: none !important;
    -moz-transform: none !important;
    -ms-transform: none !important;
    -webkit-transform: none !important;
    transform: none !important;

    -webkit-animation: none !important;
    -moz-animation: none !important;
    -o-animation: none !important;
    -ms-animation: none !important;
    animation: none !important;
  }
}
</style>
