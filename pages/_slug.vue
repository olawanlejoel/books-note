<template>
  <div v-if="book">
    <header>
      <div @click="$router.back()">
        <Back />
      </div>
      <div class="head">
        <img
          :src="$urlFor(book.bookcover)"
          :alt="book.bookname"
          loading="lazy"
          class="book-img"
        />
      </div>
      <div class="book-info">
        <b class="title">{{ book.bookname }}</b>
        <p class="author">{{ book.author }}</p>
        <p class="desc">
          {{ book.description }}
        </p>
      </div>
    </header>
    <section id="body">
      <p class="top-label">
        My Notes
      </p>
      <div class="info" v-if="book.mynotes">
        <SanityContent :blocks="book.mynotes" />
      </div>
      <div class="info" v-else>
        <p>No notes available!</p>
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
import { SanityContent } from "@nuxtjs/sanity/dist/components/sanity-content";

export default {
  components: { SanityContent },
  async asyncData({ params, $sanity }) {
    const query = groq`*[_type == "books" && slug.current == "${params.slug}"][0]`;
    const book = await $sanity.fetch(query);
    return { book };
  }
};
</script>

<style scoped>
header {
  background: #200122; /* fallback for old browsers */
  background: linear-gradient(to right, #200122, #6f0000);
  height: 40vh;
  position: fixed;
}

#body {
  padding: 40vh 15px 18px;
  text-align: center;
}

.head {
  position: absolute;
  top: 20%;
  left: 50%;
  transform: translate(-50%, -20%);
}

img {
  max-width: 100%;
}

.book-img {
  width: 110px;
  height: auto;
  filter: drop-shadow(5px 5px 10px #2e2e2e);
}

.book-info {
  padding-top: 20vh;
  text-align: center;
}

.book-info b {
  color: rgb(255, 255, 255);
}

.book-info .author {
  color: rgb(190, 190, 190);
  font-size: 14px;
}

.book-info .desc {
  color: rgb(153, 153, 153);
  padding-top: 5px;
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

.top-label {
  color: rgb(34, 34, 34);
  font-weight: bold;
  padding-top: 20px;
}

.info {
  color: rgb(104, 104, 104);
  font-size: 14px;
  padding-top: 5px;
}
</style>
