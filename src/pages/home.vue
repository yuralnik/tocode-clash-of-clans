<template>
  <carousel :settings="settings" :breakpoints="breakpoints">
    <slide class="card__wrapper" v-for="item in items" :key="item.id">
      <Card
        :name="`${item.lvl} lvl`"
        :title="item.title"
        :imgUrl="item.img"
        :link="`/${item.alias}`"
      >
        <template v-slot:body>
          {{ item.descr }}
        </template>
        <template v-slot:footer class="stats-wrapper">
          <Stats v-for="(stat, index) in item.info" :key="index">
        <template v-slot:statBody>
          {{ stat.value }}
        </template>
        <template v-slot:statFooter>
          {{ stat.title }}
        </template>
      </Stats>
        </template>
      </Card>
      
    </slide>
    <template #addons>
      <navigation />
    </template>
  </carousel>
</template>

<script>
import items from '@/seeders/items.js'

import Card from '@/components/UI/Card'

import Stats from '@/components/UI/Stats'

import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Pagination, Navigation } from 'vue3-carousel'

export default {
  components: {
    Card,
    Stats,
    Carousel,
    Slide,
    Pagination,
    Navigation
  },
  data() {
    return {
      items: items,
      settings: {
        itemsToShow: 2,
        wrapArround: true,
        snapAlign: 'center'
      },
      breakpoints: {
        300: {
          itemsToShow: 1
        },
        700: {
          itemsToShow: 1
        }
      }
    }
  }
}
</script>
