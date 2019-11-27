<template>
  <v-app id="sandbox">
    <v-navigation-drawer
      v-model="primaryDrawer.model"
      :clipped="primaryDrawer.clipped"
      :floating="primaryDrawer.floating"
      :mini-variant="primaryDrawer.mini"
      :permanent="primaryDrawer.type === 'permanent'"
      :temporary="primaryDrawer.type === 'temporary'"
      app
      overflow
    >
    <v-row class="kk">
      <v-col cols="12">
        <v-row
          v-ripple
          class="text-center elevation-2 text-center"

          style="min-height: 60px;color:white;text-align-center"
        >
        <a class="text-center">Home</a>

        </v-row>
      </v-col>

    </v-row>

    </v-navigation-drawer>

    <v-app-bar
      :clipped-left="primaryDrawer.clipped"
      absolute
      app
    >
      <v-app-bar-nav-icon
        v-if="primaryDrawer.type !== 'permanent'"
        @click.stop="primaryDrawer.model = !primaryDrawer.model"
      />
      <v-toolbar-title>Paradox</v-toolbar-title>
      <v-switch
        v-model="$vuetify.theme.dark"
          primary
          label="Dark"
          class="float-right"
      />
    </v-app-bar>


    <v-content>
      <v-container fluid>
        <v-row
          align="center"
          justify="center"
        >
          <v-col cols="12">
            <!-- <h5></!--> -->
          </v-col>
        </v-row>
      </v-container>
    </v-content>




    <v-footer
      :inset="footer.inset"
      app
    >
      <!-- <span class="px-4">&copy; {{ new Date().getFullYear() }}</span> -->
    </v-footer>
  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawers: ['Default (no property)', 'Permanent', 'Temporary'],
      primaryDrawer: {
        model: null,
        type: 'default (no property)',
        clipped: false,
        floating: false,
        mini: false,
      },
      footer: {
        inset: false,
      },
    }),
  }

  // :collapse="!collapseOnScroll"
  //     :collapse-on-scroll="collapseOnScroll"
</script>
<style>

.kk{
  background-color:primary;
}
</style>
