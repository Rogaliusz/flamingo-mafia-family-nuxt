<template>
  <div id="hierarchy">
    <h2 class="h-title">Hierarchy</h2>

    <div class="fraction-item" data-aos="fade-right" data-aos-duration="1000">
      <div class="fraction">
        <img src="@/static/assets/soldier.webp" width="300" height="300" />
      </div>

      <div class="fraction-content fraction-content-left">
        <h2>Soldiers - 7777</h2>
        <h3>Special Flamingos dedicated to "solving" problems.</h3>
        <h3>They spend their free time in jail or helping their superiors.</h3>
        <h3>They love drugs, money & guns.</h3>
        <h3>Always carrying.</h3>
      </div>
    </div>

    <div
      class="fraction-item"
      style=""
      data-aos="fade-right"
      data-aos-duration="1000"
    >
      <div class="fraction">
        <img src="@/static/assets/caporegime.webp" width="300" height="300" />
      </div>
      <div class="fraction-content fraction-content-right">
        <h2>Caporegimes - 1813</h2>
        <h3>Good looking, captains of flamingo soldiers.</h3>
        <h3>Love the best suits & bags of cash.</h3>
        <h3>If possible, they have more than one gun.</h3>
        <h3>On vacations, they like to rest on the beach.</h3>
      </div>
      <div class="fraction"></div>
    </div>

    <div class="fraction-item" data-aos="fade-right" data-aos-duration="1000">
      <div class="fraction">
        <img src="@/static/assets/consigliere.webp" width="300" height="300" />
      </div>
      <div class="fraction-content fraction-content-left">
        <h2>Consiglieres - 400</h2>
        <h3>The most trust boss flamingos.</h3>
        <h3>Their hallmark is floral shirts.</h3>
        <h3>Don't take part in robberies.</h3>
        <h3>Loves cash collected from their caporegimes.</h3>
      </div>
    </div>

    <div class="fraction-item" data-aos="fade-right" data-aos-duration="1000">
      <div class="fraction">
        <img src="@/static/assets/boss.webp" width="300" height="300" />
      </div>
      <div class="fraction-content fraction-content-right">
        <h2>Bosses - 111</h2>
        <h3>The Flamingos on top.</h3>
        <h3>They live in Villas.</h3>
        <h3>Floral suits are their passion.</h3>
        <h3>If you're lucky, equipped with laser eyes.</h3>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'FmfFractions',
}
</script>

<style>
@import './Fractions.scss';
</style>
