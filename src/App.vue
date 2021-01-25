<template>
  <v-app id="inspire">


    <v-app-bar
      app
      absolute
      color="#6A76AB"
      dark
      dense
      shrink-on-scroll
      src="https://cdn.thecrazytourist.com/wp-content/uploads/2018/07/ccimage-shutterstock_694353502.jpg"
      scroll-target="#scrolling-techniques-4"
    >
        <!-- <template v-slot:img="{ props }">
          <v-img
            v-bind="props"
            gradient="to top right, rgba(100,115,201,.7), rgba(25,32,72,.7)"
          ></v-img>
        </template>

      <v-app-bar-nav-icon></v-app-bar-nav-icon> -->
  <v-spacer></v-spacer>
      <v-toolbar-title>This is a title for my page</v-toolbar-title>

  <v-spacer></v-spacer>

      <template v-slot:extension>

        <v-tabs centered>
          <v-tab   v-for="item in items"
            :key="item.title"
            :to="item.link"
            text>{{item.title}}</v-tab>
        </v-tabs>
      </template>
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
                color="grey lighten-4"
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


    <v-footer dark padless>
   <v-col
     class="text-center"
     cols="12"
   >
   <v-card-text>
     <v-btn
       v-for="icon in icons"
       :key="icon"
       class="mx-4 purple--text"
       icon
     >
       <v-icon size="24px">
         {{ icon }}
       </v-icon>
     </v-btn>
   </v-card-text>

     {{ new Date().getFullYear() }} — <strong>big dick daddy</strong>
   </v-col>
 </v-footer>
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
     ],
     icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-linkedin',
        'mdi-instagram',
      ],


  }),
};
</script>
