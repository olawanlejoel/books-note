<template>
  <div>
    <header>
      <div @click="$router.back()">
        <Back />
      </div>
      <div class="head">
        <Logo />
        <b>Books Note</b>
      </div>
    </header>
    <section id="body">
      <p class="top-label">
        About App
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
      </div>
    </section>
    <footer>
      <div class="abt-icon">
        <About />
      </div>
    </footer>
  </div>
</template>

<script>
export default {};
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
  text-align: center;
}

.top-label {
  color: rgb(34, 34, 34);
  font-weight: bold;
  margin-top: 20px;
}

.info {
  color: rgb(104, 104, 104);
  font-size: 14px;
  margin-top: 5px;
}
</style>
