<template>
  <div class="books">
    <Hero
      title="The Game of Thrones Books"
      subtitle="...from an API of Ice and Fire"
      color="is-warning"
    />
    <div class="section">
      <div class="container">
        <div class="columns is-multiline">
          <div class="column is-2" v-for="book in books" :key="book.isbn">
            <div id="cards" class="card">
              <div class="card-content">
                <h2>{{ book.name }}</h2>
                <router-link
                  :to="{ name: 'details', params: { bookName: book.name, bookId: book.isbn, country: book.country, isbn: book.isbn, releaseDate:book.released, publisher:book.publisher, pages:book.numberOfPages, author:book.authors }}"
                >View Details</router-link>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Hero from "@/components/Hero";
export default {
  components: {
    Hero
  },
  data() {
    return {
      books: null
    };
  },
  mounted() {
    fetch("https://anapioficeandfire.com/api/books")
      .then(resp => resp.json())
      .then(data => {
        this.books = data;
      });
  }
};
</script>
<style lang="scss" scoped>
.card {
  max-height: 120px;
  min-height: 120px;
  margin: 0 auto;
}
</style> 