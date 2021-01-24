<template>
  <v-app id="inspire">
    <v-app-bar
      app
      color="white"
      flat
    >
      <v-container class="py-0 fill-height">
        <v-avatar
          class="mr-10"
          color="purple"
          size="50"
        >Logo</v-avatar>

        <v-btn
          v-for="item in items"
          :key="item.title"
          :to="item.link"
          text
        >
          {{ item.title }}
        </v-btn>

        <v-spacer></v-spacer>

        <v-responsive max-width="260">
          <v-text-field
            dense
            flat
            hide-details
            rounded
            solo-inverted
          ></v-text-field>
        </v-responsive>
      </v-container>
    </v-app-bar>

    <v-main class="grey lighten-3">
      <v-container>
        <v-row>
          <v-col cols="2">
            <v-sheet rounded="lg">
              <v-list color="transparent">
                <v-list-item
                  v-for="link in sublinks"
                  :key="link.title"
                  :to="link.link"
                  link
                >
                  <v-list-item-content>
                    <v-list-item-title>
                      {{link.title}}
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>

                <v-divider class="my-2"></v-divider>

                <v-list-item
                  link
                  color="black"
                >
                  <v-list-item-content>
                    <v-list-item-title>
                      Refresh
                    </v-list-item-title>
                  </v-list-item-content>
                </v-list-item>
              </v-list>
            </v-sheet>
          </v-col>

          <v-col>
            <v-sheet
              min-height="70vh"
              rounded="lg"
            >
              <router-view></router-view>
            </v-sheet>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>


<script>
import HelloWorld from './components/HelloWorld';
// import pdf from 'vue-pdf';

export default {
  name: 'App',

  components: {
    HelloWorld,

  },

  data: () => ({
    links: [
        'Dashboard',
        'Messages',
        'Profile',
        'Updates',
      ],

      items: [
       { title: 'Dashboard',link:'/'},
       { title: 'Test', link:'/test'},
       { title: 'Profile', link:'/about'},
       { title: 'Progress', link:'/progress'},
       { title: 'About', link:'/about'},

     ],
     sublinks:[
       { title: 'Intro', icon: 'mdi-format-list-checks' , link:'/pythonLessons/intro'},
       { title: 'Lesson 1', icon: 'mdi-help-box', link:'/pythonLessons/lesson1'},
     ]


  }),
};
</script>
