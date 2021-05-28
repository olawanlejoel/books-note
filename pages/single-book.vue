<template>
  <div>
    <header>
      <div @click="$router.back()">
        <Back />
      </div>
      <div class="head">
        <img src="~/assets/img/book1.jpg" class="book-img" alt="" />
      </div>
      <div class="book-info">
        <b class="title">The King of Drugs</b>
        <p class="author">Nora Barrett</p>
        <p class="desc">
          Lorem ipsum, dolor sit amet consectetur adipisicing elit. Fugit
          corporis quis repudiandae earum voluptatem culpa...
        </p>
      </div>
    </header>
    <section id="body">
      <p class="top-label">
        My Notes
      </p>
      <div class="info">
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum,
          quidem odio sit quas iusto hic voluptate harum iste facere ratione
          earum, aliquid labore. Neque architecto aut quia quos eius reiciendis?
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum,
          quidem odio sit quas iusto hic voluptate harum iste facere ratione
          earum, aliquid labore. Neque architecto aut quia quos eius reiciendis?
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum,
          quidem odio sit quas iusto hic voluptate harum iste facere ratione
          earum, aliquid labore. Neque architecto aut quia quos eius reiciendis?
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum,
          quidem odio sit quas iusto hic voluptate harum iste facere ratione
          earum, aliquid labore. Neque architecto aut quia quos eius reiciendis?
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum,
          quidem odio sit quas iusto hic voluptate harum iste facere ratione
          earum, aliquid labore. Neque architecto aut quia quos eius reiciendis?
        </p>
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum,
          quidem odio sit quas iusto hic voluptate harum iste facere ratione
          earum, aliquid labore. Neque architecto aut quia quos eius reiciendis?
        </p>
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
export default {};
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
