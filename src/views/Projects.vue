<template>
  <div>
    <h1 class="grey--text text--darken-2 ml-5 my-5">My Projects</h1>
    <v-container class="my-5">
      <v-expansion-panels popout>
        <v-expansion-panel
          class="elevation"
          v-for="(item, i) in projects"
          :key="i"
        >
          <v-expansion-panel-header
            ><span class="font-weight-bold" style="font-size:18px">
              {{ item.title }}</span
            >
            <v-spacer></v-spacer
            ><v-flex xs2 sm2 md1 lg2>
              <div>
                <v-chip
                  small
                  :class="`${item.status} white--text font-weight-bold my-2`"
                >
                  <span style="color:black"> {{ item.status }}</span></v-chip
                >
              </div>
            </v-flex>
          </v-expansion-panel-header>
          <v-expansion-panel-content>
            <v-divider class="mb-4"></v-divider>
            {{ item.content }}
          </v-expansion-panel-content>
        </v-expansion-panel>
      </v-expansion-panels>
    </v-container>
  </div>
</template>
<script>
export default {
  name: 'Project',
  data() {
    return {
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
  }
}
</script>

<style scoped>
.v-chip.complete {
  background: greenyellow !important;
}
.v-chip.ongoing {
  background: orange !important;
}
.v-chip.overdue {
  background: tomato !important;
}
.elevation {
  box-shadow: 0 2px 5px;
}
</style>
