<template>
  <div>
    <h1 class="grey--text text--darken-2 ml-5 my-3">Dashboard</h1>
    <v-container class="my-5">
      <v-layout>
        <v-flex xs4 md3>
          <v-overflow-btn
            @change="sortBy"
            class="my-2  ptr"
            :items="sortOpt"
            label="Sort By"
          >
          </v-overflow-btn></v-flex
      ></v-layout>

      <v-card
        class="my-1 mb-4"
        v-for="project in projects"
        :key="project.title"
      >
        <v-layout row wrap :class="`pa-4 project ${project.status}`">
          <v-flex xs5 sm4 md6 lg4 class="pl-2">
            <div class="caption grey--text text--darken-2 font-weight-bold">
              Project Title
            </div>

            <div class="font-weight-bold">{{ project.title }}</div>
          </v-flex>
          <v-flex xs3 sm3 md2 lg3>
            <div class="caption grey--text text--darken-2 font-weight-bold">
              Person
            </div>
            <div class="font-weight-bold">{{ project.person }}</div>
          </v-flex>
          <v-flex xs3 sm3 md3 lg3>
            <div class="caption grey--text text--darken-2 font-weight-bold">
              Due By
            </div>
            <div class="font-weight-bold">{{ project.due }}</div>
          </v-flex>
          <v-flex xs2 sm2 md1 lg2>
            <div class="right">
              <v-chip
                small
                :class="`${project.status} font-weight-bold my-2`"
                style="color:black"
              >
                {{ project.status }}</v-chip
              >
            </div>
          </v-flex>
        </v-layout>
      </v-card>
    </v-container>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'Dashboard',
  data() {
    return {
      sortOpt: ['Name', 'Title'],
      projects: [
        {
          title: 'Design a new website',
          person: 'The Net Ninja',
          due: '1st Jan 2019',
          status: 'ongoing',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'
        },
        {
          title: 'Code up the homepage',
          person: 'Chun Li',
          due: '10th Jan 2019',
          status: 'complete',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'
        },
        {
          title: 'Design video thumbnails',
          person: 'Ryu',
          due: '20th Dec 2018',
          status: 'complete',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'
        },
        {
          title: 'Create a community forum',
          person: 'Gouken',
          due: '20th Oct 2018',
          status: 'overdue',
          content:
            'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt consequuntur eos eligendi illum minima adipisci deleniti, dicta mollitia enim explicabo fugiat quidem ducimus praesentium voluptates porro molestias non sequi animi!'
        }
      ]
    }
  },
  components: {},
  methods: {
    sortBy(e) {
      let sortBy = 'person'
      if (e == 'Name') {
        // console.log(this.projects[0][sortBy])
        this.projects = this.projects.sort((a, b) =>
          a[sortBy] < b[sortBy] ? -1 : 1
        )
      } else {
        sortBy = 'title'
        this.projects = this.projects.sort((a, b) =>
          a[sortBy] < b[sortBy] ? -1 : 1
        )
      }
    }
  }
}
</script>

<style scoped>
.project.complete {
  border-left: 7px solid greenyellow;
}
.project.ongoing {
  border-left: 7px solid orange;
}
.project.overdue {
  border-left: 7px solid tomato;
}
.v-chip.complete {
  background: greenyellow !important;
}
.v-chip.ongoing {
  background: orange !important;
}
.v-chip.overdue {
  background: tomato !important;
}
.ptr {
  cursor: pointer !important;
}
</style>
