<template>
  <b-row>
    <b-col
      v-for="(doctor) in doctorsData"
      :key="doctor.id"
      xl="4"
      md="6"
      sm="12"
    >
      <b-card>
        <div class="d-flex justify-content-start">
          <b-avatar
            :src="doctor.avatar"
            :text="avatarText(doctor.fullName)"
            size="104px"
            rounded
            :to="{name:'doctor-detail', params: {id : doctor.id}}"
          />
          <div class="d-flex flex-column ml-1">
            <div class="mb-1">
              <h4
                class="mb-0 text-primary"
                role="button"
                @click="$router.push({name:'doctor-detail', params: {id : doctor.id}})"
              >
                {{ doctor.fullName }}
              </h4>
              <table class="mt-2 mt-xl-0 w-100">
                <tr>
                  <th>
                    <span class="font-weight-bold">Spécialité: {{ doctor.specialite }} </span>
                  </th>
                </tr>
                <tr>
                  <th class="pb-50">
                    <span class="pb-50 text-capitalize font-weight-lighter">{{ doctor.company }}</span>
                  </th>
                </tr>
                <tr>
                  <th>
                    <feather-icon
                      icon="MapPinIcon"
                      class="mr-75"
                    />
                    <span class=" pb-25 font-weight-lighter">{{ doctor.country }}</span>
                  </th>
                  <td class="float-right">
                    <div>
                      <star-rating
                        :star-size="20"
                        :show-rating="false"
                        :rounded-corners="true"
                      />
                    </div>
                  </td>
                </tr>
              </table>
            </div>
          </div>
        </div>
      </b-card>
    </b-col>
  </b-row>
</template>

<script>
import {
  BCard, BAvatar, BRow, BCol,
} from 'bootstrap-vue'
import { avatarText } from '@core/utils/filter'
import StarRating from 'vue-star-rating'

export default {
  components: {
    BCard,
    BRow,
    BCol,
    BAvatar,
    StarRating,
  },
  props: {
    doctorsData: {
      type: Array,
      required: true,
    },
  },
  setup() {
    return {
      avatarText,
    }
  },
}
</script>

<style>

</style>
