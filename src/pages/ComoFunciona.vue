<template>
  <div>

    <section style="padding-top:124px;padding-bottom:40px">
      <div class="container">
        <div class="page-anim page-anim-1" style="margin-bottom:18px">
          <span class="section-label">Processo</span>
          <div class="page-line"></div>
        </div>
        <h1 class="page-anim page-anim-2 page-h1">Como <span class="text-gradient">funciona</span></h1>
      </div>
    </section>

    <section style="padding-top:8px;padding-bottom:48px" v-reveal>
      <div class="container">
        <div class="steps-wrapper">
          <div class="steps-grid stagger-up" ref="stepsGrid">
            <div v-for="(step, i) in steps" :key="step.n" class="step-card reveal-child">
              <div class="step-card-inner">
                <div class="step-num-wrap">
                  <span class="step-num">{{ step.n }}</span>
                </div>
                <h3 class="step-title">{{ step.title }}</h3>
                <p class="step-desc">{{ step.desc }}</p>
                <span class="step-actor" :class="step.actor === 'Voce faz' ? 'actor-primary' : 'actor-muted'">{{ step.actor }}</span>
              </div>
              <div class="step-card-border"></div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section style="padding-top:16px;padding-bottom:80px" v-reveal>
      <div class="container">
        <div class="cta-strip">
          <div class="cta-strip-dots"></div>
          <div style="position:relative;z-index:1;text-align:center">
            <h2 style="font-size:clamp(1.6rem,3vw,2.4rem);font-weight:200;letter-spacing:-0.03em;color:var(--heading);margin-bottom:10px">Pronto para simular seu credito?</h2>
            <p style="font-size:0.84rem;color:var(--muted);max-width:380px;margin:0 auto 24px;line-height:1.65">Comece agora e receba as melhores propostas comparativas em ate 48 horas.</p>
            <router-link to="/" class="btn-cta-primary">
              SIMULAR CREDITO
              <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><path d="M5 12h14m0 0-7-7m7 7-7 7"/></svg>
            </router-link>
          </div>
        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
import { onMounted, ref } from 'vue'

const stepsGrid = ref(null)

onMounted(() => {
  const io = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) entry.target.classList.add('active')
    })
  }, { threshold: 0.12 })
  document.querySelectorAll('.stagger-up').forEach(el => io.observe(el))
})

const steps = [
  { n: 1, title: 'Voce conta o que precisa', desc: 'Simule o tipo de credito, valor desejado e informacoes da sua empresa. Leva apenas 2 minutos.', actor: 'Voce faz' },
  { n: 2, title: 'Comparamos as melhores ofertas', desc: 'Nossas equipes consultam a rede parceira para encontrar as instituicoes mais adequadas para seu perfil.', actor: 'A gente faz' },
  { n: 3, title: 'Voce recebe propostas comparativas', desc: 'Em ate 48 horas, voce recebe as melhores propostas com taxa, prazo e condicoes de cada instituicao.', actor: 'A gente faz' },
  { n: 4, title: 'Escolhe a melhor opcao', desc: 'Compare as propostas e escolha a que melhor se adequa a sua empresa. Formalize direto com a instituicao.', actor: 'Voce faz' },
  { n: 5, title: 'Credito liberado', desc: 'Apos a aprovacao da instituicao parceira, o credito e liberado para a sua empresa.', actor: 'Garantido' },
]
</script>

<style scoped>
.page-line { height: 1px; background: linear-gradient(to right, var(--border-l), var(--border-s), transparent); max-width: 460px; margin-top: 14px; }
.page-h1 { font-size: clamp(2.2rem, 5vw, 4rem); font-weight: 200; letter-spacing: -0.03em; line-height: 1.08; color: var(--heading); margin-top: 10px; }

.steps-wrapper { border-radius: 18px; border: 1px solid var(--border-s); background: var(--bg-1); padding: 28px 32px; }

.steps-grid { display: grid; grid-template-columns: repeat(5, 1fr); gap: 16px; }
@media(max-width:1200px) { .steps-grid { grid-template-columns: repeat(2, 1fr); } }
@media(max-width:600px) { .steps-grid { grid-template-columns: 1fr; } }

.step-card {
  position: relative; border-radius: 16px; overflow: hidden;
  background: rgba(4,47,51,0.6); border: 1px solid var(--border-s);
  transition: transform 0.35s var(--ease-out), box-shadow 0.35s;
}
.step-card:hover { transform: translateY(-4px); box-shadow: 0 12px 40px rgba(14,116,144,0.1); }
.step-card-inner { padding: 22px 20px; display: flex; flex-direction: column; }
.step-card-border {
  position: absolute; inset: 0; border-radius: inherit; padding: 1px; pointer-events: none;
  background: linear-gradient(135deg, rgba(14,116,144,0) 0%, rgba(14,116,144,0.25) 50%, rgba(14,116,144,0) 100%);
  background-size: 300% 300%; animation: border-travel 4s ease-in-out infinite;
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor; mask-composite: exclude;
}
@keyframes border-travel { 0% { background-position: 0% 0%; } 50% { background-position: 100% 100%; } 100% { background-position: 0% 0%; } }

.step-num-wrap { margin-bottom: 14px; }
.step-num {
  display: inline-flex; align-items: center; justify-content: center;
  width: 36px; height: 36px; border-radius: 50%;
  background: var(--accent-light); color: var(--bg-0);
  font-size: 0.86rem; font-weight: 500; font-family: var(--font-head);
}
.step-title { font-size: 0.92rem; font-weight: 300; color: var(--heading); margin-bottom: 8px; letter-spacing: -0.01em; }
.step-desc { font-size: 0.78rem; color: var(--muted); line-height: 1.6; margin-bottom: 14px; flex: 1; }
.step-actor {
  display: inline-flex; padding: 4px 12px; border-radius: 999px;
  font-size: 0.6rem; font-weight: 500; align-self: flex-start;
}
.actor-primary { background: rgba(14,116,144,0.1); color: var(--accent-light); border: 1px solid rgba(14,116,144,0.2); }
.actor-muted { background: rgba(255,255,255,0.03); color: var(--muted); border: 1px solid var(--border-s); }

.cta-strip {
  position: relative; border-radius: 18px; overflow: hidden;
  padding: 44px 32px; text-align: center;
  background: var(--bg-1); border: 1px solid var(--border-s);
}
.cta-strip-dots {
  position: absolute; inset: 0; opacity: 0.6;
  background-image: radial-gradient(circle, rgba(14,116,144,0.05) 1px, transparent 1px);
  background-size: 32px 32px; pointer-events: none;
}

.btn-cta-primary {
  display: inline-flex; align-items: center; gap: 8px; padding: 13px 26px;
  border-radius: 999px; font-size: 0.82rem; font-weight: 400;
  color: #fff; background: linear-gradient(135deg, var(--accent-dark), var(--accent));
  box-shadow: 0 0 28px rgba(34,211,238,0.35);
  transition: transform 0.2s, box-shadow 0.2s, background 0.2s;
}
.btn-cta-primary:hover { background: var(--accent-light); color: var(--bg-0); transform: translateY(-2px); box-shadow: 0 0 40px rgba(34,211,238,0.45); }
</style>
