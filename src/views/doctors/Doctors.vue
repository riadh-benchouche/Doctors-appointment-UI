<template>
  <section>
    <b-container>
      <b-row class="mb-2 d-flex justify-content-between">
        <b-col
          md="8"
        >
          <div class="demo-vertical-spacing ">
            <b-input-group class="input-group-merge">
              <b-input-group-prepend is-text>
                <feather-icon icon="SearchIcon" />
              </b-input-group-prepend>
              <b-form-input placeholder="Search" />
            </b-input-group>
          </div>
        </b-col>
        <b-col
          md="4"
        >
          <v-select
            :clearable="false"
            :dir="$store.state.appConfig.isRTL ? 'rtl' : 'ltr'"
            :options="location"
            :reduce="val => val.id"
            label="label"
            placeholder="Location"
          />
        </b-col>
      </b-row>
    </b-container>
    <b-row>
      <doctor-compact-card :doctors-data="data"></doctor-compact-card>
    </b-row>
  </section>
</template>

<script>
import {
  BRow,
  BContainer,
  BCol,
  BFormInput,
  BInputGroup,
  BInputGroupPrepend,
} from 'bootstrap-vue'
import DoctorCompactCard from '@/views/doctors/doctorCompactCard.vue'
import vSelect from 'vue-select'

export default {
  components: {
    DoctorCompactCard,
    vSelect,
    BRow,
    BContainer,
    BCol,
    BFormInput,
    BInputGroup,
    BInputGroupPrepend,
  },
  data() {
    return {
      data: [
        {
          id: 1,
          fullName: 'Halsey Redmore',
          company: 'CHU Mustapha bacha',
          specialite: 'Chirurgie dentaire',
          country: 'Albania',
          contact: '(472) 607-9137',
          email: 'hredmore1@imgur.com',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/avatars/10.png'),
        },
        {
          id: 2,
          fullName: 'Marjory Sicely',
          company: 'Oozz PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'Russia',
          contact: '(321) 264-4599',
          email: 'msicely2@who.int',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/avatars/1.png'),
        },
        {
          id: 3,
          fullName: 'Cyrill Risby',
          company: 'Oozz PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'China',
          contact: '(923) 690-6806',
          email: 'crisby3@wordpress.com',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/avatars/9.png'),
        },
        {
          id: 4,
          fullName: 'Maggy Hurran',
          company: 'Aimbo PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'Pakistan',
          contact: '(669) 914-1078',
          email: 'mhurran4@yahoo.co.jp',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/avatars/10.png'),
        },
        {
          id: 5,
          fullName: 'Cyrill Risby',
          company: 'Oozz PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'China',
          contact: '(923) 690-6806',
          email: 'crisby3@wordpress.com',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/avatars/9.png'),
        },
        {
          id: 6,
          fullName: 'Maggy Hurran',
          company: 'Aimbo PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'Pakistan',
          contact: '(669) 914-1078',
          email: 'mhurran4@yahoo.co.jp',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/avatars/10.png'),
        },
      ],
      location: [
        {
          id: 1,
          label: 'Alger',
        },
        {
          id: 2,
          label: 'Albania',
        },
        {
          id: 3,
          label: 'Russia',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.per-page-selector {
  width: 90px;
}

.v-select {
  &.item-selector-title,
  & {
    background-color: #fff;

    .dark-layout & {
      background-color: unset;
    }
  }
}
</style>

<style lang="scss">
@import '~@core/scss/vue/libs/vue-select.scss';
</style>
