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
                    v-ripple.400="'rgba(113, 102, 240, 0.15)'"
                    v-b-modal.modal-1
                    variant="primary"
                    class="ml-auto"
                >
                  <feather-icon
                      icon="CalendarIcon"
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
      <b-modal
          no-close-on-backdrop
          ok-variant="primary"
          header-text-variant="primary"
          id="modal-1"
          title="Take an appointment with"
          ok-only
          ok-title="Confirm"
          class="text-primary"
      >
        <doctor-compact-card-modal :doctors-data="data"></doctor-compact-card-modal>
        <b-card-text>
          <b-form-group>
            <h5 class="text-primary">Date & TIme</h5>
            <flat-pickr
                v-model="dateNtim"
                class="form-control"
                :config="{ enableTime: true,dateFormat: 'Y-m-d H:i'}"
            />
          </b-form-group>
        </b-card-text>
      </b-modal>
      <!--/ profile navbar -->
    </b-card>
  </b-container>
</template>

<script>
import {
  BCard, BImg, BNavbar, BNavbarToggle, BCollapse, BTabs, BButton, BContainer, BModal, VBModal, BCardText, BFormGroup,
} from 'bootstrap-vue'
import Ripple from 'vue-ripple-directive'
import flatPickr from 'vue-flatpickr-component'
import DoctorCompactCardModal from '@/views/doctors/components/doctorCompactCardModal.vue'

export default {
  components: {
    BCard,
    BContainer,
    BTabs,
    BFormGroup,
    flatPickr,
    BButton,
    BNavbar,
    BNavbarToggle,
    BCollapse,
    BImg,
    BModal,
    BCardText,
    DoctorCompactCardModal,
  },
  directives: {
    'b-modal': VBModal,
    Ripple,
  },
  props: {
    headerData: {
      type: Object,
      default: () => {
      },
    },
  },
  data() {
    return {
      dateNtim: null,
      data: {
        id: 1,
        fullName: 'Dr. Amine Mohamed',
        company: 'CHU Mustapha',
        specialite: 'Chirurgie dentaire',
        country: 'Alger',
        contact: '(472) 607-9137',
        rating: '4,5',
        email: 'hredmore1@imgur.com',
        // eslint-disable-next-line global-require
        avatar: require('@/assets/images/profile/user-uploads/user-01.jpg'),
      },
    }
  },

}
</script>
<style lang="scss">
@import '~@core/scss/vue/libs/vue-flatpicker.scss';
</style>
