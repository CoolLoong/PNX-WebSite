<template>
  <section id="about">
    <div class="container">
      <div class="frist">
        <h2>{{ $t("message.about-frist") }}</h2>
        <div class="block"></div>
      </div>
      <div class="group">
        <textCard
          v-for="textCard in textCardGroup"
          :typcn-icon="textCard.icon"
          :title="textCard.title"
          :content="textCard.content"
          :key="textCard.id"
        >
        </textCard>
      </div>
    </div>
  </section>
</template>

<script setup>
import textCard from "./textcard.vue";
import { useI18n } from "vue-i18n";
const { t } = useI18n();
const textCardGroup = [
  {
    icon: "typcn-chart-line",
    title: t("message.about-textcard1-title"),
    content: t("message.about-textcard1-content"),
  },
  {
    icon: "typcn-folder-add",
    title: t("message.about-textcard2-title"),
    content: t("message.about-textcard2-content"),
  },
  {
    icon: "typcn-cog-outline",
    title: t("message.about-textcard3-title"),
    content: t("message.about-textcard3-content"),
  },
  {
    icon: "typcn-device-desktop",
    title: t("message.about-textcard4-title"),
    content: t("message.about-textcard4-content"),
  },
  {
    icon: "typcn-puzzle-outline",
    title: t("message.about-textcard5-title"),
    content: t("message.about-textcard5-content"),
  },
  {
    icon: "typcn-th-small-outline",
    title: t("message.about-textcard6-title"),
    content: t("message.about-textcard6-content"),
  }
];
</script>

<style lang="scss" scoped>
#about {
  padding: 120px 0 50px 0;
  .container {
    position: relative;
    width: 100%;
    max-width: 1200px;
    height: 600px;
    margin: 0 auto;
    padding: 0 20px;
    box-sizing: border-box;
    .group {
      display: flex;
      flex-wrap: wrap; //装不下就换行
      justify-content: space-between;
      align-content: space-between;
      height: 455px;
      overflow: hidden;
    }
    .frist {
      h2 {
        font-size: 40px;
        font-weight: 300;
      }
      .block {
        width: 70px;
        height: 2px;
        background: #e55d87;
        background: -moz-linear-gradient(-45deg, #e55d87 0%, #5fc3e4 100%);
        background: -webkit-linear-gradient(-45deg, #e55d87 0%, #5fc3e4 100%);
        background: linear-gradient(135deg, #e55d87 0%, #5fc3e4 100%);
        margin-bottom: 50px;
      }
    }
  }
  .container:after,
  .row:after,
  .u-cf {
    content: "";
    display: table;
    clear: both;
  }
  .six.columns {
    width: 48%;
  }
}
</style>