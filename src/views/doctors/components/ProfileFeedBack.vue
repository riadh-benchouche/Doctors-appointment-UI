<template>
  <section>
    <h3 class="mb-2 text-primary">Avis</h3>
    <div
      v-for="(data,index) in twitterFeed"
      :key="data.avatar"
      class="profile-twitter-feed"
      :class="index != 0 ? 'mt-2' : 'mt-1'"
    >
      <div class="d-flex justify-content-start align-items-center mb-1">
        <b-avatar
          size="40"
          :src="data.imgUrl"
          class="mr-1"
        />
        <div class="profile-user-info">
          <h6 class="mb-0">
            {{ data.title }}
          </h6>
            <small class="text-muted">1 month Ago</small>
        </div>
      </div>
      <b-card-text class="mb-25">
        {{ data.desc }}
      </b-card-text>
    </div>
  </section>
    <!-- twitter feed -->
</template>

<script>
import {
  BAvatar, BCardText,
} from 'bootstrap-vue'

export default {
  components: {
    BAvatar, BCardText,
  },
  props: {
    twitterFeed: {
      type: Array,
      default: () => {},
    },
  },
}
</script>
