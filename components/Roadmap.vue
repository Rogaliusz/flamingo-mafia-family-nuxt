<template>
  <div id="roadmap" class="roadmap">
    <h2 data-aos="fade-up" data-aos-duration="1000">Roadmap</h2>
    <div class="roadmap-container">
      <div
        class="roadmap-percentage-container"
        data-aos="fade-up"
        data-aos-duration="1000"
      >
        <div class="roadmap-progress">
          <h2>7%</h2>
        </div>

        <div
          class="roadmap-divider"
          data-aos="fade-up"
          data-aos-duration="1000"
        ></div>

        <div class="roadmap-progress">
          <h2>15%</h2>
        </div>

        <div
          class="roadmap-divider"
          data-aos="fade-up"
          data-aos-duration="1000"
        ></div>
        <div
          class="roadmap-progress"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>30%</h2>
        </div>

        <div
          class="roadmap-divider"
          data-aos="fade-up"
          data-aos-duration="1000"
        ></div>
        <div
          class="roadmap-progress"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>45%</h2>
        </div>

        <div
          class="roadmap-divider"
          data-aos="fade-up"
          data-aos-duration="1000"
        ></div>
        <div
          class="roadmap-progress"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>77%</h2>
        </div>

        <div
          class="roadmap-divider"
          data-aos="fade-up"
          data-aos-duration="1000"
        ></div>
        <div
          class="roadmap-progress"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>100%</h2>
        </div>
      </div>

      <div class="roadmap-content-container">
        <div
          class="roadmap-description"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>First job</h2>
          <h3>
            Start first PlayToEarn game where Flamingo Holders can get profit by
            staking.
          </h3>
        </div>

        <div
          class="roadmap-description"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>First shot</h2>
          <h3>The collection will be added to Rarity.tools.</h3>
        </div>

        <div
          class="roadmap-description"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>People talking</h2>
          <h3>
            Invest 5 ETH into dedicated marketing to increase The Flamingo Mafia
            Family fame.
          </h3>
        </div>

        <div
          class="roadmap-description"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>Population boom</h2>
          <h3>
            Exclusive 777 eggs drop for all Flamingos (Every boss gets one egg,
            the rest will be distributed randomly to other Flamingos).
          </h3>
        </div>

        <div
          class="roadmap-description"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>Jackpot</h2>
          <h3>7,77 Eth will be delivered to one lucky Flamingo Boss.</h3>
        </div>

        <div
          class="roadmap-description"
          data-aos="fade-up"
          data-aos-duration="1000"
        >
          <h2>Opponents are coming</h2>
          <h3>Dropped eggs are going to be revealed!</h3>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import 'aos/dist/aos.css' // You can also use <link> for styles

export default {
  name: 'fmfRoadmap',
}
</script>
<style>
.roadmap-container {
  display: flex;
}

.roadmap-percentage-container {
  display: flex;
  -moz-box-orient: vertical;
  -moz-box-direction: normal;
  flex-direction: column;
  -moz-box-align: center;
  align-items: center;
  grid-gap: 10px;
  gap: 10px;
  width: -moz-max-content;
  width: max-content;
}

.roadmap-progress {
  text-align: center;
  margin-top: auto;
  margin-bottom: auto;
  /* margin-left: 40px; */
}

.roadmap-progress > h2 {
  line-height: 0%;
  color: #f7a234;
}

.roadmap-divider {
  width: 2px;
  height: 54px;
  background: #1a1a1b;
}

.roadmap-content-container {
  display: -moz-box;
  display: flex;
  -moz-box-orient: vertical;
  -moz-box-direction: normal;
  flex-direction: column;
  grid-gap: 55px;
  gap: 55px;
  margin-left: 60px;
}

.roadmap-description {
  text-align: left;
}

.roadmap-description > h2 {
  margin: 0;
  font-size: 40px;
  color: #f7a234;
}

@media only screen and (max-width: 768px) {
  /* For mobile phones: */

  .roadmap-container {
    margin-right: 0px;
  }

  .content {
    width: 100%;
  }

  .roadmap-description > h2 {
    font-size: 24px;
  }

  .roadmap-description > h3 {
    font-size: 18px;
  }

  .roadmap-content-container {
    grid-gap: 28px;
    gap: 28px;
    margin-left: 30px;
  }

  .roadmap {
    max-width: 1300px;
  }
}
</style>
