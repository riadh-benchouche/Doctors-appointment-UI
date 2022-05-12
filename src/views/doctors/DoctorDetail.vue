<template>
  <div id="user-profile">
    <profile-header :header-data="profileData.header" />
    <!-- profile info  -->
    <section id="profile-info">
      <b-row>
        <!-- about suggested page and twitter feed -->
        <b-col
          lg="3"
          cols="12"
          order="2"
          order-lg="1"
        >
          <b-card><h1>test</h1></b-card>
        </b-col>
        <!--/ about suggested page and twitter feed -->

        <!-- post -->
        <b-col
          lg="6"
          cols="12"
          order="1"
          order-lg="2"
        >
          <b-card><h1>test</h1></b-card>
        </b-col>
        <!-- post -->

        <!-- latest photos suggestion and polls -->
        <b-col
          lg="3"
          cols="12"
          order="3"
        >
          <b-card><h1>test</h1></b-card>
        </b-col>
      </b-row>
    </section>
    <!--/ profile info  -->
  </div>
</template>

<script>
import { BRow, BCol, BCard } from 'bootstrap-vue'

import ProfileHeader from './components/ProfileHeader.vue'

/* eslint-disable global-require */
export default {
  components: {
    BRow,
    BCol,
    BCard,

    ProfileHeader,

  },
  data() {
    return {
      profileData: {
        header: {
          avatar: require('@/assets/images/portrait/small/avatar-s-2.jpg'),
          username: 'Kitty Allanson',
          designation: 'UI/UX Designer',
          coverImg: require('@/assets/images/profile/user-uploads/timeline.jpg'),
        },
        userAbout: {
          about: 'Tart I love sugar plum I love oat cake. Sweet ⭐️ roll caramels I love jujubes. Topping cake wafer.',
          joined: 'November 15, 2015',
          lives: 'New York, USA',
          email: 'bucketful@fiendhead.org',
          website: 'www.pixinvent.com',
        },
        suggestedPages: [
          {
            avatar: require('@/assets/images/avatars/12-small.png'),
            username: 'Peter Reed',
            subtitle: 'Company',
            favorite: false,
          },
          {
            avatar: require('@/assets/images/avatars/1-small.png'),
            username: 'Harriett Adkins',
            subtitle: 'Company',
            favorite: false,
          },
          {
            avatar: require('@/assets/images/avatars/10-small.png'),
            username: 'Juan Weaver',
            subtitle: 'Company',
            favorite: false,
          },
          {
            avatar: require('@/assets/images/avatars/3-small.png'),
            username: 'Claudia Chandler',
            subtitle: 'Company',
            favorite: false,
          },
          {
            avatar: require('@/assets/images/avatars/5-small.png'),
            username: 'Earl Briggs',
            subtitle: 'Company',
            favorite: true,
          },
          {
            avatar: require('@/assets/images/avatars/6-small.png'),
            username: 'Jonathan Lyons',
            subtitle: 'Beauty Store',
            favorite: false,
          },
        ],
        twitterFeeds: [
          {
            imgUrl: require('@/assets/images/avatars/5-small.png'),
            title: 'Gertrude Stevens',
            id: 'tiana59 ',
            tags: '#design #fasion',
            desc: 'I love cookie chupa chups sweet tart apple pie ⭐️ chocolate bar.',
            favorite: false,
          },
          {
            imgUrl: require('@/assets/images/avatars/12-small.png'),
            title: 'Lura Jones',
            id: 'tiana59 ',
            tags: '#vuejs #code #coffeez',
            desc: 'Halvah I love powder jelly I love cheesecake cotton candy. 😍',
            favorite: true,
          },
          {
            imgUrl: require('@/assets/images/avatars/1-small.png'),
            title: 'Norman Gross',
            id: 'tiana59 ',
            tags: '#sketch #uiux #figma',
            desc: 'Candy jelly beans powder brownie biscuit. Jelly marzipan oat cake cake.',
            favorite: false,
          },
        ],
        suggestions: [
          {
            avatar: require('@/assets/images/portrait/small/avatar-s-9.jpg'),
            name: 'Peter Reed',
            mutualFriend: '6 Mutual Friends',
          },
          {
            avatar: require('@/assets/images/portrait/small/avatar-s-6.jpg'),
            name: 'Harriett Adkins',
            mutualFriend: '3 Mutual Friends',
          },
          {
            avatar: require('@/assets/images/portrait/small/avatar-s-7.jpg'),
            name: 'Juan Weaver',
            mutualFriend: '1 Mutual Friends',
          },
          {
            avatar: require('@/assets/images/portrait/small/avatar-s-8.jpg'),
            name: 'Claudia Chandler',
            mutualFriend: '16 Mutual Friends',
          },
          {
            avatar: require('@/assets/images/portrait/small/avatar-s-1.jpg'),
            name: 'Earl Briggs',
            mutualFriend: '4 Mutual Friends',
          },
          {
            avatar: require('@/assets/images/portrait/small/avatar-s-10.jpg'),
            name: 'Jonathan Lyons',
            mutualFriend: '25 Mutual Friends',
          },
        ],
        polls: [
          {
            name: 'RDJ',
            result: '82%',
            votedUser: [
              { img: require('@/assets/images/portrait/small/avatar-s-12.jpg'), username: 'Tonia Seabold' },
              { img: require('@/assets/images/portrait/small/avatar-s-5.jpg'), username: 'Carissa Dolle' },
              { img: require('@/assets/images/portrait/small/avatar-s-9.jpg'), username: 'Kelle Herrick' },
              { img: require('@/assets/images/portrait/small/avatar-s-10.jpg'), username: 'Len Bregantini' },
              { img: require('@/assets/images/portrait/small/avatar-s-11.jpg'), username: 'John Doe' },
            ],
          },
          {
            name: 'Chris Hemswort',
            result: '67%',
            votedUser: [
              { img: require('@/assets/images/portrait/small/avatar-s-9.jpg'), username: 'Tonia Seabold' },
              { img: require('@/assets/images/portrait/small/avatar-s-1.jpg'), username: 'Carissa Dolle' },
              { img: require('@/assets/images/portrait/small/avatar-s-8.jpg'), username: 'Jonathan Lyons' },
            ],
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
