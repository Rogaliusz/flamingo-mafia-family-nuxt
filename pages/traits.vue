<template>
  <div>
    <h2 style="margin-top: 70px">Traits</h2>
    <h3>
      The Flamingo Mafia Family collection was built from over 140 different
      traits.
    </h3>
    <h3>
      The list contains details about the used traits. It has information about
      the type, rarity & name.
    </h3>
    <h3>
      It's sorted by rarity, so the rarest traits are displayed on the top.
    </h3>

    <div class="traits-container">
      <div class="trait" data-aos="fade-up" data-aos-duration="1000">
        <h3 v-show="!$device.isMobile" style="flex-basis: 25%">Index</h3>
        <h3 style="flex-basis: 25%">Trait type</h3>
        <h3 style="flex-basis: 25%">Value</h3>
        <h3 style="flex-basis: 25%; text-align: right">Rarity</h3>
      </div>
      <div
        v-for="(trait, index) in traits"
        :key="trait.id"
        class="trait"
        data-aos="fade-up"
        data-aos-duration="1000"
      >
        <h3 v-show="!$device.isMobile" style="flex-basis: 25%">{{ index }}.</h3>
        <h3 style="flex-basis: 25%">{{ trait.Type }}</h3>
        <h3 style="flex-basis: 25%">{{ trait.Value }}</h3>
        <h3 style="flex-basis: 25%; text-align: right">
          {{ trait.Rarity.toFixed(2) }} %
        </h3>
      </div>
    </div>
  </div>
</template>

<script>
import json from '@/static/traits-stats.json'

export default {
  name: 'Traits',
  data: () => ({
    traits: json,
  }),
}
</script>
<style>
.traits-container {
  margin-top: 40px;
  display: flex;
  flex-direction: column;
  gap: 20px;
}
.trait {
  display: flex;
  flex-direction: row;
  cursor: pointer;
  padding: 30px;
  text-align: left;
  border: 2px solid white;
  border-style: solid;
  background-color: #1a1a1b;
  transition: all 0.5s linear;
  transition: width 1s ease-in-out;
  display: inline-flex;
  flex-wrap: wrap;
}

.trait:hover {
  border: 2px solid #f7a234;
  transform: scale(1.2) !important;
}
.trait:hover h3 {
  color: #f7a234 !important;
}

@media only screen and (max-width: 768px) {
  .trait {
    flex-direction: column;
  }
}
</style>
