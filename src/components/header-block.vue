<template>
  <header class="header-block fixed" id="header">
    <div class="container">
      <div class="header">
        <div class="header-block-left-logo pulse">
          <a href="#" class="logo"><img src="../assets/img/logo-header.png" alt="logo"></a>
        </div>
        <nav class="header-block-left-navigation">
          <ul class="header-block-left-navigation-item">
            <li id="Home"><a href="#">Home</a></li>
            <li><a href="#Courses">Courses</a></li>
            <li><a href="#Webinar">Webinar</a></li>
            <li><a href="#Prising">Prising</a></li>
          </ul>
        </nav>
        <div class="header-block-right">
          <button type="button" class="header-block-right-button" @click="showModal=true">Contact</button>
          <modal v-if="showModal" @close="showModal=false"/>
        </div>
        <div class="menu-mobile">
          <div class="header-block-left-logo pulse">
            <a href="#" class="logo"><img src="../assets/img/logo-header.png" alt="logo"></a>
          </div>
          <nav class="header-block-left-mobile">
            <ul class="header-block-left-navigation-mobile">
              <li id="Home" @click="openMenu"><a href="#">Home</a></li>
              <li @click="openMenu"><a href="#Courses">Courses</a></li>
              <li @click="openMenu"><a href="#Webinar">Webinar</a></li>
              <li @click="openMenu"><a href="#Prising">Prising</a></li>
            </ul>
          </nav>
          <div class="header-block-right-mobile">
            <button type="button" class="header-block-right-button" @click="showModal=true">Contact</button>
            <modal v-if="showModal" @close="showModal=false"/>
          </div>
        </div>
        <div class="burger">
          <button class="hamburger hamburger--slider" type="button" @click="openMenu">
            <span class="hamburger-box">
              <span class="hamburger-inner"></span>
            </span>
          </button>
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import Modal from '@/components/modal-block'
import "@/assets/css/humburger.scss"
export default {
  name: 'header-block',
  components: {
    Modal
  },
  data() {
    return {
      showModal: false,
    }
  },
  methods: {
    openMenu() {
      document.querySelector(".hamburger").classList.toggle("is-active")
      document.querySelector(".menu-mobile").classList.toggle("active")
    }
  }
};
</script>

<style lang="scss" scoped>
$background-color: #171836;
$background-color-element: #282B57;
$headings-text: rgba(255, 255, 255, 0.8);
$headings-text2: rgba(255, 255, 255, 0.7);
$headings-text3: rgba(59, 245, 189, 1);
$text-color: rgba(255, 255, 255, 0.4);
$text-color2: rgba(255, 255, 255, 0.6);
$text-color3: rgba(209, 209, 215, 1);
$text-color4: rgba(143, 145, 208, 1);
$text-button: rgba(255, 255, 255, 1);
$highlighting-elements: rgba(245, 68, 59, 1);
$highlighting-elements2: rgba(41, 43, 86, 1);
$highlighting-elements3: rgba(151, 153, 206, 1);
$highlighting-elements4: #212145;
$highlighting-elements5: #4c4567;
$highlighting-elements6: rgba(255, 255, 255, 0.2);
$icon-color: #ACABBF;
$focus-color: #008ABF;
$border-color: rgba(154, 156, 203, 0.6);
$headings: rgba(255, 255, 255, 0.6);

.header-block {
  position: fixed;
  width: 100%;
  height: 80px;
  left: 0;
  top: 0;
  z-index: 100;
  &.fixed {
    background-color: rgba($background-color, 0.8);
    border-bottom: 1px solid $background-color;
    box-shadow: 0 20px 20px -20px $background-color-element;
  }
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 14px;
  line-height: 16.94px;
  height: 80px;
    .header-block-left-logo {
    }
    .header-block-left-navigation {
      width: 58%;
      .header-block-left-navigation-item {
        display: flex;
        justify-content: space-between;
        li a {
          &:hover {
            color: $text-button;
          }
        }
      }
  }
  .header-block-right {
    .header-block-right-button {
      width: 102px;
      height: 43px;
      background-color: $highlighting-elements;
      color: $text-button;
      border-radius: 6px;
      border: 1px solid transparent;
      &:hover {
        border: 1px solid $focus-color;
        box-shadow:inset 0 0 15px 3px rgba(17, 37, 93, 1);
        background:linear-gradient(rgba(208, 2, 27, 1), rgba(208, 2, 27, 1));
      }
    }
  }
}
.menu-mobile {
  padding-left: 30px;
  position: fixed;
  width: 100%;
  background-color: $headings;
  box-shadow: 0 0 10px #FFF;
  backdrop-filter: blur(10px);
  height: 100vh;
  left: 0;
  top: 0;
  display: block;
  transition: all .3s ease;
  transform: translateX(-110%);
  &_heading {
    padding: 15px 0 20px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  &.active {
    transform: translateX(0);
    overflow: auto;
    background-color: rgba(151, 153, 206, .4);
  }
  .header-block-left-logo {
    margin-top: 20px;
  }
  ul {
    margin-top: 40px;
  }
  li {
    padding-bottom: 60px;
  }
  a {
    color: $background-color;
    font-size: 16px;
    text-shadow:5px 5px 5px rgba(143, 145, 208, 1);
  }
}
.burger {
  display: none;
}

@media screen and (max-width: 768px){
  .header {
    .header-block-left-navigation {
      display: none;
    }
    .burger {
      display: block;
    }
    .header-block-right {
     display: none;
    }
  }
  .header-block-right-mobile {
    padding: 10px 30px;
    width: 105px;
    text-align: center;
    background-color: $highlighting-elements;
    color: $text-button;
    border-radius: 6px;
    border: 1px solid transparent;
    &:hover {
      border: 1px solid $focus-color;
      box-shadow:inset 0 0 15px 3px rgba(17, 37, 93, 1);
      background:linear-gradient(rgba(208, 2, 27, 1), rgba(208, 2, 27, 1));
    }
  }
}
</style>