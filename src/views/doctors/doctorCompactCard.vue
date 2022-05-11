<template>
  <b-row>
    <b-col
      v-for="(doctor) in doctorsData"
      :key="doctor.id"
      cols="4"
    >
      <b-card>
        <div class="d-flex justify-content-start">
          <b-avatar
            :src="doctor.avatar"
            :text="avatarText(doctor.fullName)"
            size="104px"
            rounded
          />
          <div class="d-flex flex-column ml-1">
            <div class="mb-1">
              <h4 class="mb-0 text-primary">
                {{ doctor.fullName }}
              </h4>
              <table class="mt-2 mt-xl-0 w-100">
                <tr>
                  <th class="pb-50">
                    <span class="font-weight-bold">Spécialité </span>
                  </th>
                  <td class="pb-50">
                    {{ doctor.specialite }}
                  </td>
                </tr>
                <tr>
                  <th class="pb-50">
                    <span class="font-weight-bold">Hopital</span>
                  </th>
                  <td class="pb-50 text-capitalize">
                    {{ doctor.company }}
                  </td>
                </tr>
                <tr>
                  <th class="pb-50">
                    <feather-icon
                      icon="MapPinIcon"
                      class="mr-50 "
                    />
                    <span class="font-weight-bold">Country</span>
                  </th>
                  <td class="pb-50 ml-1">
                    {{ doctor.country }}
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

export default {
  components: {
    BCard,
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
  setup(props) {
    console.log(props.doctorsData)
    return {
      avatarText,
    }
  },
}
</script>

<style>

</style>
