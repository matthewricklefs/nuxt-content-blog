<template>
  <v-container fluid>
    <section class="my-3">
      <v-btn text to="/">
        <v-icon small class="mr-2">mdi-arrow-left</v-icon>
        Go Back
      </v-btn>
    </section>

    <section class="post-content">
      <h1>My First Post</h1>

      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Architecto
        illum vel, odio nobis repellendus praesentium eaque amet rerum.
        Recusandae, eos! Saepe molestias dolores natus error quisquam est
        dolorum accusantium deleniti. Hic repellendus, libero nostrum ut
        pariatur accusantium ad odio eligendi labore dignissimos necessitatibus
        quia reprehenderit odit alias doloremque ipsum.
        <br />
        Omnis officia enim quas eaque repellendus pariatur molestiae explicabo
        obcaecati sed! Eligendi, quod quo molestias alias libero, quibusdam ad
        iure illum veniam officia harum voluptates! Culpa suscipit tempora esse?
        <br />
        <br />
        Similique nemo aspernatur deleniti consequuntur nulla dolor, natus
        molestias veniam quis culpa.
      </p>
    </section>

    <v-row class="d-flex justify-space-between align-center mt-5" cols="12">
      <v-col>
        <v-btn small class="mr-2">Previous Post </v-btn>
        <v-btn small class="mr-2">Next Post</v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'PostPage',
  layout: 'DefaultLayout',
}
</script>

<style lang="scss" scoped>
</style>