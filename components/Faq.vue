<template>
  <div>
    <h2 data-aos="flip-left" data-aos-duration="1000">FAQ</h2>
    <div class="faq-container">
      <div
        id="faq"
        class="faq-question"
        data-aos="flip-left"
        data-aos-duration="1000"
        @click="f1 = !f1"
      >
        <h3>How many NFTs will The Flamingo Mafia include?</h3>
        <h3 v-if="f1">
          The collection will include 10101 unique Flamingos. The collection was
          built from over 140 different traits. A detailed list is available on
          the website in section - traits.
        </h3>
      </div>

      <div
        class="faq-question"
        data-aos="flip-right"
        data-aos-duration="1000"
        @click="f2 = !f2"
      >
        <h3>What is the hierarchy system?</h3>
        <h3 v-if="f2">
          The hierarchy system is a unique Flamingo Mafia Family feature. There
          are 4 Flamingo groups with a limited count - Soldiers (7777),
          Caporegimes (1813), Consiglieres (400) & Bosses (111). Every group has
          their special customized traits & special benefits mentioned in the
          roadmap.
        </h3>
      </div>

      <div
        class="faq-question"
        data-aos="flip-left"
        data-aos-duration="1000"
        @click="f3 = !f3"
      >
        <h3>Why was the Flamingo Mafia Family built on the Polygon Network?</h3>
        <h3 v-if="f3">
          Polygon network is fast & cheap blockchain technology. Every
          transaction related to Flamingo transporting is very cheap. It is also
          supported by OpenSea market, the biggest NFT marketplace.
        </h3>
      </div>

      <div
        class="faq-question"
        data-aos="flip-right"
        data-aos-duration="1000"
        @click="f4 = !f4"
      >
        <h3>Where can I buy Flamingos?</h3>
        <h3 v-if="f4">
          In the minting phase, every Flamingo NFT can be minted on this website
          by interacting with the Polygon network contract. Every Flamingo is
          going to be revealed from an egg. Every holder can reveal their own
          egg by interacting with the contract on this page. After the Minting
          phase, Flamingo Mafia Family will be available in the OpenSea portal.
        </h3>
      </div>

      <div
        class="faq-question"
        data-aos="flip-left"
        data-aos-duration="1000"
        @click="f5 = !f5"
      >
        <h3>What is the reveal feature & how to use it?</h3>
        <h3 v-if="f5">
          Every Flamingo is hiding in an egg. The holder can reveal this egg and
          see exactly what Flamingo type they got! To do this, he must go to the
          Reveal section which is only visible for Flamingo Mafia Family
          holders. After the reveal, the holder should refresh Flamingo metadata
          on the OpenSea portal.
        </h3>
      </div>

      <div
        class="faq-question"
        data-aos="flip-left"
        data-aos-duration="1000"
        @click="f7 = !f7"
      >
        <h3>Where can I find more Flamingos, to see how they look?</h3>
        <h3 v-if="f7">
          NFT pictures are regularly published on our Twitter :-)
        </h3>
      </div>

      <div
        class="faq-question"
        data-aos="flip-right"
        data-aos-duration="1000"
        @click="f6 = !f6"
      >
        <h3>Who is The Flamingo Mafia Family Team?</h3>
        <h3 v-if="f6">
          The Flamingo Mafia Family was created only by one person -
          DonFlamingo. He is an artist, developer, marketer & NFT aficionado who
          wants to change his life by building the best community on the Polygon
          chain :-).
        </h3>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'FmfFaq',
  data: () => ({
    f1: false,
    f2: false,
    f3: false,
    f4: false,
    f5: false,
    f6: false,
    f7: false,
  }),
}
</script>

<style>
.faq-container {
  display: flex;
  flex-direction: column;
  gap: 30px;
}

.faq-question {
  cursor: pointer;
  padding: 30px;
  text-align: center;
  display: flex;
  flex-direction: column;
  border: 2px solid white;
  border-style: solid;
  gap: 30px;
  background-color: #1a1a1b;

  transition: all 0.5s linear;
  transition: width 1s ease-in-out;
}

.faq-question:hover {
  border: 2px solid #f7a234;
  transform: scale(1.2) !important;
}
.faq-question:hover h3 {
  color: #f7a234 !important;
}
</style>
