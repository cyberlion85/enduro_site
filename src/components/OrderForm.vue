<template>
  <v-row justify="center">
    <v-dialog v-model="dialog" persistent max-width="290">
      <!-- <template v-slot:activator="{ on, attrs }">
        <v-btn color="primary" dark v-bind="attrs" v-on="on">
          Open Dialog
        </v-btn>
      </template> -->
      <v-card>
        <v-card-title class="headline">
          Use Google's location service?
        </v-card-title>
        <v-card-text
          >Let Google help apps determine location. This means sending anonymous
          location data to Google, even when no apps are running.</v-card-text
        >
        <v-card-actions>
          <v-spacer></v-spacer>
          <v-btn color="green darken-1" text @click="destroyMethod()">
            old
          </v-btn>
          <v-btn color="green darken-1" text @click="fetchImages()">
            axios
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-row>
</template>
<script>
import axios from "axios";
export default {
  data: () => ({
    dialog: false,
  }),
  methods: {
    destroyMethod() {
      // this.fetchImages();
      console.log("destroyMethod");
      this.dialog = false;
      this.$emit("destroy");
    },
    fetchImages() {
      const data = {
        email: { text_body: "stas", description: "frontend2" },
      };

      var config = {
        method: "post",
        url: "http://localhost:4000/emails",
        // headers: {
        //   con: "application/json",
        //   "Content-Type": "application/json",
        // },
        data: data,
      };
      console.log("fetchimage!!!!!!");
      return axios(config).then(function(response) {
        console.log(JSON.stringify(response.data));
      });
    },
  },
  // eslint-disable-next-line space-before-function-paren
  created: function () {
    // console.log("start form");
    this.dialog = true;
  },
  // eslint-disable-next-line space-before-function-paren
  destroyed: function () {
    // console.log("destroyed");
    // this.dialog = true;
  },
};
</script>
