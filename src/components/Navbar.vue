<template>
  <nav>
    <!-- <v-btn color="black" class="white--text" >dark theme</v-btn> -->
    <!-- slider nav -->
    <v-navigation-drawer v-model="drawer" bottom app temporary>
      <template v-slot:prepend>
        <v-layout column align-center>
          <v-flex class="mt-4"
            ><v-responsive>
              <v-avatar size="120" color="primary">
                <span class="white--text display-3 font-weight-bold">A B</span>
              </v-avatar>
              <p :class="`font-weight-bold ml-5 pt-2`">
                Abdul Basit
              </p>
            </v-responsive>
          </v-flex>
        </v-layout>
        <v-list-item two-line router to="/">
          <v-list-item-avatar>
            <v-icon large color="primary">fas fa-tachometer-alt</v-icon>
          </v-list-item-avatar>

          <v-list-item-content>
            <v-list-item-title class="font-weight-bold title">
              Dash Board
            </v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </template>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          router
          :to="item.router"
        >
          <v-list-item-icon>
            <v-icon right color="primary lighten-1">{{ item.icon }}</v-icon>
          </v-list-item-icon>

          <v-list-item-content>
            <v-list-item-title class="font-weight-bold">{{
              item.title
            }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <!-- slider nav End-->
    <v-toolbar>
      <v-app-bar-nav-icon
        large
        @click="drawer = !drawer"
        class="ml-n0"
      ></v-app-bar-nav-icon>
      <v-toolbar-title class="text-uppercase">
        <span class="display-1 ml-n5 font-weight-bold">M</span>
        <span class="font-weight-bold">anager - App</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>

      <!-- theme BTN -->
      <div class="mr-5">
        <label id="switch" class="switch">
          <input type="checkbox" @click="drk" id="slider" />
          <span class="slider round"></span>
        </label>
      </div>
      <!-- theme BTN -->
      <v-btn small class="red lighten-2 black--text" text>
        <span>Sign Out</span>
        <v-icon right style="font-size:28px"
          >mdi-arrow-right-bold-box-outline</v-icon
        >
      </v-btn>
    </v-toolbar>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      drawer: false,
      items: [
        { title: 'My Projects', icon: 'fa fa-folder', router: '/projects' },
        { title: 'Team', icon: 'fas fa-users', router: '/team' }
      ]
    }
  },
  methods: {
    drk() {
      this.$vuetify.theme.dark =
        this.$vuetify.theme.dark == false ? true : false
    },
    navRoute: route => route
  },
  created() {
    this.$vuetify.theme.dark = true
  }
}
</script>
<style scoped>
/* The switch - the box around the slider */
.switch {
  position: relative;
  display: inline-block;
  width: 70px;
  height: 34px;
}

/* Hide default HTML checkbox */
.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

/* The slider */
.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

.slider:before {
  position: absolute;
  content: '';
  height: 50px;
  width: 50px;
  left: 0px;
  bottom: 4px;
  top: 0;
  bottom: 0;
  margin: auto 0;
  -webkit-transition: 0.4s;
  transition: 0.4s;
  box-shadow: 0 0px 15px #2020203d;
  background: white url('https://i.ibb.co/FxzBYR9/night.png');
  background-repeat: no-repeat;
  background-position: center;
}

input:checked + .slider {
  background-color: #2196f3;
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196f3;
}

input:checked + .slider:before {
  -webkit-transform: translateX(24px);
  -ms-transform: translateX(24px);
  transform: translateX(24px);
  background: white url('https://i.ibb.co/7JfqXxB/sunny.png');
  background-repeat: no-repeat;
  background-position: center;
}

/* Rounded sliders */
.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}
</style>
