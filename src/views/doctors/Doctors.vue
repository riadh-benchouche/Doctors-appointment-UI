<template>
  <section>
    <b-container>
      <b-row class="mb-2 d-flex justify-content-between">
        <b-col
            cols="8"
        >
          <div class="demo-vertical-spacing ">
            <b-input-group class="input-group-merge">
              <b-input-group-prepend is-text>
                <feather-icon icon="SearchIcon"/>
              </b-input-group-prepend>
              <b-form-input placeholder="Search"/>
            </b-input-group>
          </div>
        </b-col>
        <b-col
            cols="4">
          <v-select
              :dir="$store.state.appConfig.isRTL ? 'rtl' : 'ltr'"
              :options="location"
              :reduce="val => val.id"
              label="label"
              placeholder="Location"
          />
        </b-col>
      </b-row>
    </b-container>
    <b-row class="pb-md-1 px-md-3">
      <doctor-card :doctors-data="data"></doctor-card>
    </b-row>
    <b-row class="d-flex justify-content-between pb-md-1 px-md-3">
      <h1 class="text-primary">Recommended</h1>
      <section>
        <b-button
            v-if="!ShallShowFilter"
            v-ripple.400="'rgba(255, 255, 255, 0.15)'"
            variant="primary"
            class="btn-icon"
            @click="ShallShowFilter = true"
        >
          <feather-icon icon="FilterIcon" size="20"/>
        </b-button>
        <b-button
            v-if="ShallShowFilter"
            v-ripple.400="'rgba(255, 255, 255, 0.15)'"
            variant="primary"
            class="btn-icon"
            @click="ShallShowFilter = false"
        >
          <feather-icon v-if="ShallShowFilter" icon="XIcon" size="20"/>
        </b-button>
      </section>
    </b-row>
    <b-container v-if="ShallShowFilter">
      <b-row class="mb-2 d-flex justify-content-between">
        <b-col
            md="4"
        >
          <div class="demo-vertical-spacing ">
            <b-input-group class="input-group-merge">
              <b-input-group-prepend is-text>
                <feather-icon icon="SearchIcon"/>
              </b-input-group-prepend>
              <b-form-input placeholder="Search..."/>
            </b-input-group>
          </div>
        </b-col>
        <b-col
            md="4"
        >
          <v-select
              :dir="$store.state.appConfig.isRTL ? 'rtl' : 'ltr'"
              :options="specialite"
              :reduce="val => val.id"
              label="label"
              placeholder="Specialite"
          />
        </b-col>
        <b-col
            md="4"
        >
          <v-select
              :dir="$store.state.appConfig.isRTL ? 'rtl' : 'ltr'"
              :options="location"
              :reduce="val => val.id"
              label="label"
              placeholder="Location"
          />
        </b-col>
      </b-row>
    </b-container>
    <b-row class="px-md-3">
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
  BButton,
} from 'bootstrap-vue'
import DoctorCompactCard from '@/views/doctors/doctorCompactCard.vue'
import DoctorCard from '@/views/doctors/DoctorCard.vue'
import vSelect from 'vue-select'
import Ripple from 'vue-ripple-directive'

export default {
  components: {
    DoctorCompactCard,
    DoctorCard,
    vSelect,
    BRow,
    BContainer,
    BCol,
    BFormInput,
    BInputGroup,
    BInputGroupPrepend,
    BButton,
  },
  directives: {
    Ripple,
  },
  data() {
    return {
      ShallShowFilter: false,
      data: [
        {
          id: 1,
          fullName: 'Halsey Redmore',
          company: 'CHU Mustapha bacha',
          specialite: 'Chirurgie dentaire',
          country: 'Albania',
          contact: '(472) 607-9137',
          rating: '2',
          email: 'hredmore1@imgur.com',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
        },
        {
          id: 2,
          fullName: 'Marjory Sicely',
          company: 'Oozz PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'Russia',
          contact: '(321) 264-4599',
          rating: '3',
          email: 'msicely2@who.int',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
        },
        {
          id: 3,
          fullName: 'Cyrill Risby',
          company: 'Oozz PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'China',
          contact: '(923) 690-6806',
          rating: '5',
          email: 'crisby3@wordpress.com',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
        },
        {
          id: 4,
          fullName: 'Maggy Hurran',
          company: 'Aimbo PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'Pakistan',
          contact: '(669) 914-1078',
          rating: '4',
          email: 'mhurran4@yahoo.co.jp',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
        },
        {
          id: 5,
          fullName: 'Cyrill Risby',
          company: 'Oozz PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'China',
          contact: '(923) 690-6806',
          rating: '1',
          email: 'crisby3@wordpress.com',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
        },
        {
          id: 6,
          fullName: 'Maggy Hurran',
          company: 'Aimbo PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'Pakistan',
          contact: '(669) 914-1078',
          rating: '5',
          email: 'mhurran4@yahoo.co.jp',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
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
      specialite: [
        {
          id: 1,
          label: 'Cardiologue',
        },
        {
          id: 2,
          label: 'Chirurgien dentiste',
        },
        {
          id: 3,
          label: 'Ophtalmologue',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
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
