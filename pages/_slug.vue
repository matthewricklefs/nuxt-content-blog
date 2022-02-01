<template>
  <v-container fluid>
    <section class="my-3">
      <v-btn text to="/">
        <v-icon small class="mr-2">mdi-arrow-left</v-icon>
        Go Back
      </v-btn>
    </section>

    <section class="post-content">
      <h2 class="text-h2 mb-10">{{ post.title }}</h2>
      <nuxt-content :document="post" />
    </section>

    <v-row class="d-flex justify-space-between align-center mt-5" cols="12">
      <v-col>
        <v-btn :disabled="!prev" :to="prev && prev.path" small class="mr-2"
          >Previous Post
        </v-btn>
        <v-btn :disabled="!next" :to="next && next.path" small class="mr-2"
          >Next Post</v-btn
        >
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'PostPage',
  layout: 'DefaultLayout',
  async asyncData({ $content, error, params }) {
    // TODO Paginate posts
    const [prev, next] = await $content()
      .only(['path'])
      .sortBy('createdAt', 'desc')
      .surround(params.slug)
      .fetch()

    const post = await $content(params.slug)
      .fetch()
      .catch(() =>
        error({
          statusCode: 404,
          message: 'Oops, looks like that post does not exist!',
        })
      )

    return {
      post,
      prev,
      next,
    }
  },

  head() {
    return {
      title: this.post.title,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: this.post.description,
        },
        // open graph
        {
          hid: 'og:title',
          property: 'og:title',
          content: this.post.title,
        },
        // twitter card
        {
          hid: 'twitter:title',
          name: 'twitter:title',
          content: this.post.title,
        },
        {
          hid: 'twitter:description',
          name: 'twitter:description',
          content: this.post.description,
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
</style>