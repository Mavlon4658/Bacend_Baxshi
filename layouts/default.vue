<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
      <!--  -->
      <v-list-item>
        <v-list-item-icon>
          <v-icon>mdi-home</v-icon>
        </v-list-item-icon>

        <v-list-item-title>Dashboard</v-list-item-title>
      </v-list-item>
      <v-row justify="center">
        <v-expansion-panels accordion>
          <v-expansion-panel v-for="(item, i) in menues" :key="i">
            <v-expansion-panel-header>{{item.name}}</v-expansion-panel-header>
            <v-expansion-panel-content
              style="padding: 0 !important; position: relative !important"
            >
              <v-list-item
                style="position: relative; left: -6%; !important; width: 111% !important;"
                v-for="(title, i) in item.admins"
                :key="i"
                link
                :to="title.to"
              >
                <v-list-item-title class="ms-10" v-text="title.title"></v-list-item-title>
              </v-list-item>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-row>
    </v-navigation-drawer>

    <v-app-bar app>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

      <v-toolbar-title>baxshiinternat.uz</v-toolbar-title>
    </v-app-bar>

    <v-main class="">
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      drawer: false,
      menues: [
        { 
          name: 'Biz haqimizda',
          admins: [
                    {title: "Ko'rish", to: "/"}, 
                    {title: 'Qo\'shish', to: "/AboutAdd"},
                  ],
        },
        { 
          name: 'Yangiliklar',
          admins: [
                    {title: 'Management', to: "/"}, 
                    {title: 'Settings', to: "/"}
                  ],
        },
      ],
      
    }
  },
}
</script>
