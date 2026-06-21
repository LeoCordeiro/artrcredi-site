<template>
  <div>

    <section style="padding-top:124px;padding-bottom:40px">
      <div class="container">
        <div class="page-anim page-anim-1" style="margin-bottom:18px">
          <span class="section-label">Sobre nos</span>
          <div class="page-line"></div>
        </div>
        <h1 class="page-anim page-anim-2 page-h1">A <span class="text-gradient">ArtrCredi</span></h1>
      </div>
    </section>

    <section style="padding-top:16px;padding-bottom:48px;position:relative">
      <div class="container">
        <div class="grid-2" v-reveal>
          <div class="info-board">
            <div class="info-board-header">
              <span class="dot-pulse"></span>
              <span style="font-size:12px;font-weight:500;color:var(--accent-light);letter-spacing:.04em">ArtrCredi</span>
            </div>
            <div class="metrics-grid">
              <div class="metric-cell"><p class="metric-label">Sede</p><p class="metric-value">Sao Paulo, SP</p></div>
              <div class="metric-cell"><p class="metric-label">CNPJ</p><p class="metric-value">67.089.141/0001-01</p></div>
              <div class="metric-cell"><p class="metric-label">Modelo</p><p class="metric-value">Fintech de credito</p></div>
              <div class="metric-cell"><p class="metric-label">Segmento</p><p class="metric-value">Acesso a credito</p></div>
            </div>
            <div style="padding:18px 22px;border-top:1px solid var(--border-s);background:rgba(14,116,144,0.05)">
              <p style="font-size:13px;color:var(--muted);line-height:1.65;font-style:italic">"Conectamos sua empresa as melhores condicoes de credito do mercado. Comparacao automatica, resposta rapida, sem custos."</p>
              <p style="font-size:11.5px;color:var(--accent-light);margin-top:8px;font-weight:500">-- ArtrCredi</p>
            </div>
          </div>

          <div>
            <p style="font-size:0.86rem;color:var(--muted);line-height:1.7;margin-bottom:18px">A ArtrCredi e uma fintech especializada em conectar empresas as melhores condicoes de credito do mercado. Temos acesso a uma rede qualificada de instituicoes financeiras - desde fintechs a fundos de recebiveis - e comparamos automaticamente as melhores propostas para o seu perfil de empresa.</p>
            <p style="font-size:0.84rem;color:var(--muted);line-height:1.7;margin-bottom:28px">O modelo e simples: voce simula seu credito, nos consultamos nossa rede e voce recebe as propostas comparativas em ate 48 horas. <strong style="color:var(--heading);font-weight:400">Sem custos adicionais</strong> -- sua empresa acessa credito de forma rapida e transparente.</p>
            <router-link to="/" class="btn-cta">
              Simular credito
              <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M7 17L17 7m0 0H7m10 0v10"/></svg>
            </router-link>
            <div class="mini-stats" v-reveal="{ delay: 200 }">
              <div class="mini-stat" v-for="s in miniStats" :key="s.value">
                <p class="mini-stat-value">{{ s.value }}</p>
                <p class="mini-stat-label">{{ s.label }}</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section style="padding-top:32px;padding-bottom:80px">
      <div class="container">
        <div v-reveal style="margin-bottom:36px">
          <span class="section-label">Diferenciais</span>
          <div class="page-line" style="margin-bottom:20px"></div>
          <h2>Por que escolher a <span class="text-gradient">ArtrCredi</span></h2>
        </div>
        <div class="diffs-grid stagger-up" ref="diffsGrid">
          <div v-for="d in diffs" :key="d.title" class="diff-card reveal-child">
            <div class="diff-icon">
              <svg width="17" height="17" viewBox="0 0 24 24" fill="none" stroke="var(--accent-light)" stroke-width="1.5" stroke-linecap="round" v-html="d.icon"></svg>
            </div>
            <h3 style="font-size:0.86rem;font-weight:300;color:var(--heading);margin-bottom:7px">{{ d.title }}</h3>
            <p style="font-size:0.78rem;color:var(--muted);line-height:1.6">{{ d.desc }}</p>
          </div>
        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  const io = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) entry.target.classList.add('active')
    })
  }, { threshold: 0.12 })
  document.querySelectorAll('.stagger-up').forEach(el => io.observe(el))
})

