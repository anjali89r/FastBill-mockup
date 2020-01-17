<template>
  <v-card>
    <v-card :color="category.color">
      <v-card-title>
        <span class="title font-weight-medium white--text">{{category.name}}</span>
        <v-spacer></v-spacer>
        <v-tooltip bottom>
          <template v-slot:activator="{ on }">
            <v-btn fab color="warning" v-on="on">
              <v-icon>add</v-icon>
            </v-btn>
          </template>
          <span>Add {{category.action}}</span>
        </v-tooltip>
      </v-card-title>
    </v-card>
    <v-card>
      <v-card-title>
        <v-text-field
          v-model="search"
          style="max-width:250px;"
          append-icon="search"
          label="Search"
          single-line
          hide-details
          clearable
        ></v-text-field>
        <v-spacer></v-spacer>
      </v-card-title>
      <v-data-table
        :headers="headers"
        :items="offers"
        :items-per-page="5"
        item-key="name"
        class="elevation-2"
        :search="search"
      ></v-data-table>
    </v-card>
  </v-card>
</template>
<script>
export default {
  props: ["headers", "offers", "category"],
  data: () => ({
    search: ""
  })
};
</script>
