<template>
  <div>
    <v-sheet
      :height="$vuetify.breakpoint.smAndUp ? '90vh' : '100vh'"
      color="primary"
      tile
    >
      <v-img
        :key="image"
        :src="image"
        gradient="to top, rgba(160, 90, 70, .3), rgba(30, 40, 30, .85)"
        height="100%"
      >
        <v-container fill-height white--text>
          <v-row
            ><v-col align="center" justify="center">
              <h1
                :class="$vuetify.breakpoint.smAndUp ? 'display-3' : 'display-2'"
                v-text="title"
              />
              <div class="title font-weight-light" v-text="subtitle" />
              <v-btn
                class="align-self-end white--text mt-5"
                fab
                outlined
                @click="$vuetify.goTo('#get_train')"
              >
                <v-icon color="white">mdi-chevron-double-down</v-icon>
              </v-btn></v-col
            ></v-row
          >
        </v-container>
      </v-img>
    </v-sheet>
  </div>
</template>

<script>
export default {
  data: () => ({
    items: [
      {
        src: "static/enduro/9.jpg",
      },
      {
        src: "static/enduro/1.jpg",
      },
      {
        src: "static/enduro/3.jpg",
      },
      {
        src: "static/enduro/5.jpg",
      },
    ],
    titles: {
      home: {
        title: "Прокат мотоциклов эндуро в Москве!",
        subtitle: "Чем мы занимаемся? Смотри ниже :)",
      },
    },
  }),

  computed: {
    namespace() {
      if (!this.$route || !this.$route.name) return "";

      return this.$route.name.toLowerCase();
    },
    image() {
      // console.log("/static/" + this.namespace + "-hero.png");
      // console.log("/src/assets/home-hero.jpg");
      // return "/static/" + this.namespace + "-hero.png";
      return "static/enduro/9.jpg";
      // return "static/enduro/home-hero.jpg";
    },
    subtitle() {
      return "Чем мы занимаемся? Смотри ниже :)";
    },
    title() {
      return "Прокат мотоциклов эндуро в Москве!";
    },
  },
};
</script>
