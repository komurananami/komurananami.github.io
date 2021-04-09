<template>
  <header id="nav">
    <div class="nav">
      <div class="nav-left">
        <a href="https://fontmeme.com/ja/font-signature/"
          ><img
            class="nav-left-img"
            src="https://fontmeme.com/permalink/210330/86265904da868351312d6fcc83be3480.png"
            alt="font-signature"
            border="0"
        /></a>
      </div>
      <div class="nav-right">
        <router-link to="/" class="nav-right-item">Home</router-link>
        <router-link to="/skills" class="nav-right-item">Skills</router-link>
        <router-link to="/works" class="nav-right-item">Works</router-link>
        <router-link to="/playground" class="nav-right-item"
          >Playground</router-link
        >
      </div>
    </div>
  </header>

  <router-view />
</template>

<script>
document.body.style.margin = "0";
console.log(document.body);
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  color: #2c3e50;
}

#nav {
  // padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #e5e5e5;
    }
  }
}

header {
  position: fixed;
  width: 100%;
  height: 100px;
  z-index: 8;
  top: 0px;
  left: 0px;
}

.container {
  position: relative;
  overflow: hidden;
  padding: 80px;
}

.nav {
  padding: 0 80px;
  height: 100%;
  z-index: 9;
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;

  &-left-img {
    width: 60px;
  }
  &-right {
    &-item {
      margin-left: 20px;
    }
  }
}
</style>
