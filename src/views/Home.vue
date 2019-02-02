<template>
  <div class="home">
    <div>
      <section id="intro">
        <header class="flex">
          <div style="flex:1;">
            <!-- <span>Amanze.me</span> -->
          </div>
          <div style="display:flex;">
            <!-- <span class="social-icon" v-for="(social, pos) in socials" :key="pos" @click="goto(social.url)">
              <img :src="social.src" :alt="social.alt">
            </span> -->
          </div>
          <div class="container">
            <div class="row">
              <div id="menu" class="d-block d-sm-none col-12">
                <a data-action="bio" id="bio_button" style="animation-delay:0.9s;"
                  @click="summaryShowing = !summaryShowing">{{summaryShowing ? 'BIO' : 'BACK'}}</a>
                <a data-action="biz_inquiries" href="mailto:hello@amanze.me" id="biz_inquiries_button" class="button" style="animation-delay:1.1s;">hello@amanze.me</a>
              </div>
            </div>
          </div>
        </header>
        <main ref="intro-main">
          <div class="container pad" style="position: relative; margin-top: 2em;">
            <div class="row">
              <div class="d-block d-sm-none col-12">
                <div id="main-image" class="centered-circle" style="animation-delay:0.4s;"></div>
              </div>
            </div>
            <div class="row">
              <div class="d-none d-sm-block col-12">
                <div id="main-image"></div>
              </div>
            </div>
            <div class="row">
              <div class="d-none d-sm-block col-12">
                <div id="caption-holder">
                  <div class="caption">Hi,</div>
                  <div class="main-text">Everyone</div>
                </div>
              </div>
            </div>
          </div>
        </main>
      </section>
      <section id="hand-drawer">
        <div class="flex container">
          <div style="flex:1;"></div>
          <div style="" class="flex">
            <div id="right-hand" class="right">
              <img src="/img/right_shad_80h.png" class="hand" alt="right hand">
            </div>
            <div id="left-hand" class="">
              <img src="/img/left_shad_80h.png" class="hand" alt="left hand">
            </div>
          </div>
        </div>
      </section>
      <section id="about">
        <div class="container">
          <div class="row">
            <div id="menu" class="d-none d-sm-block col-12">
              <a data-action="bio" id="bio_button" style="animation-delay:0.9s;"
                @click="summaryShowing = !summaryShowing">{{summaryShowing ? 'BIO' : 'BACK'}}</a>
              <a data-action="biz_inquiries" href="mailto:hello@amanze.me" id="biz_inquiries_button" class="button" style="animation-delay:1.1s;">hello@amanze.me</a>
            </div>
          </div>
          <div id="summary" v-if="summaryShowing">
            <div class="content">
              <h1 style="animation-delay:0.4s;">Amanze Ogbonna</h1>
              <h2 style="animation-delay:0.4s;">SOFTWARE ENGINEER</h2>
              <center>
                <p style="animation-delay:0.4s;">Designer and Developer who loves solving probles. Obsessed with alternative energy and web technology</p>
              </center>
            </div>
            <div>
              <span class="social-icon" v-for="(social, pos) in socials" :key="pos" @click="goto(social.url)">
                <img :src="social.src" class="hand" :alt="social.alt">
              </span>
            </div>
          </div>
          <div id="bio" v-else>

            <div class="content text-left">
              <p>Born in Lagos Nigeria on July 5th, 1990, into the house of Edward Ogbonna Akor and Paulina Ulumma Akor. Amanze has always been a curious person who wants to know how things work. He ventured into science to find his answers. </p>
              <p style="animation-delay:0.2s;">After been selected from thousands of candidates to join the Meltwater Entrepreneurial School of Technology community in 2015, where he met his cofounder. He and his Co-founder were able to raise $50,000 to solve a problem in the Agric sector. </p>
              <p style="animation-delay:0.4s;">Amanze is also a Computer scientist, Software Engineer, Product Manager, Entrepreneur and is familiar with the West African entrepreneurial landscape. Experienced in managing a strong software development team and bringing the best out of everyone. </p>
              <p style="animation-delay:0.6s;">After his ordeal of growing up with the bad power supply in Nigeria, his future interest is in finding and using alternative power sources to support the electric grid and help make good, reliable and affordable electricity to be accessible to the common
                man.
              </p>
            </div>
          </div>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
require('../assets/css/bootstrap-grid.css')

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data: () => ({
    summaryShowing: true,
    socials: [
      {
        src: "/img/github.svg",
        alt: "github",
        url: "//github.com/darlingtonamz"
      },
      {
        src: "/img/linkedin.svg",
        alt: "linkedin",
        url: "//linkedin.com/in/amanze"
      },
      {
        src: "/img/twitter.svg",
        alt: "twitter",
        url: "//twitter.com/am_zee"
      }
    ]
  }),
  methods: {
    goto (url) {
      window.open(url, '_blank');
    }
  },
  mounted() {
    setTimeout(() => {
      this.$refs['intro-main'].classList.add("active")
    }, 1000)
  }
}
</script>

