<template>
  <div>
    <h1 class="grey--text text--darken-2 ml-5 my-3">Team</h1>
    <v-container class="my-5">
      <v-layout row wrap class="ma-1 center">
        <v-flex
          xs12
          sm6
          md4
          lg3
          v-for="person in team"
          class="pa-3"
          :key="person.name"
        >
          <v-card elevation="6" color="text-center my-2 py-5">
            <v-avatar size="120" color="primary">
              <span class="white--text display-3">{{
                nameCaps(person.name)
              }}</span>
            </v-avatar>

            <v-card-text
              ><div class="font-weight-bold" style="font-size:20px">
                {{ person.name }}
              </div>
              <div>{{ person.role }}</div></v-card-text
            >
            <v-card-actions>
              <v-btn block color="primary">
                <v-icon left>far fa-comment-alt</v-icon
                ><span class="font-weight-bold">Message</span>
              </v-btn>
            </v-card-actions>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'Team',
  data() {
    return {
      team: [
        { name: 'Abdul Basit', role: 'Web developer' },
        { name: 'Mudassir rehman', role: 'Graphic designer' },
        { name: 'Osama Irfan', role: 'Web developer' },
        { name: 'Umer', role: 'Social media maverick' },
        { name: 'Abu Bakar', role: 'Sales guru' }
      ]
    }
  },
  methods: {
    nameCaps(name) {
      return name
        .split(' ')
        .map(val => val[0])
        .slice(0, 2)
        .join(' ')
        .toUpperCase()
    }
  }
}
</script>

<style scoped>
.center {
  justify-content: center;
}
</style>
