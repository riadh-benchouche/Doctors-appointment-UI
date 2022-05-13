<template>
  <b-container>
    <b-card
      class="profile-header mb-2"
      :img-src="headerData.coverImg"
      img-top
      alt="cover photo"
      body-class="p-0"
    >
      <!-- profile picture -->
      <div class="position-relative">
        <div class="profile-img-container d-flex align-items-center">
          <div class="profile-img">
            <b-img
              :src="headerData.avatar"
              rounded
              fluid
              alt="profile photo"
            />
          </div>
          <!-- profile title -->
          <div class="profile-title ml-3 pb-2">
            <h2 class="text-white">
              {{ headerData.username }}
            </h2>
            <p class="text-white">
              {{ headerData.specialite }}
            </p>
            <p class="text-white">
              {{ headerData.company }}
              <feather-icon
                icon="MapPinIcon"
                class="ml-75 "
              />
              {{ headerData.location }}
            </p>
          </div>
          <!--/ profile title -->
        </div>
      </div>
      <!--/ profile picture -->

      <!-- profile navbar -->
      <div class="profile-header-nav">
        <b-navbar
          toggleable="md"
          type="light"
        >
          <!-- toggle button -->
          <b-navbar-toggle
            class="ml-auto"
            target="nav-text-collapse"
          >
            <feather-icon
              icon="AlignJustifyIcon"
              size="21"
            />
          </b-navbar-toggle>
          <!--/ toggle button -->

          <!-- collapse -->
          <b-collapse
            id="nav-text-collapse"
            is-nav
          >
            <b-tabs
              pills
              class="profile-tabs mt-1 mt-md-0"
              nav-class="mb-0"
            >
              <template #tabs-end>
                <b-button
                  variant="primary"
                  class="ml-auto"
                >
                  <feather-icon
                    icon="EditIcon"
                    class="d-block d-md-none"
                  />
                  <span class="font-weight-bold d-none d-md-block">Prendre rendez-vous</span>
                </b-button>
              </template>
            </b-tabs>

          </b-collapse>
          <!--/ collapse -->
        </b-navbar>
      </div>
      <!--/ profile navbar -->
    </b-card>
  </b-container>
</template>

<script>
import {
  BCard, BImg, BNavbar, BNavbarToggle, BCollapse, BTabs, BButton, BContainer,
} from 'bootstrap-vue'
import Ripple from 'vue-ripple-directive'

export default {
  components: {
    BCard,
    BContainer,
    BTabs,
    BButton,
    BNavbar,
    BNavbarToggle,
    BCollapse,
    BImg,
  },
  directives: {
    Ripple,
  },
  props: {
    headerData: {
      type: Object,
      default: () => {
      },
    },
  },
}
</script>
