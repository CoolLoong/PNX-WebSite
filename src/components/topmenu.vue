<template>
  <div>
    <Transition name="nav">
      <div class="top" v-show="isActive">
        <div class="container">
          <div class="mobile-toggle">
            <span></span> <span></span> <span></span>
          </div>
          <nav id="topnav">
            <div id="logo">
              <router-link to="/" class="logotext">PowerNukkitX</router-link>
            </div>
            <div id="menu">
              <!-- TODO 写路由 -->
              <router-link to="/">{{
                $t("message.topmenu-menu1")
              }}</router-link>
              <router-link to="/download">{{
                $t("message.topmenu-menu2")
              }}</router-link>
              <a href="#">{{ $t("message.topmenu-menu3") }}</a>
              <a href="#">{{ $t("message.topmenu-menu4") }}</a>
              <a href="#">{{ $t("message.topmenu-menu5") }}</a>
              <a href="#">{{ $t("message.topmenu-menu6") }}</a>
            </div>
            <div class="righticon">
              <div class="link">
                <ion-icon name="logo-github"></ion-icon>
                <ion-icon name="logo-discord"></ion-icon>
                <ion-icon name="mail-outline"></ion-icon>
              </div>
              <Lang></Lang>
            </div>
          </nav>
        </div>
      </div>
    </Transition>
    <a class="smoothscroll" href="#about">
      <div class="scroll-down"></div>
    </a>
  </div>
  <!-- <div class="container">
    <div class="menu"></div>
  </div> -->
</template>

<script setup>
import { onMounted, onUnmounted, ref } from "vue";
import Lang from "./lang.vue";

//控制nav是否显示
let isActive = ref(true);

onMounted(() => window.addEventListener("scroll", navigation)); //监听滚动
onUnmounted(() => window.removeEventListener("scroll", navigation));

function navigation() {
  //滚动距离效果
  let scrollY = document.documentElement.scrollTop;
  if (scrollY > 400) {
    isActive.value = false;
  } else {
    isActive.value = true;
  }
}
</script>

<style lang="scss" scoped>
.top {
  display: -webkit-flex; /* Safari */
  display: flex;
  justify-content: center; //里面的元素水平垂直居中
  align-items: center;
  -webkit-box-pack: center;
  position: fixed;
  height: 100%;
  width: 100%;
  max-height: 60px;
  z-index: 3;
  background: none;
  overflow: hidden;
  transition: all 0.3s;
  padding-bottom: 4px;
  background-color: #ffffff;
  .container {
    max-width: 1080px;
    width: 100%;
    margin: 0 auto;
    padding: 0 20px;
    box-sizing: border-box;
    .mobile-toggle {
      display: none;
      cursor: pointer;
      font-size: 20px;
      position: absolute;
      right: 22px;
      top: 0;
      width: 30px;
      span {
        width: 30px;
        height: 4px;
        margin-bottom: 6px;
        background: #000000;
        display: block;
      }
    }
    #topnav {
      display: -webkit-flex; /*兼容Safari*/
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      #logo {
        margin-right: auto;
        @media screen and (max-width: 1150px) {
          & {
            margin-right: auto;
          }
        }
        .logotext {
          font-weight: 500;
          font-size: 22px;
          font-family: "Poppins", sans-serif;
          text-decoration: none;
          text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.15);
          color: #000000;
          opacity: 0.9;
          &:hover {
            transition: all 0.2s linear;
            background-image: -webkit-linear-gradient(
              left,
              #e9a5a5,
              #b8c1c0 10%,
              #65c0e0 20%,
              #aea2db 30%,
              #81c1d9 40%,
              #e9a5a5 50%,
              #b8c1c0 60%,
              #65c0e0 70%,
              #aea2db 80%,
              #81c1d9 90%,
              #e9a5a5
            );
            text-shadow: none;
            opacity: 1;
            //文字透明
            color: transparent;
            /*将背景裁剪为文字 */
            -webkit-background-clip: text;
            /*背景放大一倍，动画才有移动的空间 */
            background-size: 50% 100%;
            /*动画 规定四秒执行完 无限循环 匀速播放 */
            animation: colorful 5s infinite linear;
          }
        }
      }
      #menu {
        display: -webkit-flex;
        display: flex;
        list-style: none;
        text-align: center;
        justify-content: center;
        align-items: center;
        height: 30px;
        a {
          display: -webkit-flex;
          display: flex;
          position: relative;
          flex-direction: column; //主轴设为纵向
          text-transform: uppercase; //转换文字大写
          font-weight: 500;
          font-size: 15px;
          text-decoration: none;
          color: rgba(0, 0, 0, 0.8);
          margin-right: 30px;
          &:after {
            content: "";
            position: absolute;
            z-index: 4;
            top: 11px;
            left: 0;
            width: 100%;
            height: 10px;
            border-radius: 30px;
            box-shadow: 0px 5px rgb(0, 208, 255);
            transition: opacity 0.2s linear;
            opacity: 0;
          }
          &:hover {
            color: rgba(0, 0, 0, 1);
            &:after {
              opacity: 1;
            }
          }
        }
      }
      .righticon {
        display: -webkit-flex;
        display: flex;
        align-items: center;
        ion-icon {
          top: 3px;
          margin-left: 5px;
        }
        .link ion-icon {
          position: relative;
          font-size: 25px;
          max-height: 35px;
          color: rgba(0, 0, 0, 0.8);
          transform: scale3d(1, 1, 1);
          transition: all 0.35s linear;
          cursor: pointer;
          &:nth-child(2) {
            position: relative;
            top: 4px;
          }
          &:hover {
            color: rgba(0, 0, 0, 1);
            transform: scale3d(1.1, 1.1, 1.1);
            transition: all 0.35s linear;
          }
        }
      }
    }
  }
}
@keyframes colorful {
  0% {
    background-position: 0 0;
  }

  100% {
    background-position: -100% 0;
  }
}
/*过渡效果*/
//nav
.nav-enter-active,
.nav-leave-active {
  transition: opacity 0.5s ease;
}
.nav-enter-from,
.nav-leave-to {
  opacity: 0;
}
</style>