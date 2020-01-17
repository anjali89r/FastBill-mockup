<template>
  <v-card max-width="400">
    <v-card :color="getColor">
      <v-card-title>
        <span class="title font-weight-medium white--text">{{type.title}}</span>
        <v-spacer></v-spacer>

        <v-menu bottom left v-if="$vuetify.breakpoint.lgAndDown">
          <template v-slot:activator="{ on }">
            <v-btn dark icon v-on="on">
              <v-icon>mdi-dots-vertical</v-icon>
            </v-btn>
          </template>

          <v-list rounded>
            <v-list-item v-for="(item, i) in type.items" :key="i" @click="callAction(type.title)">
              <v-list-item-title>{{ item }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-card-title>
    </v-card>

    <v-card-text>
      <v-row v-for="(offer, index) in type.list" :key="index">
        <v-col cols="12">
          <v-list-item>
            <v-list-item-content>
              <v-list-item-title class="grey--text text--darken-1 font-weight-medium">{{offer}}</v-list-item-title>
            </v-list-item-content>
          </v-list-item>
          <v-divider v-if="index != type.list.length-1 "></v-divider>
        </v-col>
      </v-row>
    </v-card-text>
    <v-divider v-if="$vuetify.breakpoint.xl"></v-divider>
    <v-card-actions class="pa-4" v-if="$vuetify.breakpoint.xl">
      <v-btn
        rounded
        color="pink darken-1"
        to
        class="white--text text-capitalize"
        v-for="(item, i) in type.items"
        :key="i"
        @click="callAction(type.title)"
      >{{item}}</v-btn>
    </v-card-actions>
  </v-card>
</template>
<script>
export default {
  name: "Card",
  props: ["type"],
  computed: {
    getColor() {
      switch (this.type.title) {
        case "Offers":
          return "red accent-2";

        case "Incomes":
          return "teal";

        default:
          return "deep-orange lighten-1";
      }
    }
  },
  methods: {
    callAction(title) {
      this.$router.push(`/${title.toLowerCase()}`);
    }
  }
};
</script>
