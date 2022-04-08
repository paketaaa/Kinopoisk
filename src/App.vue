<template>
   <div id="app">
      <div class="cloud cloud--1"><img src="../public/img/cloud-1.png" alt="Cloud Decoration"></div>
      <div class="cloud cloud--2"><img src="../public/img/cloud-2.png" alt="Cloud Decoration"></div>
      <AppHeader />
      <div class="container">
         <div class="title"><h1>Они должны что-то знать</h1></div>
      </div>
      <MainSlider class="main-swiper" />
      <aside class="aside">
         <div class="aside__step">
            <span>01</span>
            <small>А что вы делаете</small>
         </div>
         <div class="aside__step">
            <span>02</span>
            <small>В моем холодильнике</small>
         </div>
         <div class="aside__step active">
            <span>03</span>
            <small>Подсказки</small>
         </div>
         <div class="aside__step">
            <span>04</span>
            <small>????</small>
         </div>
      </aside>
      <!-- two different methods to use links -->
      <div class="promo-find">
         <a href="">
            <span>Искать промокод</span>
            <svg
               width="28"
               height="5"
               viewBox="0 0 28 5"
               fill="none"
               xmlns="http://www.w3.org/2000/svg"
            >
               <path d="M0.370911 2.8553L26.7406 2.8553" stroke="#333333" />
               <path
                  d="M25.0246 4.54921L26.7453 2.8285L25.0246 1.13766"
                  stroke="#333333"
               />
            </svg>
         </a>
      </div>
      <a href="https://hd.kinopoisk.ru/" target="_blank" class="promo">
         hd.kinopoisk.ru
      </a>
      <button class="scroll-down">
         <svg
            width="64"
            height="5"
            viewBox="0 0 64 5"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
         >
            <path d="M63 2.53526L0.865013 2.53526" stroke="#333333" />
            <path
               d="M2.58105 0.841358L0.860344 2.56207L2.58105 4.25291"
               stroke="#333333"
            />
         </svg>
         Скрольте вниз
      </button>
   </div>
</template>

<script>
import AppHeader from "./components/AppHeader.vue";
import MainSlider from "./components/MainSlider.vue";

export default {
   data() {
      return {};
   },
   components: {
      AppHeader,
      MainSlider: MainSlider,
   },
};
</script>

<style lang="scss">
@import "../src/assets/scss/_variables.scss";
@import "../src/assets/scss/_fonts.scss";
@import "../src/assets/scss/_header.scss";
@import "../src/assets/scss/_config.scss";

.app-bg {
   position: absolute;
   width: 100%;
   height: 100%;
   top: 0;
   left: 0;
   z-index: -1;

   img {
      display: block;
      width: 100%;
      height: 100%;
      object-fit: cover;
   }
}

#app {
   position: relative;
   // display: flex;
   // flex-direction: column;
   overflow: hidden;
   font-family: "kp", Arial, sans-serif;
   font-weight: 400;
   -webkit-font-smoothing: antialiased;
   -moz-osx-font-smoothing: grayscale;
   text-align: center;
   color: #000;
   min-height: 500px;
   overflow: hidden;
   padding-bottom: 80px;

   font-size: 10px;

   background: url("../public/img/sky-bg.png") no-repeat center/cover;
}

.title {
   position: relative;
   font-family: "Futura";
   font-weight: 700;
   text-transform: uppercase;
   font-size: 4.5em;
   line-height: 72px;
   font-weight: 700;
   color: #ffcc64;
   margin-bottom: 32px;
   letter-spacing: -0.4px;
   z-index: 10;

   h1 {
      margin: 0;
      font-weight: inherit;
      font-size: inherit;
   }
}

.logo {
   position: relative;
   display: block;
   z-index: 10;
   img {
      display: block;
   }
}

.aside {
   position: absolute;
   display: flex;
   flex-direction: column;
   flex-wrap: wrap;

   left: 35px;
   top: calc(50% + 8px);
   transform: translateY(-50%);
   margin-top: -66px;
   z-index: 10;

   &__step {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      min-width: 8px;
      width: max-content;
      max-width: 100%;
      padding-bottom: 5px;
      border-bottom: 1px solid #333;

      margin-bottom: 50px;

      line-height: 15px;

      &:last-child {
         margin-bottom: 0;
      }

      &:not(.active) {
         padding-bottom: 0;
         > * {
            display: none;
         }
      }

      &.active {
         margin-top: -18px;
      }

      span,
      small {
         display: block;
      }

      span {
         font-size: 1.6em;
         font-weight: 500;
         margin-right: 20px;
      }

      small {
         font-size: 1.4em;
      }
   }
}

.scroll {
   &-down {
      font-size: 1.4em;
      line-height: 15px;
      position: absolute;
      left: -62px;
      bottom: 117px;
      width: max-content;
      transform: rotate(-90deg);

      display: flex;
      flex-wrap: wrap;
      align-items: center;
      z-index: 10;

      svg {
         margin-right: 24px;
      }
   }
}

.promo {
   position: absolute;
   top: calc(50% - 18px);
   right: -15px;
   transform: translateY(50%) rotate(90deg);

   font-size: 1.4em;
   line-height: 15px;
   color: #333333;
   text-decoration: none;
   z-index: 10;
   &:hover {
      color: #cd931b;
   }
   &-find {
      width: max-content;
      max-width: 400px;
      margin-left: auto;
      margin-right: auto;
      position: relative;
      color: #333333;
      background: #fff;
      border-radius: 8px;
      font-size: 1.5em;

      z-index: 10;

      a {
         text-decoration: none;
         display: inline-flex;
         align-items: center;
         padding: 20px;
         border-radius: 8px;
         box-shadow: 0px 5px 26px rgba(11, 75, 92, 0.0975713);

         svg {
            margin-left: 16px;
         }
      }

      svg {
         path {
            transition: all 0.3s ease;
         }
      }
      &:hover {
         color: #cd931b;

         svg {
            path {
               stroke: #cd931b;
            }
         }
      }
   }
}

.cloud{
   position: absolute;
   pointer-events: none;

   &--1{
      top: -26px;
      left: 140px;
      transform: rotate(-20deg);
   }

   &--2{
      top: 67px;
      right: 220px;
      transform: rotate(-120deg);
   }
}

.container {
   position: relative;
   margin-left: auto;
   margin-right: auto;
   padding-right: 187px;
   padding-left: 187px;
   @include animate;
}

@media (max-width: 1199px) {
   // 1199px
   #app {
      font-size: 9px;
   }
}

@media (max-width: 1070px) {
   .title {
      font-size: 4em;
   }
}

@media (max-width: 991px) {
   // 991px
   .title {
      font-size: 3.4em;
   }
}


@media (max-height: 666px) {
   #app{
      min-height: initial;
      padding-bottom: 12px;
   }
   .title{
      line-height: 1;
   }
}

</style>
