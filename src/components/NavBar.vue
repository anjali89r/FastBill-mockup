<template>
  <div>
    <v-navigation-drawer
      clipped
      class="sideDrawer hidden-md-and-up"
      v-model="sideNav"
      absolute
      temporary
    >
      <v-list>
        <v-list-item-group v-model="item" color="primary">
          <v-list-item>
            <v-list-item-action></v-list-item-action>
            <v-list-item-title>
              <router-link to="/">All</router-link>
            </v-list-item-title>
          </v-list-item>

          <v-list-item>
            <v-list-item-action></v-list-item-action>
            <v-list-item-title>
              <router-link to="/offers">Offers</router-link>
            </v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-action></v-list-item-action>
            <v-list-item-title>
              <router-link to="/incomes">Incomes</router-link>
            </v-list-item-title>
          </v-list-item>
          <v-list-item>
            <v-list-item-action></v-list-item-action>
            <v-list-item-title>
              <router-link to="/outcomes">Outcomes</router-link>
            </v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>

    <v-container class="pa-0">
      <v-row>
        <v-col cols="12">
          <v-app-bar color="elevation-0" class="app-color">
            <v-app-bar-nav-icon @click.native.stop="sideNav=!sideNav" class="hidden-md-and-up"></v-app-bar-nav-icon>
            <v-toolbar-title>
              <v-img
                alt="Company Logo"
                contain
                :src="require('../assets/main-logo.svg')"
                transition="scale-transition"
                :width="$vuetify.breakpoint.mdAndUp ? '140' : '100'"
              />
            </v-toolbar-title>

            <v-spacer></v-spacer>

            <v-btn
              text
              active-class="active-link"
              class="menu-item text-capitalize hidden-sm-and-down"
              color="grey darken-3"
              to="/"
            >
              <span class="custom-line font-weight-medium">All</span>
            </v-btn>

            <v-btn
              text
              active-class="active-link"
              class="menu-item text-capitalize hidden-sm-and-down"
              color="grey darken-3"
              to="/offers"
            >
              <span class="custom-line">Offers</span>
            </v-btn>

            <v-btn
              text
              active-class="active-link"
              class="menu-item text-capitalize hidden-sm-and-down"
              color="grey darken-3"
              to="/incomes"
            >
              <span class="custom-line">Incomes</span>
            </v-btn>
            <v-btn
              text
              active-class="active-link"
              class="menu-item text-capitalize hidden-sm-and-down"
              color="grey darken-3"
              to="/outcomes"
            >
              <span class="custom-line">Outcomes</span>
            </v-btn>
            <v-spacer></v-spacer>

            <v-text-field
              class="pt-5 hidden-sm-and-down"
              style="max-width:250px;"
              placeholder="search"
              prepend-inner-icon="search"
              filled
              rounded
              dense
              clearable
            ></v-text-field>
          </v-app-bar>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  data: () => ({
    sideNav: null,
    item: 1
  })
};
</script>
<style scoped>
.active-link span {
  color: #00838f;
}
.v-navigation-drawer {
  margin-top: 92px !important;
}
.v-application a {
  text-decoration: none;
}
.app-color {
  background-color: #fafafa !important;
}
span.custom-line {
  position: relative;
}

span.custom-line::before {
  content: "";
  position: absolute;
  margin-bottom: -3px;
  left: 50%;
  bottom: 0;
  width: 100%;
  height: 2px;
  background-color: #00838f;
  transform-origin: center;
  transform: translate(-50%, 0) scaleX(0);
  transition: transform 0.3s ease-in-out;
}

span.custom-line:hover::before {
  transform: translate(-50%, 0) scaleX(1);
}
</style>
