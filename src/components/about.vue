<template>
  <section id="about">
    <div class="container">
      <div class="row">
        <h1>About</h1>
        <div class="block"></div>
        <p>
          Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam
          nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat,
          sed diam voluptua. At vero eos et accusam et justo duo dolores et ea
          rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem
          ipsum dolor sit amet.
        </p>
      </div>
      <div class="row">
        <div class="six columns">
          <textcardVue></textcardVue>
        </div>
        <div class="six columns">
          <h3><span class="typcn typcn-pen icon"></span>Our Approach</h3>
          <p>
            Sed ut perspiciatis unde omnis iste natus error sit voluptatem
            accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
            quae ab illo inventore veritatis et quasi architecto beatae vitae
            dicta sunt explicabo.
          </p>
        </div>
        <div class="row">
          <div class="six columns">
            <h3><span class="typcn typcn-cog-outline icon"></span>Our Goal</h3>
            <p>
              Sed ut perspiciatis unde omnis iste natus error sit voluptatem
              accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
              quae ab illo inventore veritatis et quasi architecto beatae vitae
              dicta sunt explicabo.
            </p>
          </div>
          <div class="six columns">
            <h3><span class="typcn typcn-lightbulb icon"></span>Our Mission</h3>
            <p>
              Sed ut perspiciatis unde omnis iste natus error sit voluptatem
              accusantium doloremque laudantium, totam rem aperiam, eaque ipsa
              quae ab illo inventore veritatis et quasi architecto beatae vitae
              dicta sunt explicabo.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import textcardVue from './textcard.vue';
</script>

<style lang="scss" scoped>
#about {
  padding: 100px 0 50px 0;
  h1 {
    line-height: 1.2;
    letter-spacing: -0.1rem;
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
  .container {
    position: relative;
    width: 100%;
    max-width: 960px;
    margin: 0 auto;
    padding: 0 20px;
    box-sizing: border-box;
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