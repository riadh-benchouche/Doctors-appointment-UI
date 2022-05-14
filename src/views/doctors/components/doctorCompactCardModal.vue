<template>
  <b-row>
    <b-col
      cols="12"
    >
      <b-card>
        <div class="d-flex justify-content-start">
          <b-avatar
            :src="doctorsData.avatar"
            :text="avatarText(doctorsData.fullName)"
            size="104px"
            rounded
            :to="{name:'doctorsData-detail', params: {id : doctorsData.id}}"
          />
          <div class="d-flex flex-column ml-1">
            <div class="mb-1">
              <h4
                class="mb-0 text-primary"
                role="button"
                @click="$router.push({name:'doctorsData-detail', params: {id : doctorsData.id}})"
              >
                {{ doctorsData.fullName }}
              </h4>
              <table class="mt-2 mt-xl-0 w-100">
                <tr>
                  <th>
                    <span class="font-weight-bold">Spécialité:{{ doctorsData.specialite }}</span>
                  </th>
                </tr>
                <tr>
                  <th class="pb-50">
                    <span class="pb-50 text-capitalize font-weight-lighter">{{ doctorsData.company }}</span>
                  </th>
                </tr>
                <tr>
                  <th>
                    <feather-icon
                      icon="MapPinIcon"
                      class="mr-75"
                    />
                    <span class=" pb-25 font-weight-lighter">{{ doctorsData.country }}</span>
                  </th>
                  <td class="float-right">
                    <div>
                      <b-form-rating
                          readonly
                          :value="doctorsData.rating"
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
      </b-card>
    </b-col>
  </b-row>
</template>

<script>
import {
  BCard, BAvatar, BRow, BCol, BFormRating,
} from 'bootstrap-vue'
import { avatarText } from '@core/utils/filter'

export default {
  components: {
    BCard,
    BRow,
    BCol,
    BAvatar,
    BFormRating,
  },
  props: {
    doctorsData: {
      type: Object,
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
