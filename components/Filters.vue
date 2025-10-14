<template>
  <div>
    <div class="type-name mb-2">{{ type }}</div>
    <div v-for="tile in filter">
      <a v-if='cateMap[tile.category_code]?.url' :href='`${cateMap[tile.category_code]?.url}`'>
        <span class="tile">{{ tile.category_code }} ({{ tile.stone_count }})</span>
      </a>
      <span v-else class="tile">{{ tile.category_code }} ({{ tile.stone_count }})</span>
    </div>
    <div class="type-name color-name mb-2">SLAB FINISH</div>
    <div v-for="slab in slabs">
      <span class="tile" @click="() => sendFinish(slab.finish_name)">{{ slab.finish_name }} ({{ slab.stone_count
      }})</span>
    </div>
    <div class="type-name color-name mb-2">COLOR</div>
    <div v-for="color in colors">
      <span class="tile" @click="() => sendColor(color.color_code)">{{ color.color_code }} ({{ color.stone_count
      }})</span>
    </div>
  </div>
</template>

<script>
import {apiEndpoint} from '../assets/utils';

export default {
  props: ['categoryCode'],
  methods: {
    sendColor(color) {
      console.log('here')
      this.$emit('callback-triggered', color)
    },
    sendFinish(finish) {
      console.log('here')
      this.$emit('callback-finish', finish)
    },
  },
  data() {
    return {
      type: 'STONE TYPE',
      filter: [],
      colors: [],
      slabs: [],
      cateMap: {
        'PORCELAIN': {
          url: 'imperia',
          bannerImage: 'granite.png',
          smallIntroText: 'OUR FINEST',
          largeIntroText: 'GRANITES'
        },
        'QUARTZ': {
          url: 'levante',
          bannerImage: 'quarzite.png',
          smallIntroText: 'OUR FINEST',
          largeIntroText: 'QUARZITES'
        },
        'GRANITES & DOLOMITES': {
          url: 'inventory/granite-dolomites',
          bannerImage: 'marble.png',
          smallIntroText: 'OUR FINEST',
          largeIntroText: 'MARBLES'
        },
        'MARBLE': {
          url: 'inventory/marble',
          bannerImage: 'precious.png',
          smallIntroText: 'OUR EXQUISITE',
          largeIntroText: 'SELECTION'
        },
        'QUARTZITE': {
          url: 'inventory/quartzite',
          bannerImage: 'precious.png',
          smallIntroText: 'OUR EXQUISITE',
          largeIntroText: 'SELECTION'
        },
        'Semi Precious': {
          url: 'inventory/semi-precious',
          bannerImage: 'precious.png',
          smallIntroText: 'OUR EXQUISITE',
          largeIntroText: 'SELECTION'
        },
      }
    }
  },
  created() {
    
    fetch(apiEndpoint + 'auth/login/token/', {
      method: "POST",
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({"username": process.env.account, "password": process.env.password})
    })
      .then((res) => res.json())
      .then((data) => {
        // store the posts in the reactive state
        this.token = data.records.token;
        const url = this.categoryCode ? apiEndpoint + 'inventory/stone/v1?category_code=' + this.categoryCode : apiEndpoint + 'inventory/stone/v1'
        fetch(url, {
          method: "GET",
          headers: {
            'Content-Type': 'application/json',
            'Authorization': 'Token ' + this.token
          },
        })
          .then((rest) => rest.json())
          .then((result) => {
            console.log('here4')
            console.log(result, 'result');
            // store the posts in the reactive state
            this.filter = [...result.category_stats];
            this.colors = [...result.color_stats]
            this.slabs = [...result.stone_finish_stats]
          })
      })
  }
}
</script>

<style scoped>
.type-name {
  font-size: 15px;
  letter-spacing: 6px;
  font-family: NexaLight;
  color: #000000;
}

.color-name {
  margin-top: 40px;
}

.tile {
  font-size: 14px;
  font-family: NexaLight;
  color: #434343;
  cursor: pointer;
}
</style>
