<template>
  <div>
    <h3 class="mb-2 text-primary">Docteur Similaire</h3>
    <b-row>
      <b-col
          v-for="(doctor) in doctorsData"
          :key="doctor.id"
          cols="12"
      >
        <div class="d-flex justify-content-start">
          <b-avatar
              size="90"
              variant="primary"
              :src="doctor.avatar"
              :text="avatarText(doctor.fullName)"
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
                    <span class="font-weight-bold">{{ doctor.specialite }} </span>
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
                      <b-form-rating
                          readonly
                          :value="doctor.rating"
                          variant="warning"
                          inline
                          no-border
                          class="mt-0"
                      />
                    </div>
                  </td>
                </tr>
              </table>
            </div>
          </div>
        </div>
      </b-col>
    </b-row>
  </div>
</template>

<script>
import {
  BAvatar, BRow, BCol, BFormRating,
} from 'bootstrap-vue'
import { avatarText } from '@core/utils/filter'

export default {
  components: {
    BFormRating,
    BRow,
    BCol,
    BAvatar,
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
