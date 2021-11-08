<template>
  <div style="background-color: #1a1a1b; margin-top: 40px">
    <div class="separator"></div>
    <div class="footer">
      <div style="flex-basis: 40%">
        <img
          src="@/static/assets/logo.webp"
          width="200"
          height="200"
          class="footer-logo"
        />
      </div>
      <div class="footer-section quick-links">
        <h2>Links</h2>
        <a
          href="https://twitter.com/donflamingonft"
          target="_blank"
          rel="noreferrer"
          >Twitter</a
        >
        <a href="https://discord.gg/k8JnYzgkpX" target="_blank" rel="noreferrer"
          >Discord</a
        >
        <a
          href="https://opensea.io/collection/flamingo-mafia-family"
          target="_blank"
          rel="noreferrer"
          >OpenSea</a
        >
        <a
          href="https://flamingomafiafamily.medium.com/"
          target="_blank"
          rel="noreferrer"
          >Medium</a
        >
        <a href="https://flamingopunks.com/" target="_blank" rel="noreferrer"
          >Flamingo Punks</a
        >
      </div>
      <div class="footer-section jump-to">
        <h2>Jump to</h2>
        <a href="/traits/">Traits</a>
        <a href="/#faq">FAQ</a>
        <a v-show="hasReveal" href="/#reveal">Reveal</a>
        <a href="/#mint">Mint</a>
        <a href="/#roadmap">Roadmap</a>
        <a href="/#hierarchy">Hierarchy</a>
        <a href="/#fmf">About FMF</a>
      </div>
    </div>
    <h3 style="padding: 30px">
      Copyright © 2021 The Flamingo Mafia Family. All rights reserved.
    </h3>
    <a
      style="margin-top: -30px"
      href="https://polygonscan.com/address/0xa2ba2540b950d7b2dab38f1ef08681811ce82ad3"
    >
      0xa2Ba2540B950D7B2dAb38F1EF08681811cE82aD3</a
    >
  </div>
</template>
<script>
export default {
  name: 'FmfFooter',
  props: ['hasReveal'],
}
</script>
<style>
.separator {
  margin: auto;
  border: 1px solid #ffffff;
}
.footer-logo {
  background: radial-gradient(
    50% 50% at 50% 50%,
    #f7a234 0%,
    rgba(255, 255, 255, 0.734375) 0.01%,
    rgba(252, 252, 252, 0.726798) 0.02%,
    #1a1a1b 100%
  );

  margin-top: 139px;
  display: block;
  margin-left: auto;
  margin-right: auto;
  width: 200px;
}

.footer {
  display: flex;
  margin: auto;
  max-width: 1600px;
  gap: 40px;
}

.footer-section {
  display: flex;
  flex-direction: column;
  gap: 20px;
  text-align: left;
}

.quick-links {
  flex-basis: 30%;
}

a {
  display: block;
  font-family: Teko;
  font-style: normal;
  font-weight: normal;
  font-size: 20px;
  line-height: 29px;
  color: #fff;
  text-decoration: none;
}

a:hover {
  color: #f7a234;
}

li a:hover {
  color: #fff;
}

@media only screen and (max-width: 768px) {
  .footer-logo {
    margin-top: 50px;
  }
  .footer {
    flex-direction: column;
    gap: 20px;
  }

  .footer-section {
    padding-left: 20px;
  }
}
</style>
