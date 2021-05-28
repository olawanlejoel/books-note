<template>
  <div>
    <header>
      <div class="head">
        <Logo />
        <b>Books Note</b>
      </div>
    </header>
    <section id="body">
      <p class="top-label">
        You currently have <strong>{{ books.length }}</strong> Books!
      </p>
      <div class="books">
        <div v-for="book in books" :key="book.id">
          <NuxtLink class="link" :to="book.slug.current">
            <div class="book">
              <img
                :src="$urlFor(book.bookcover)"
                :alt="book.bookname"
                loading="lazy"
                class="book-img"
              />
              <!-- <img :src="book.image" alt="" class="book-img" /> -->
              <div class="book-info">
                <b class="title"> {{ book.bookname }}</b>
                <p class="author">{{ book.author }}</p>
                <p class="desc">
                  {{ book.description }}
                </p>
              </div>
            </div>
          </NuxtLink>
        </div>
      </div>
    </section>
    <footer>
      <NuxtLink to="/about">
        <div class="abt-icon">
          <About />
        </div>
      </NuxtLink>
    </footer>
  </div>
</template>

<script>
import { groq } from "@nuxtjs/sanity";

export default {
  async asyncData({ $sanity }) {
    const query = groq`*[_type == "books"]`;
    const books = await $sanity.fetch(query);
    return { books };
  }
};
</script>

<style scoped>
header {
  position: fixed;
  height: 10vh;
  width: 100%;
  background: #200122; /* fallback for old browsers */
  background: linear-gradient(to right, #200122, #6f0000);
  border-bottom-left-radius: 30px;
  border-bottom-right-radius: 30px;
  color: #fff;
}

.link {
  text-decoration: none;
}

.head {
  display: inline-flex;
  flex-wrap: wrap;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.head b {
  margin-left: 10px;
  font-size: 20px;
}

#body {
  padding: 12vh 15px 0;
}

.top-label {
  color: rgb(34, 34, 34);
  font-size: 14px;
}

img {
  max-width: 100%;
}

.books .link .book {
  width: 100%;
  border-bottom: 1px solid #20012273;
  display: inline-flex;
  padding: 12px 0;
  margin: 12px 0;
}

.books .link .book:last-child {
  border-bottom: none;
}

.book-img {
  width: 60px;
  height: auto;
  margin-right: 15px;
}

.book-info .author {
  color: rgb(34, 34, 34);
  font-size: 14px;
}

.book-info .desc {
  color: rgb(104, 104, 104);
  margin-top: 5px;
  font-size: 12px;
}

footer {
  position: fixed;
  bottom: 0;
  right: 0;
  background: #200122; /* fallback for old browsers */
  background: linear-gradient(to right, #200122, #6f0000);
  height: 70px;
  width: 70px;
  border-top-left-radius: 100%;
}

.abt-icon {
  position: absolute;
  top: 60%;
  left: 60%;
  transform: translate(-50%, -50%);
}
</style>
