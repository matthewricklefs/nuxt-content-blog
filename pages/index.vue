<template>
  <v-container fluid>
    <div class="intro mt-5 mb-8">
      <h1 class="text-h1">Matthew's Coding Blog</h1>

      <h2 class="mt-2">
        Elevating our Nuxt.js capabilities
        <span class="emoji">🚀</span>
      </h2>
    </div>

    <v-row class="posts-container">
      <v-col cols="12">
        <div class="filter">
          <v-select
            v-model="category"
            style="width: 100px"
            outlined
            dense
            hide-details="auto"
            :items="['all', 'coding', 'youtbe']"
          />
        </div>
      </v-col>

      <v-col v-for="post in 4" :key="post" cols="12" md="6">
        <v-card elevation="0">
          <v-card-title> My First Blog </v-card-title>

          <v-card-text
            >Lorem ipsum dolor sit amet consectetur, adipisicing elit. Sequi
            error corporis dolore, ullam autem possimus dolorum dolor nihil
            nulla! Eaque nemo saepe doloribus mollitia quos ex! Officiis
            voluptates voluptatibus et?</v-card-text
          >

          <v-card-actions>
            <v-btn text to="/1">Read More</v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>

    <v-row class="post-pagination">
      <v-col class="text-right" cols="12">
        <v-btn>
          <v-icon small> mdi-arrow-left</v-icon>
        </v-btn>

        <v-btn>
          <v-icon small> mdi-arrow-right</v-icon>
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'HomePage',
  layout: 'DefaultLayout',
  data: () => ({
    category: 'all',
  }),
}
</script>
