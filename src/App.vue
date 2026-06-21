<template>
  <div class="app-root">
    <Header />
    <main>
      <router-view v-slot="{ Component, route }">
        <Transition name="page" mode="out-in">
          <component :is="Component" :key="route.path" />
        </Transition>
      </router-view>
    </main>
    <Footer />
  </div>
</template>

<script setup>
import Header from '@/components/Header.vue'
import Footer from '@/components/Footer.vue'
</script>

<style>
:root {
  --bg-0: #042F33;
  --bg-1: #063940;
  --bg-2: #084550;
  --accent: #0E7490;
  --accent-dark: #0B5D73;
  --accent-light: #22D3EE;
  --text: #E8E8ED;
  --heading: #FAFAFA;
  --muted: rgba(255,255,255,0.45);
  --glass: rgba(255,255,255,0.03);
  --border-s: rgba(14,116,144,0.12);
  --border-m: rgba(14,116,144,0.20);
  --border-l: rgba(14,116,144,0.30);
  --glow-sm: 0 0 20px rgba(34,211,238,0.15);
  --glow-md: 0 0 40px rgba(34,211,238,0.20);
  --font-body: 'Inter', sans-serif;
  --font-head: 'Outfit', sans-serif;
  --ease-out: cubic-bezier(0.16, 1, 0.3, 1);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }

body {
  background: var(--bg-0);
  color: var(--text);
  font-family: var(--font-body);
  font-weight: 300;
  font-size: 0.9rem;
  line-height: 1.7;
  overflow-x: hidden;
}

body::before {
  content: '';
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 1000;
  opacity: 0.035;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='300' height='300'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.85' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='300' height='300' filter='url(%23noise)' opacity='1'/%3E%3C/svg%3E");
}

h1, h2, h3, h4 {
  font-family: var(--font-head);
  color: var(--heading);
  font-weight: 200;
  letter-spacing: -0.03em;
  line-height: 1.15;
}
h1 { font-size: clamp(2.4rem, 5vw, 3.8rem); font-weight: 200; }
h2 { font-size: clamp(1.8rem, 3vw, 2.2rem); }
h3 { font-size: 1.1rem; font-weight: 300; }
p { color: var(--text); font-weight: 300; font-size: 0.84rem; line-height: 1.72; }
a { color: var(--text); text-decoration: none; }

.text-gradient {
  background: linear-gradient(135deg, var(--accent-light) 0%, var(--accent) 50%, #67E8F9 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-label {
  display: inline-block;
  font-size: 0.68rem;
  font-weight: 500;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--accent-light);
  margin-bottom: 12px;
}

.container {
  max-width: 1180px;
  margin: 0 auto;
  padding: 0 40px;
  position: relative;
  z-index: 1;
}

.section {
  position: relative;
  padding: 64px 0;
  overflow: hidden;
}
.section-alt { background: var(--bg-1); }

.section-header {
  text-align: center;
  margin-bottom: 64px;
}
.section-header p {
  max-width: 540px;
  margin: 12px auto 0;
  color: var(--muted);
  font-size: 0.86rem;
}

.section-sep {
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, rgba(14,116,144,0.3), transparent);
}

::-webkit-scrollbar { width: 5px; }
::-webkit-scrollbar-track { background: var(--bg-0); }
::-webkit-scrollbar-thumb { background: rgba(34,211,238,0.3); border-radius: 3px; }
::-webkit-scrollbar-thumb:hover { background: rgba(34,211,238,0.5); }

@media (max-width: 991px) {
  .container { padding: 0 24px; }
}
@media (max-width: 574px) {
  .container { padding: 0 16px; }
  .section { padding: 48px 0; }
}
</style>
