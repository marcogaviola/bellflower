<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      Data List
    </v-app-bar>

    <v-main>
      <v-card>
        <v-card-title>
          Bellflower Street Data
          <v-spacer></v-spacer>
          <v-text-field
            v-model="search"
            append-icon="mdi-magnify"
            label="Search"
            single-line
            outlined
            hide-details
          ></v-text-field>
        </v-card-title>
        <v-data-table
          :headers="headers"
          :items="data"
          :search="search"
        ></v-data-table>
      </v-card>
    </v-main>
  </v-app>
</template>

<script>
import bellflower from "./assets/bellflower.json"
export default {
  name: 'App',

  data: () => ({
    search: '',
    headers: [
      {
        text: 'Address',
        align: 'start',
        value: 'Address',
      },
      { text: 'Last Name', value: 'lastname' },
      { text: 'First Name', value: 'firstname' },
      { text: 'Middle Name', value: 'middlename' },
      { text: 'Gender', value: 'gender' }
    ],
    data: bellflower
  }),
};
</script>
