<template>
  <div class="section">
    <ul class="article-list">
      <h1>{{$static.header.edges[0].node.name}}</h1>
      <img :src="`${$static.header.edges[0].node.image.file.url.src}`" />
      <h2>{{$static.header.edges[0].node.specialism}}</h2>
      <div>{{$static.header.edges[0].node.location}}</div>
    </ul>
  </div>
</template>

<style scoped>
h1 {

}
</style>

<static-query>
  query HomeQuery {
    posts: allContentfulBlogPost {
      edges {
        node {
          title
          description
          slug
          publishDate(format: "MMMM Do, YYYY")
          tags
          heroImage {
            path
            slug
            file {
              fileName
              url
            }
          }
          description
        }
      }
    }
    header: allContentfulPageHeader {
      edges {
        node {
          image {
            path
            slug
            file {
              fileName
              url
            }
          }
          name
          specialism
          location
        }
      }
    }
  }
</static-query>
<script>

export default {
  components: {
  },
};
</script>
