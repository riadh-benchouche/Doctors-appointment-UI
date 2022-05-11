<template>
  <b-row>
    <doctor-compact-card :doctors-data="data"></doctor-compact-card>
  </b-row>
</template>

<script>
import DoctorCompactCard from '@/views/doctors/doctorCompactCard.vue'

export default {
  components: {
    DoctorCompactCard,
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
  &.payment-selector {
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
