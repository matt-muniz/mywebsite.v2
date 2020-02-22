<template>
  <main>
    <!-- Above the fold -->

    <section class="section section_one text-center">
      <v-row style="height: 100%" align-content="center">
        <v-col style="padding: 0">
          <!-- Offer -->
          <div>
            <v-card>
              <v-img src="img1.jpg" height="100%">
                <v-row class="content_container" :align="alignment" :justify="justify">
                  <v-col style="padding: 0">
                    <v-row class="content" :align="alignment" :justify="justify">
                      <v-col>
                        <h1 class="heading text-uppercase">
                          <span class="red--text">Stop</span> Leaving Money
                          <br />on the Table
                        </h1>
                      </v-col>
                    </v-row>
                    <v-row class="content" :align="alignment" :justify="justify">
                      <v-col>
                        <h4 class="subHeading text-uppercase">
                          Get your
                          <span class="red--text">free</span> social media
                          <br />marketing strategy Below!
                        </h4>
                      </v-col>
                    </v-row>
                    <v-row class="content" :align="alignment" :justify="justify">
                      <v-col>
                        <v-btn class="btn seciont_one-btn info lighten-1" text>Click now</v-btn>
                      </v-col>
                    </v-row>
                  </v-col>
                </v-row>
              </v-img>
            </v-card>
          </div>
          <!-- Grab Attention -->
          <v-row :align="alignment" :justify="justify">
            <v-col>
              <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptatem, minus?</p>
            </v-col>
          </v-row>
          <!-- Action -->
          <v-row :align="alignment" :justify="justify">
            <v-col>
              <v-btn class="btn error lighten-1" text>Click now</v-btn>
            </v-col>
          </v-row>
        </v-col>
      </v-row>
    </section>

    <!-- Beflow the fold -->
    <section>below the fold</section>
  </main>
</template>

<script>
export default {
  // head(){
  //   return {
  //     link: [
  //       { rel: 'stylesheet', href: ''}
  //     ]
  //   }
  // },
  data() {
    return {
      alignment: 'center',
      justify: 'center',
      color: '#0f6d97'
    }
  }
}
</script>

<style scoped>
.btn {
  font-size: 0.8rem;
  height: 30px !important;
}
.section_one {
  height: calc(100vh - 96px);
}
.content_container {
  height: 100%;
}
.row {
  width: 100%;
  margin: auto;
}
.heading {
  font-family: monsterat;
  font-size: 1.4rem;
}
.subHeading {
  font-family: monsterat;
}
@media (min-width: 450px) {
  .btn {
    font-size: 1.1rem;
    height: 36px !important;
  }
  .heading {
    font-size: 2.1rem;
  }
  .subHeading {
    font-size: 1.6rem;
  }
}
@media (min-width: 700px) {
  .heading {
    font-size: 2.4rem;
  }
  .subHeading {
    font-size: 2rem;
  }
}
</style>
<style>
.v-image__image {
  opacity: 0.8 !important;
  background-blend-mode: soft-light;
  background-color: #0f6c97a6;
}
</style>