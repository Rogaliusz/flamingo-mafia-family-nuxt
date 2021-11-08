<template>
  <div>
    <About />
    <Minting />
    <Roadmap />
    <Fractions />
    <Faq />
  </div>
</template>

<script>
import About from '~/components/About.vue'
import Fractions from '~/components/Fractions.vue'
import Roadmap from '~/components/Roadmap.vue'
import Minting from '~/components/Minting.vue'
import Faq from '~/components/Faq.vue'
export default { components: { About, Fractions, Roadmap, Minting, Faq } }
</script>
