<template>
  <section>
    <h3 class="mb-2 text-primary">À propos</h3>
    <div
      v-for="(data,key,index) in aboutData"
      :key="data.title"
      :class="index ? 'mt-2':''"
    >
      <h5 class="text-capitalize mb-50 text-primary">
        {{ key }}
      </h5>
      <b-card-text >
        {{ data }}
      </b-card-text>
    </div>
    <b-container class="p-md-3">
    <b-card class="bg-light">
      <div class="d-flex justify-content-between align-items-center">
        <div class="text-center">
          <h4 class="text-muted font-weight-bolder">
            Rating
          </h4>
          <h1 class="mb-0 text-primary">
            4,8
          </h1>
          <b-form-rating
              readonly
              value="4,8"
              variant="warning"
              inline
              no-border
              class="mt-0 bg-light"
          />
        </div>
        <div class="progress-wrapper w-100 d-flex justify-content-start">
          <b-container>
          <b-row
              v-for="bar in bars"
              :key="bar.id"
          >
            <b-col
                cols="2"
            >
              {{ bar.id }}
            </b-col>
            <b-col
                cols="10"
            >
              <b-progress
                  :key="bar.id"
                  :value="bar.value"
                  class="mb-25"
              />
            </b-col>
          </b-row>
          </b-container>
        </div>
      </div>
    </b-card>
    </b-container>
  </section>
</template>

<script>
import {
  BRow,
  BContainer,
  BCol,
  BCardText,
  BProgress,
  BCard,
  BFormRating,
} from 'bootstrap-vue'

export default {
  components: {
    BContainer,
    BRow,
    BCol,
    BCardText,
    BProgress,
    BCard,
    BFormRating,
  },
  props: {
    aboutData: {
      type: Object,
      default: () => {},
    },
  },
  data() {
    return {
      bars: [
        { id: '5', value: 89 },
        { id: '4', value: 25 },
        { id: '3', value: 50 },
        { id: '2', value: 63 },
        { id: '1', value: 5 },
      ],
    }
  },

}
</script>
