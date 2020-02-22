<template>
  <v-app dark>
    <NavBar />
    <!-- Main content -->
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed">
      <span>&copy; {{ getCurrentYear }}</span>
    </v-footer>
  </v-app>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
export default {
  components: {
    NavBar
  },
  data() {
    return {
      currentDate: new Date(),
      currentYear: null,
      fixed: false
    }
  },
  computed: {
    getCurrentYear() {
      return (this.currentYear = this.currentDate.getFullYear())
    }
  }
}
</script>

<style>
</style>
