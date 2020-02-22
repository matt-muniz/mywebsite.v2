<template>
  <div>
    <!-- System Bar -->
    <v-system-bar fixed window app>
      <v-spacer></v-spacer>
      <v-layout>
        <span class="social_icons" v-for="item in social_icons" :key="item.alt">
          <v-tooltip :color="item.color" bottom>
            <template v-slot:activator="{on: tooltip}">
              <nuxt-link v-on="{...tooltip}" :to="item.to">
                <font-awesome-icon class="icon" :icon="['fab', item.src]" />
                <!-- <v-img src="instagram.svg" alt></v-img> -->
              </nuxt-link>
            </template>
            <span>{{item.alt}}</span>
          </v-tooltip>
        </span>
      </v-layout>
      <v-spacer></v-spacer>
      <!-- Contact on screens bigger than mobile -->
      <v-layout justify-center v-if="!mobile">
        <p v-for="item in contact" :key="item.strong">
          <strong>{{ item.strong }}</strong>
          <a :href="item.to">
            <span>{{ item.span }}</span>
          </a>
        </p>
      </v-layout>
      <!-- Contact on mobile -->
      <v-layout v-if="mobile" justify-end>
        <v-menu max-width="100%" offset-y>
          <template v-slot:activator="{ on }">
            <span class="mr-1" v-on="on">Contact</span>
            <span>
              <font-awesome-icon
                v-on="on"
                style="height: 100%"
                class="icon"
                :icon="['fas', 'chevron-down']"
              />
            </span>
          </template>
          <v-list>
            <v-list-item v-for="item in contact" :key="item.strong">
              <v-list-item-title>
                <p>
                  <strong>{{ item.strong }}</strong>
                  <br />
                  <a :href="item.to">
                    <span>{{ item.span }}</span>
                  </a>
                </p>
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-layout>
      <v-spacer></v-spacer>
    </v-system-bar>
    <!-- App bar -->
    <v-app-bar absolute app>
      <img class="mr-2" height="100%" src="logo.png" alt />
      <h1 style="color: #0f6d97">Business Builder Elite</h1>
      <v-spacer></v-spacer>
      <v-layout justify-center v-if="!mobile">
        <p v-for="item in pages" :key="item.title">
          <nuxt-link :to="item.to">{{ item.title }}</nuxt-link>
        </p>
      </v-layout>
      <v-layout v-if="mobile" justify-end>
        <v-menu max-width="100%" offset-y>
          <template v-slot:activator="{on}">
            <span>
              <v-icon v-on="on">mdi-menu</v-icon>
            </span>
          </template>
          <v-list>
            <v-list-item v-for="item in pages" :key="item.title">
              <v-list-item-title>
                <p>
                  <nuxt-link :to="item.to">{{ item.title }}</nuxt-link>
                </p>
              </v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-layout>
      <v-spacer></v-spacer>
    </v-app-bar>
  </div>
</template>

<script>
export default {
  data() {
    return {
      mobileWidth: null,
      mobile: true,
      contact: [
        {
          strong: 'Email:',
          span: 'businessbuilderelite@gmail.com',
          to: 'mailto:businessbuilderelite@gmail.com'
        },
        {
          strong: 'Number:',
          span: '978-325-2105',
          to: 'tel:9783252105'
        }
      ],
      social_icons: [
        {
          alt: 'facebook',
          src: 'facebook',
          to: '/inspire',
          color: '#4c76be'
        },
        {
          alt: 'instagram',
          src: 'instagram',
          to: '/',
          color: '#f49c4e'
        },
        {
          alt: 'twitter',
          src: 'twitter',
          to: '/',
          color: '#4ec8fb'
        },
        {
          alt: 'linkedIn',
          src: 'linkedin',
          to: '/',
          color: '#2a87c9'
        }
      ],
      pages: [
        {
          title: 'Portfolio',
          to: '/'
        },
        {
          title: 'About',
          to: '/'
        },
        {
          title: 'Services',
          to: '/inspire'
        }
      ]
    }
  },

  methods: {
    mobileResize() {
      this.mobileWidth = window.innerWidth

      this.mobileWidth <= 700 ? (this.mobile = true) : (this.mobile = false)
    }
  },
  mounted() {
    this.mobileWidth = window.innerWidth
    if (this.mobileWidth >= 700) {
      this.mobile = false
    }
    window.addEventListener('resize', this.mobileResize)
  }
}
</script>

<style>
.v-system-bar p {
  font-size: 0.8rem;
}
.v-system-bar p,
.v-app-bar p {
  padding: 0;
  margin: 0;
}
.v-system-bar span {
  color: #5a5a5a;
}

a {
  text-decoration: none;
  margin-right: 10px;
}
.social_icons {
  font-size: 1.2rem;
  margin: 0 5px;
}
.icon {
  color: #5a5a5a;
}

@media (max-width: 450px) {
  .v-app-bar h1 {
    font-size: 130%;
  }
  .v-app-bar img {
    height: 80%;
  }
}
</style>