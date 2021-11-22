<template>
  <div class="card">
    <div v-if="imgUrl" class="card-img__wrapper">
      <img class="card-img" :src="imgUrl" :alt="title" />
    </div>
    <span class="card-name">{{ name }}</span>
    <span class="card-title">{{ title }}</span>
    <div class="card-body">
      <slot name="body"></slot>
      <router-link
        class="btn btnPrimary"
        style="display: block; margin-top: 16px;"
        v-if="link"
        :to="link"
      >
        See more
      </router-link>
      <slot name="footer">
          <!-- <FooterCard>
          </FooterCard> -->
      </slot>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    imgUrl: {
      type: String,
      required: false
    },
    link: {
      type: String
    }
  }
}
</script>