<style lang="scss">
@import url('/assets/css/bootstrap-grid.css');

html, body, #app {height: 100vh;}

.flex {display: flex; }
body {
  margin: 0;
  color: #525252;
  // font-family: 'Rubik';
  font-family: 'Rubik', sans-serif !important;
  // background: #FAFBFE;
}

h1 {
  font-size: 5vw;
  font-weight: 300;
  animation-name: slide_down;
  animation-duration: 2s;
  margin: 10px;
  display: block;
  margin-block-start: 0.67em;
  margin-block-end: 0.67em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
}
h2 {
  color: #BDBFAE;
  font-weight: 600;
  font-size: 20px;
  animation-name: h2;
  animation-duration: 3s;
  text-align: center;
  display: block;
  margin-block-start: 0.83em;
  margin-block-end: 0.83em;
  margin-inline-start: 0px;
  margin-inline-end: 0px;
}
#app {
  // font-family: 'Avenir', Helvetica, Arial, sans-serif;
  font-family: 'Rubik', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.pad {padding: 16px;}
.content-container {
  position: absolute;
  width: 50%;
  right: 0;
  top: 0;
  height: 100%;
  overflow: hidden;
  background-color: white;
}

* {
  -webkit-transition: cubic-bezier(1.000, 0.000, 0.000, 1.000);
  animation-fill-mode: both;
  box-sizing: border-box;
}
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
    background: url('/img/me.png') no-repeat bottom;
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
    color: #b4b4c3 !important;
    font-size: 3em;
  }

  .centered-circle {
    position: unset !important;
    border-radius: 50%;
    height: 150px !important;
    width: 150px !important;
    box-shadow: 0px 5px 10px -2px;
    margin: auto;
    background-size: cover !important;
    animation-name: slide_up;

  }
}
#intro {
  // background: white;
  background: url('/static/img/bg.svg') no-repeat fixed right;
  // background: #FFFFFF;
  background: #FAFBFE;

  .social-icon {
      height: 20px;
    width: 20px;
    background: white;
    margin: 5px;
    cursor: pointer;
  }
}

#hand-drawer {
  // background: #FAFBFE;
  position: relative;
  z-index: 2;
  box-shadow: 0px -5px 10px -10px;

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

}
#menu {
  text-align: right;
  position: absolute;
  top: 1em;
  right: 1em;
  z-index: 2;

  a {
    padding: 10px 16px;
    animation-name: slide_down;
    animation-duration: 1s;
    display: inline-block;
    color: #BDBFAE;
    text-decoration: none;
    font-weight: 600;
    font-size: 12px;
    cursor: pointer;
    transition: color 0.3s, border-color 0.3s;
  }

  .button {
    padding: 0 16px;
    line-height: 30px;
    border: 1px solid #EAEAE5;
    border-radius: 30px;
    height: 30px;
    display: inline-block;
  }
}

.text-left {text-align: left !important;}
.content {
  vertical-align: middle;
  text-align: center;
  padding: 30px;
  p {
    max-width: 500px;
    left: 0;
    right: 0;
    margin: auto;
    animation-name: slide_down;
    animation-duration: 1s;
    margin-bottom: 40px;
    line-height: 150%;
    display: block;
    margin-block-start: 1em;
    margin-block-end: 1em;
    margin-inline-start: 0px;
    margin-inline-end: 0px;
  }
}
#bio {
  .content {
    margin: 0 auto;
    display: block;
    width: 100%;
    height: 100%;
    overflow-y: scroll;
    margin-top: 4em;
    padding-top: 0;
  }
  p {
    margin: 0 auto;
    text-align: left;
    display: block;
    font-size: 14px;
    margin: 0 auto 20px;
    animation-name: slide_up;
  }
}
#summary {
  .social-icon {
    height: 20px;
    width: 20px;
    background: white;
    margin: 5px;
    cursor: pointer;

    img {
      height: inherit;
    }

    &:hover {
      height: 23px;
      width: 23px;
    }
  }
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

.hand { cursor: pointer;}

@keyframes h2 {
  from { letter-spacing: 0; opacity:0; }
  to { letter-spacing: 10px }
}

@keyframes slide_down {
  from { transform: translateY(-22px); opacity:0; }
  to { transform: translateY(0px); }
}

@keyframes slide_up {
  from { transform: translateY(22px); opacity:0; }
  to { transform: translateY(0px); }
}

@media screen and (max-width: 700px) {
  h1 {
      font-size: 50px;
  }
}

@media screen and (max-width: 576px) {
  #intro {
    height: 350px;
  }
  #hand-drawer {
    display: none;
  }
  #about {
    box-shadow: 0px -5px 10px -10px;
  }
  #bio {
    .content {
      margin-top: 2em;
      padding-top: 0;
    }
  }
}
// @media screen and (max-width: 700px) {
//   body {
//     font-size: 16px;
//   }
//   .above-sm { display: none}
//   .sm { display: none}
// }
</style>
