<template>
  <div class="wrapper-person view-sm">
    <div v-if="item" class="card_wrapper">
      <img :src="item.img" :alt="item.descr" />
      <h1 style="color: #ffffff;" class="title">{{ item.title }}</h1>
      <p>{{ item.descr }}</p>
      <div class="card-stats">
        <div v-for="(stat, index) in item.info" :key="index" class="one-third">
          <div class="stat-value">
            {{ stat.value }}
          </div>
          <div class="stat">
            {{ stat.title }}
          </div>
        </div>
      </div>
      <br />
      <div>
        <router-link to="/" class="btn btnPrimary">back to Home</router-link>
      </div>
    </div>
  </div>
</template>

<script>
import items from '@/seeders/items.js'

export default {
  data() {
    return {
      item: null
    }
  },
  created() {
    const alias = this.$route.params.itemAlias
    const item = items.find(el => el.alias === alias)
    this.item = item
  }
}
</script>

<style lang="scss">
.wrapper-person {
    text-align: center;
  .card-stats {
    border-radius: 14px;
    margin: 30px 0;
    text-align: center;
  }
}
</style>
