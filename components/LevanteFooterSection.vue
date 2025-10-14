<template>
  <div class="footer-box mt-5">
    <div class="footer-head">
      <img class="logo" src="../static/kiva-white-logo-v2.png" width="120" />

      <img
        class="country-logo"
        src="../static/kiva-white-country-logo-v2.png"
        width="100"
      />
    </div>
    <div class="footer-list mb-5">
      <div v-for="pageName in info">
        <div
          class="mt-5 text-uppercase footer-text footer-text-right"
          @click="pageView(pageName?.toLowerCase())"
        >
          {{ pageName }}
        </div>
      </div>
    </div>

    <div v-for="name in locations" class="mb-4 footer-text mobile-text">
      <div @click="toUrl(name.url)">{{ name.name }}</div>
    </div>
    <div class="text-right footer-bottom mobile-icon">
      <a target="_blank" href="https://www.linkedin.com/company/kiva-stone/">
        <i class="fab fa-linkedin mr-3"></i>
      </a>
      <a target="_blank" href="https://www.facebook.com/kivastonedallas">
        <i class="fab fa-facebook-f mr-3"></i>
      </a>
      <a target="_blank" href="https://www.instagram.com/kivastonedallas/ ">
        <i class="fab fa-instagram"></i>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      locations: [
        {
          name: "Texas",
          url: `
          https://www.google.com/maps/place/Kiva+Stone+Dallas/@32.9114913,-96.9013748,15z/data=!4m2!3m1!1s0x0:0x6fda816a09223a02?sa=X&ved=2ahUKEwiO1tSFypuAAxWDamwGHdDICL4Q_BJ6BAhVEAA&ved=2ahUKEwiO1tSFypuAAxWDamwGHdDICL4Q_BJ6BAhyEAg `,
        },
        {
          name: "Florida",
          url: `
          https://www.google.com/maps/place/Kiva+Stone/@26.3132877,-80.1181213,15z/data=!4m2!3m1!1s0x0:0x17d81509f34c86c8?sa=X&ved=2ahUKEwj-vIeSypuAAxURVWwGHT_bCKQQ_BJ6BAhMEAA&ved=2ahUKEwj-vIeSypuAAxURVWwGHT_bCKQQ_BJ6BAhjEAg `,
        },
        {
          name: "Illinois",
          url: `
          https://www.google.com/maps/place/Kiva+Stone/@41.9741896,-87.9955143,12.15z/data=!4m6!3m5!1s0x880faf7fa5a6a78d:0xfc372452e09bd45d!8m2!3d42.0244654!4d-87.9749245!16s%2Fg%2F11jgw2sn1g?entry=ttu `,
        },
        {
          name: "Ohio",
          url: `
          https://www.google.com/maps/place/Kiva+Stone/@26.3132877,-80.1181213,15z/data=!4m2!3m1!1s0x0:0x17d81509f34c86c8?sa=X&ved=2ahUKEwj-vIeSypuAAxURVWwGHT_bCKQQ_BJ6BAhMEAA&ved=2ahUKEwj-vIeSypuAAxURVWwGHT_bCKQQ_BJ6BAhjEAg `,
        },
      ],
      info: ["About", "Stories", "Blog", "Contact"],
    };
  },
  methods: {
    pageView(page) {
      location.href = `/${
        page === "About" ? "experience" : page.toLowerCase()
      }`;
    },
    toUrl(url) {
      window.open(url, "_blank");
    },
  },
};
</script>

<style scoped>
.footer-head {
  display: flex;
  justify-content: space-between;
}

.logo {
  /* margin-left: -50px; */
}

.footer-box {
  background-color: #27150a;
  padding-top: 60px;
  padding-left: 80px;
  padding-right: 80px;
  position: relative;
  width: 100%;
  color: #e2e2e2;
}

a {
  color: white;
}

.footer-list {
  display: flex;
}

.footer-bottom {
  font-size: 12px;
  padding-bottom: 10px;
}

.country-logo {
  display: block;
  align-self: center;
}

.footer-text {
  font-size: 12px;
  font-family: Nexa;
  color: #e2e2e2;
  letter-spacing: 5px;
  font-weight: lighter;
  cursor: pointer;
  padding-bottom: 10px;
  margin-right: 32px;
}

@media only screen and (max-width: 1279px) and (min-width: 1024px) {
  .footer-box {
  }
}

@media only screen and (max-width: 1023px) and (min-width: 768px) {
  .footer-box {
    padding-top: 60px;
    padding-left: 80px;
    padding-right: 80px;
  }
}

@media only screen and (max-width: 767px) {
  .footer-box {
    text-align: center;
    padding-top: 60px;
    padding-left: 40px;
    padding-right: 40px;
  }

  .country-logo {
    display: none;
  }

  .logo {
    margin-left: 0;
  }

  .footer-text {
    font-size: 8px;
    margin-right: 0;
  }

  .footer-text-right {
    margin-right: 20px;
  }

  .footer-head {
    justify-content: center;
  }

  .footer-list {
    text-align: center;
    justify-content: center;
  }

  .footer-bottom {
    text-align: center;
    justify-content: center;
    display: flex;
    margin: 0 !important;
  }

  .mobile-text {
    text-align: center;
  }

  .mobile-icon {
    margin-left: -80px;
    font-size: 16px;
  }
}
</style>
