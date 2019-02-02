<template>
  <div id="app">
      <section id="intro">
        <header class="flex">
          <div style="flex:1;">
            <span>Amanze.me</span>

          </div>
          <div style="display:flex;">
            <span class="social-icon" v-for="(social, pos) in socials" :key="pos" @click="goto(social.url)">
              <img :src="social.src" :alt="social.alt">
            </span>
            <!-- <span class="social-icon">
              <img src="/static/img/linkedin.svg" alt="linkedin">
            </span>
            <span class="social-icon">
              <img src="/static/img/twitter.svg" alt="twitter">
            </span> -->

          </div>
        </header>
        <main ref="intro-main">
          <div class="container pad" style="position: relative;">
            <div id="main-image"></div>
            <div id="caption-holder">
              <div class="caption">Hi, my name is</div>
              <div class="main-text">Amanze Ogbonna</div>
            </div>

          </div>
        </main>
      </section>
      <section id="hand-drawer">
        <div class="flex container">
          <div style="flex:1;"></div>
          <div style="" class="flex">
            <div class="right">
              <img src="/static/img/right_shad_80h.png" class="hand" alt="right hand">
            </div>
            <div>
              <img src="/static/img/left_shad_80h.png" class="hand" alt="right hand">

            </div>
          </div>
        </div>
      </section>
      <section id="about">
        <div class="container">
          <div class="title">About</div>
          <br>
          <div>Born in Lagos Nigeria on July 5th, 1990, into the house of Edward Ogbonna Akor and Paulina Ulumma Akor. Amanze has always been a curious person who wants to know how things work. He ventured into science to find his answers. After been selected from thousands of candidates to join the Meltwater Entrepreneurial School of Technology community in 2015, where he met his cofounder. He and his Co-founder were able to raise $50,000 to solve a problem in the Agric sector. Amanze is also a Computer scientist, Software Engineer, Product Manager, Entrepreneur and is familiar with the West African entrepreneurial landscape. Experienced in managing a strong software development team and bringing the best out of everyone. After his ordeal of growing up with the bad power supply in Nigeria, his future interest is in finding and using alternative power sources to support the electric grid and help make good, reliable and affordable electricity to be accessible to the common man.</div>
        </div>
      </section>
  </div>
</template>

<script>
require('./assets/css/bootstrap-grid.css')
export default {
  name: 'app',
  data: () => ({
    socials: [
      {
        src: "/static/img/github.svg",
        alt:"github",
        url: "//github.com/darlingtonamz"
      },
      {
        src:"/static/img/linkedin.svg",
        alt:"linkedin",
        url: "//linkedin.com/in/amanze"
      },
      {
        src:"/static/img/twitter.svg",
        alt:"twitter",
        url: "//twitter.com/am_zee"
      }
    ]
  }),
  methods: {
    goto(url){
      window.open(url, '_blank');
    }
  },
  mounted() {
    setTimeout(() => {
      this.$refs['intro-main'].classList.add("active");
    }, 1000);
  },
}
</script>

<style lang="scss">
@import url('/assets/css/bootstrap-grid.css');

html, body, #app {height: 100vh;}

.flex {display: flex; }
body {
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // color: #2c3e50;
}
.pad {padding: 16px;}

main {
  /* text-align: center; */
  margin-top: 40px;
  max-height: 400px;
  transition: .3s height ease-in-out;
  height: 0px;
  overflow: hidden;
  // position: relative;

  &.active {
    height: 420px;
  }

  #main-image {
    position: absolute;
    background: url('/static/img/me.png') no-repeat bottom;
    // content: " ";
    height: 400px;
    width: 400px;
    top: 20px;
    right: 0;
  }

  #caption-holder {
    position: relative;
    z-index: 1;
    margin-top: 140px;
  }

  .caption {
    color: #B6B2BC;
    font-size: 1em;
  }
  .main-text {
    color: #171449;
    font-size: 3em;
  }
}
#intro {
  // background: white;
  background: url('/static/img/bg.svg') no-repeat fixed right;

  .social-icon {
      height: 20px;
    width: 20px;
    background: white;
    margin: 5px;
    cursor: pointer;
  }

}

#hand-drawer {
  background: #FAFBFE;
  position: relative;
  z-index: 2;
  box-shadow: 2px 2px 20px -5px;

  .right { margin-right: 180px;}
  .hand {
    height: 80px;
    margin-top: -25px
  }
}
.title {
  font-size: 2em;
}
#about {
  position: relative;
  z-index: 2;
  background: #FAFBFE;
}

header {
  margin: 0;
  height: 56px;
  padding: 0 16px 0 24px;
  /* background-color: #35495E; */
  color: #35495E;
  /* color: #ffffff; */
}

header span {
  display: block;
  position: relative;
  font-size: 20px;
  line-height: 1;
  letter-spacing: .02em;
  font-weight: 400;
  box-sizing: border-box;
  padding-top: 16px;
}
</style>