const miniStats = [
  { value: '48h', label: 'Resposta maxima' },
  { value: '10+', label: 'Instituicoes parceiras' },
  { value: '0', label: 'Custo para empresa' },
]
const diffs = [
  { title:'Acesso direto ao credito', desc:'Encontramos as melhores ofertas do mercado. Voce aprova e contrata direto com a instituicao parceira.', icon:'<circle cx="12" cy="12" r="10"/><path d="M12 6v6l4 2"/>' },
  { title:'Comparacao automatica', desc:'Nossa rede faz a pesquisa por voce. Em ate 48 horas voce recebe propostas comparativas de multiplas instituicoes.', icon:'<path d="M22 11.08V12a10 10 0 11-5.93-9.14"/><polyline points="22 4 12 14.01 9 11.01"/>' },
  { title:'Sem custo para sua empresa', desc:'Nossa remuneracao vem das instituicoes parceiras. Voce nao paga taxa adicional.', icon:'<path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14 2 14 8 20 8"/><line x1="16" y1="13" x2="8" y2="13"/><line x1="16" y1="17" x2="8" y2="17"/>' },
  { title:'Rede qualificada', desc:'Todos os parceiros sao validados e monitorados. Trabalhamos apenas com instituicoes reconhecidas no mercado.', icon:'<path d="M17 21v-2a4 4 0 00-4-4H5a4 4 0 00-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 00-3-3.87"/><path d="M16 3.13a4 4 0 010 7.75"/>' },
]
</script>

<style scoped>
.page-line { height: 1px; background: linear-gradient(to right, var(--border-l), var(--border-s), transparent); max-width: 460px; margin-top: 14px; }
.page-h1 { font-size: clamp(2.2rem, 5vw, 4rem); font-weight: 200; letter-spacing: -0.03em; line-height: 1.08; color: var(--heading); margin-top: 10px; }

.grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; align-items: start; }
@media(max-width:900px) { .grid-2 { grid-template-columns: 1fr; } }

.info-board { border-radius: 16px; border: 1px solid var(--border-s); overflow: hidden; background: var(--bg-1); }
.info-board-header { padding: 14px 22px; border-bottom: 1px solid var(--border-s); background: rgba(14,116,144,0.06); display: flex; align-items: center; gap: 10px; }
.dot-pulse { width: 7px; height: 7px; border-radius: 50%; background: var(--accent-light); display: inline-block; animation: blink 2s infinite; }
@keyframes blink { 0%,100% { opacity: 1; } 50% { opacity: 0.4; } }
.metrics-grid { display: grid; grid-template-columns: 1fr 1fr; }
.metric-cell { padding: 20px 22px; border-right: 1px solid var(--border-s); border-bottom: 1px solid var(--border-s); }
.metric-cell:nth-child(2n) { border-right: none; }
.metric-cell:nth-child(3), .metric-cell:nth-child(4) { border-bottom: none; }
.metric-label { font-size: 0.6rem; text-transform: uppercase; letter-spacing: 0.12em; color: var(--muted); margin-bottom: 6px; font-weight: 500; }
.metric-value { font-size: 0.86rem; font-weight: 300; color: var(--heading); letter-spacing: -0.01em; }

.btn-cta {
  display: inline-flex; align-items: center; gap: 7px; padding: 11px 22px;
  border-radius: 999px; font-size: 0.82rem; font-weight: 400;
  color: #fff; background: linear-gradient(135deg, var(--accent-dark), var(--accent));
  box-shadow: 0 0 16px rgba(34,211,238,0.25);
  transition: transform 0.2s, box-shadow 0.2s;
}
.btn-cta:hover { transform: translateY(-2px); box-shadow: 0 0 28px rgba(34,211,238,0.4); }

.mini-stats { display: grid; grid-template-columns: repeat(3, 1fr); gap: 12px; margin-top: 24px; }
.mini-stat { padding: 16px; border-radius: 12px; border: 1px solid var(--border-s); background: var(--bg-1); text-align: center; }
.mini-stat-value { font-size: 1.5rem; font-family: var(--font-head); font-weight: 200; letter-spacing: -0.02em; color: var(--accent-light); line-height: 1; }
.mini-stat-label { font-size: 0.6rem; color: var(--muted); margin-top: 5px; }

.diffs-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 14px; }
@media(max-width:600px) { .diffs-grid { grid-template-columns: 1fr; } }

.diff-card {
  padding: 20px; border-radius: 14px; background: var(--bg-1); border: 1px solid var(--border-s);
  transition: all 0.3s var(--ease-out);
}
.diff-card:hover { border-color: var(--border-m); background: rgba(14,116,144,0.05); transform: translateY(-2px); }
.diff-icon {
  width: 36px; height: 36px; border-radius: 9px;
  background: rgba(14,116,144,0.08); border: 1px solid rgba(14,116,144,0.2);
  display: flex; align-items: center; justify-content: center; margin-bottom: 12px;
}
</style>
