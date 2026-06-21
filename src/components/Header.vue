<template>
  <nav class="main-nav">
    <router-link to="/" class="nav-logo">
      <img class="nav-logo-img" src="/logo.png" alt="ArtrCredi" />
    </router-link>
    <ul class="nav-links">
      <li><router-link to="/como-funciona">Como Funciona</router-link></li>
      <li><router-link to="/sobre">Sobre</router-link></li>
      <li><router-link to="/contato">Contato</router-link></li>
    </ul>
    <div class="nav-cta">
      <a href="/#simulacao" class="btn-nav btn-nav-solid" @click.prevent="goToSim">Simular Credito</a>
    </div>
    <div class="nav-hamburger" :class="{ open }" @click="open = !open">
      <span></span><span></span><span></span>
    </div>
  </nav>
  <div class="nav-mobile" :class="{ open }">
    <ul>
      <li><router-link to="/como-funciona" @click="open=false">Como Funciona</router-link></li>
      <li><router-link to="/sobre" @click="open=false">Sobre</router-link></li>
      <li><router-link to="/contato" @click="open=false">Contato</router-link></li>
    </ul>
    <a href="/#simulacao" class="btn-nav btn-nav-solid" style="margin-top:20px" @click.prevent="goToSim();open=false">Simular Credito</a>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const open = ref(false)
const router = useRouter()

function goToSim() {
  if (router.currentRoute.value.path !== '/') {
    router.push('/').then(() => {
      setTimeout(() => {
        const el = document.getElementById('simulacao')
        if (el) el.scrollIntoView({ behavior: 'smooth' })
      }, 300)
    })
  } else {
    const el = document.getElementById('simulacao')
    if (el) el.scrollIntoView({ behavior: 'smooth' })
  }
}
</script>

<style scoped>
.main-nav {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 900;
  padding: 0 40px;
  height: 60px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: rgba(4,47,51,0.75);
  backdrop-filter: blur(16px);
  -webkit-backdrop-filter: blur(16px);
  border-bottom: 1px solid rgba(14,116,144,0.1);
}
.nav-logo {
  display: flex;
  align-items: center;
  gap: 10px;
}
.nav-logo-img {
  height: 50px;
  width: auto;
  object-fit: contain;
  mix-blend-mode: lighten;
}
.nav-links {
  display: flex;
  align-items: center;
  gap: 28px;
  list-style: none;
}
.nav-links a {
  font-size: 0.82rem;
  font-weight: 300;
  color: var(--muted);
  transition: color 0.2s;
}
.nav-links a:hover { color: var(--heading); }
.nav-cta {
  display: flex;
  align-items: center;
  gap: 12px;
}
.btn-nav {
  padding: 7px 18px;
  border-radius: 999px;
  font-size: 0.8rem;
  font-weight: 400;
  cursor: pointer;
  transition: all 0.25s;
  font-family: var(--font-body);
}
.btn-nav-solid {
  background: linear-gradient(135deg, var(--accent-dark), var(--accent));
  border: none;
  color: #fff;
  box-shadow: 0 0 16px rgba(34,211,238,0.25);
}
.btn-nav-solid:hover {
  box-shadow: 0 0 28px rgba(34,211,238,0.4);
  transform: translateY(-1px);
}
.nav-hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
  padding: 4px;
}
.nav-hamburger span {
  display: block;
  width: 22px; height: 1.5px;
  background: var(--text);
  border-radius: 2px;
  transition: all 0.3s var(--ease-out);
  transform-origin: center;
}
.nav-hamburger.open span:nth-child(1) { transform: translateY(6.5px) rotate(45deg); }
.nav-hamburger.open span:nth-child(2) { opacity: 0; transform: scaleX(0); }
.nav-hamburger.open span:nth-child(3) { transform: translateY(-6.5px) rotate(-45deg); }
.nav-mobile {
  display: none;
  position: fixed;
  top: 60px; left: 0; right: 0;
  background: rgba(4,47,51,0.97);
  backdrop-filter: blur(20px);
  border-bottom: 1px solid var(--border-s);
  padding: 20px 40px 28px;
  z-index: 899;
}
.nav-mobile.open { display: block; }
.nav-mobile ul { list-style: none; display: flex; flex-direction: column; gap: 16px; }
.nav-mobile ul a { font-size: 0.9rem; color: var(--muted); }
.nav-mobile .btn-nav { display: inline-block; margin-top: 12px; }

@media (max-width: 991px) {
  .main-nav { padding: 0 24px; }
  .nav-links, .nav-cta { display: none; }
  .nav-hamburger { display: flex; }
}
</style>
