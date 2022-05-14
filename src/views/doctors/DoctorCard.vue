<template>
  <swiper
      class="swiper-responsive-breakpoints"
      :options="swiperOptions"
      :dir="$store.state.appConfig.isRTL ? 'rtl' : 'ltr'"
  >
    <swiper-slide
        v-for="(doctor) in doctorsData"
        :key="doctor.id"
    >
      <b-card
          :img-src="require('@/assets/images/profile/user-uploads/timeline.jpg')"
          img-alt="Profile Cover Photo"
          img-top
          class="card-profile"
      >
        <div class="profile-image-wrapper">
          <div class="profile-image p-0">
            <b-avatar
                size="114"
                variant="primary"
                :src="require('@/assets/images/profile/user-uploads/user-01.jpg')"
                :to="{name:'doctor-detail', params :{id:doctor.id}}"
            />
          </div>
        </div>
        <h3 role="button" @click="$router.push({name:'doctor-detail', params :{id:doctor.id}})">{{doctor.fullName}}</h3>
        <h6 class="text-muted">
          Spécialité: {{doctor.specialite}}
        </h6>
        <b-badge
            class="profile-badge"
            variant="light-primary"
        >
          {{doctor.company}}
        </b-badge>
        <p>
          <feather-icon
              icon="MapPinIcon"
              class="mr-25"
          />
          {{doctor.country}}
        </p>
        <hr class="mb-2">

        <!-- follower projects rank -->
        <div class="d-flex justify-content-between align-items-center">
          <div>
            <h4 class="text-muted font-weight-bolder">
              Rating
            </h4>
            <h1 class="mb-0">
              4.3
            </h1>
            <b-form-rating
                readonly
                :value="doctor.rating"
                variant="warning"
                inline
                no-border
                class="mt-0"
            />
          </div>
          <div class="progress-wrapper w-50">
            <b-row
                v-for="bar in bars"
                :key="bar.variant"
            >
              <b-col
                  md="2"
              >
                {{ bar.variant }}
              </b-col>
              <b-col
                  md="10"
              >
                <b-progress
                    :key="bar.variant"
                    :value="bar.value"
                    class="mb-25"
                />
              </b-col>
            </b-row>
          </div>
        </div>
        <!--/ follower projects rank -->
      </b-card>
    </swiper-slide>

    <div
        slot="pagination"
        class="swiper-pagination"
    />
  </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import {
  BCard, BAvatar, BBadge, BProgress, BRow, BCol, BFormRating,
} from 'bootstrap-vue'
import 'swiper/css/swiper.css'

export default {
  components: {
    BCard,
    BBadge,
    BAvatar,
    BProgress,
    BFormRating,
    Swiper,
    SwiperSlide,
    BRow,
    BCol,
  },
  props: {
    doctorsData: {
      type: Array,
      required: true,
    },
  },
  data() {
    return {
      swiperOptions: {
        slidesPerView: 4,
        spaceBetween: 50,
        pagination: {
          el: '.swiper-pagination',
          clickable: true,
        },
        breakpoints: {
          1200: {
            slidesPerView: 4,
            spaceBetween: 20,
          },
          992: {
            slidesPerView: 2,
            spaceBetween: 20,
          },
          768: {
            slidesPerView: 2,
            spaceBetween: 20,
          },
          320: {
            slidesPerView: 1,
            spaceBetween: 20,
          },
        },
      },
      bars: [
        { variant: '5', value: 89 },
        { variant: '4', value: 25 },
        { variant: '3', value: 50 },
        { variant: '2', value: 63 },
        { variant: '1', value: 5 },
      ],
    }
  },

}
</script>
