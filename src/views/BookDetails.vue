<template>
  <div>
    <Hero
      title="Here are more details about our books"
      subtitle="You can Visit The Book Site to find out more"
      color="is-info"
    />
    <div class="card">
      <header class="card-header">
        <p class="card-header-title">Authored by {{author[0]}}</p>
      </header>
      <div class="card-content">
        <div class="content">
          <h4>This Book "{{bookName}}" is published by {{publisher}}</h4>
          <h4>Pages: {{pages}}</h4>
          <br />
          <h4>Country of origin: {{country}}</h4>
          <br />
          <h4>Book ISBN: {{isbn}}</h4>
          <br />
        </div>
      </div>
      <footer class="card-footer">
        <a :href="this.url" class="card-footer-item">Visit Book Site</a>
      </footer>
    </div>
  </div>
</template>

<script>
import Hero from "@/components/Hero";
export default {
  props: [
    "bookId",
    "country",
    "publisher",
    "isbn",
    "releaseDate",
    "url",
    "pages",
    "author",
    "bookName"
  ],
  components: { Hero }
};
</script>
<style lang="scss" scoped>
.card {
  max-width: 400px;
  margin: 0 auto;
}
</style>
