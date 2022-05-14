<template>
  <div id="user-profile">
    <profile-header :header-data="profileData.header" />
    <section id="profile-info" class="px-md-3">
      <b-card>
      <b-row>
        <b-col
          lg="3"
          cols="12"
          order="2"
          order-lg="1"
        >
          <similar-doctor-compact-card :doctors-data="data"></similar-doctor-compact-card>
        </b-col>
        <b-col
          lg="6"
          cols="12"
          order="1"
          order-lg="2"
        >
          <profile-about :about-data="profileData.userAbout" />
        </b-col>
        <b-col
          lg="3"
          cols="12"
          order="3"
        >
          <profile-feed-back :twitter-feed="profileData.twitterFeeds" />
        </b-col>
      </b-row>
      </b-card>
    </section>
  </div>
</template>

<script>
import { BRow, BCol, BCard } from 'bootstrap-vue'
import SimilarDoctorCompactCard from '@/views/doctors/components/SimilarDoctorCompactCard.vue'
import ProfileFeedBack from '@/views/doctors/components/ProfileFeedBack.vue'
import ProfileAbout from '@/views/doctors/components/ProfileAbout.vue'
import ProfileHeader from './components/ProfileHeader.vue'

/* eslint-disable global-require */
export default {
  components: {
    BRow,
    BCol,
    BCard,
    ProfileHeader,
    SimilarDoctorCompactCard,
    ProfileFeedBack,
    ProfileAbout,
  },
  data() {
    return {
      data: [
        {
          id: 1,
          fullName: 'Halsey Redmore',
          company: 'CHU Mustapha',
          specialite: 'Chirurgie dentaire',
          country: 'Albania',
          contact: '(472) 607-9137',
          rating: '2.8',
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
          fullName: 'Cyrill Risby',
          company: 'Oozz PVT LTD',
          specialite: 'Chirurgie dentaire',
          country: 'China',
          contact: '(923) 690-6806',
          rating: '4.6',
          email: 'crisby3@wordpress.com',
          // eslint-disable-next-line global-require
          avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
        },
      ],
      profileData: {
        header: {
          avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
          username: 'Dr. Amine Mohamed',
          specialite: 'Spécialité: Chirurgie dentaire',
          company: 'CHU Mustapha',
          location: 'Alger',
          coverImg: require('@/assets/images/profile/user-uploads/timeline.jpg'),
        },
        userAbout: {
          about: 'Maitre assistant hospitalo-universitaire en Chirurgie dentaire.',
          Location: '28 Rue Didouche Mourad, Alger Ctre 16000',
          email: 'bucketful@fiendhead.org',
          contact: '(923) 690-6806',
        },
        twitterFeeds: [
          {
            imgUrl: require('@/assets/images/avatars/5-small.png'),
            title: 'Gertrude Stevens',
            id: '1',
            desc: 'Le Dr. Mohamed Amine est le plus expérimentés et le plus doux des professionnels de santé. Il s\'agit de l\'ancienne école avec une connaissance parfaite de son métier. À recommander pour les mamans cherchant à voir leurs enfants en excellente santé.',
          },
          {
            imgUrl: require('@/assets/images/avatars/12-small.png'),
            title: 'Lura Jones',
            id: '2',
            desc: 'Reception agréable et consultation professionnelle magnifique. Merci à l\'équipe pour leurs efforts.',
          },
          {
            imgUrl: require('@/assets/images/avatars/1-small.png'),
            title: 'Norman Gross',
            id: '3',
            desc: 'Un médecin très compétent , je le recommande vivement , bonne continuation !',
          },
          {
            imgUrl: require('@/assets/images/avatars/8-small.png'),
            title: 'Norman Gross',
            id: '3',
            desc: 'Un médecin très compétent , je le recommande vivement , bonne continuation !',
          },
        ],
      },
    }
  },
}
/* eslint-disable global-require */
</script>

<style lang="scss">
@import '~@core/scss/vue/pages/page-profile.scss';
</style>
