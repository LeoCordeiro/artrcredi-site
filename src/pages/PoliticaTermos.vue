<template>
  <div>

    <section style="padding-top:124px;padding-bottom:36px">
      <div class="container" style="max-width:900px">
        <div class="page-anim page-anim-1 eyebrow-row">
          <span class="eyebrow-label">Legal</span>
          <div class="eyebrow-line"></div>
        </div>
        <h1 class="page-anim page-anim-2 page-h1">Termos de Uso</h1>
        <p class="page-anim page-anim-3 page-sub">Ultima atualizacao: Junho de 2026</p>
      </div>
    </section>

    <section style="padding-bottom:28px">
      <div class="container" style="max-width:900px">
        <div class="summary-banner page-anim page-anim-4">
          <div class="summary-item">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round"><polyline points="20 6 9 17 4 12"/></svg>
            <span>Sem custo para a empresa</span>
          </div>
          <div class="summary-item">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
            <span>Propostas comparativas formalizadas</span>
          </div>
          <div class="summary-item">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
            <span>Resposta em ate 48 horas</span>
          </div>
        </div>
      </div>
    </section>

    <section style="padding-bottom:80px">
      <div class="container" style="max-width:900px">
        <div style="display:flex;flex-direction:column;gap:14px">
          <div v-for="(t, i) in terms" :key="t.title" class="term-card" v-reveal="{ delay: i * 50 }">
            <div class="term-num">{{ String(i + 1).padStart(2, '0') }}</div>
            <div class="term-body">
              <h2 class="term-title">{{ t.title }}</h2>
              <p class="term-text">{{ t.text }}</p>
            </div>
          </div>
        </div>

        <div class="legal-footer" v-reveal>
          <p>ArtrCredi · CNPJ 67.089.141/0001-01 · Sao Paulo, SP</p>
          <p>contato@artrcredi.com.br</p>
          <p style="margin-top:4px;font-size:0.72rem;color:var(--muted)">Foro competente: Comarca de Sao Paulo, SP</p>
        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
const terms = [
  {
    title: 'Sobre o servico',
    text: 'A ArtrCredi (Artr Solucoes Administrativas e Financeiras LTDA, CNPJ 67.089.141/0001-01) oferece servico de acesso facilitado a credito, conectando empresas a instituicoes financeiras parceiras para obtencao de propostas comparativas.',
  },
  {
    title: 'Escopo do servico',
    text: 'Nossos servicos incluem: comparacao automatica de ofertas de credito, envio de propostas comparativas, orientacao sobre linhas de credito e conexao direta com instituicoes financeiras parceiras.',
  },
  {
    title: 'Modelo de operacao',
    text: 'A empresa preenche a simulacao de credito informando tipo, valor desejado e dados da empresa. A ArtrCredi consulta sua rede de parceiros e envia propostas comparativas em ate 48 horas uteis. Nao ha custo para a empresa solicitante.',
  },
  {
    title: 'Responsabilidades',
    text: 'A ArtrCredi atua como facilitadora de acesso a credito. As instituicoes financeiras parceiras sao responsaveis pela analise, aprovacao e liberacao do credito. A ArtrCredi se responsabiliza pela qualidade da comparacao e do atendimento.',
  },
  {
    title: 'Remuneracao',
    text: 'A ArtrCredi e remunerada pelas instituicoes financeiras parceiras. A empresa solicitante nao paga nenhuma taxa adicional pelo servico de comparacao e acesso a credito.',
  },
  {
    title: 'Protecao de dados',
    text: 'Os dados fornecidos sao utilizados exclusivamente para fins de simulacao e comparacao de credito. Consulte nossa Politica de Privacidade para mais detalhes sobre o tratamento de dados.',
  },
  {
    title: 'Foro competente',
    text: 'Aplica-se exclusivamente a legislacao brasileira. O foro competente para resolucao de disputas e a Comarca de Sao Paulo, Estado de Sao Paulo.',
  },
]
</script>

<style scoped>
.eyebrow-row   { margin-bottom:18px }
.eyebrow-label { font-size:0.6rem;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--accent-light);display:block;margin-bottom:10px }
.eyebrow-line  { height:1px;background:linear-gradient(to right,var(--border-l),var(--border-s),transparent) }
.page-h1       { font-size:clamp(2rem,5vw,3.6rem);font-weight:200;letter-spacing:-0.03em;line-height:1.08;color:var(--heading);margin-bottom:12px }
.page-sub      { font-size:0.86rem;color:var(--muted);line-height:1.65 }

.summary-banner {
  display:flex; flex-wrap:wrap; gap:12px; padding:18px 24px;
  border-radius:14px; border:1px solid var(--border-s); background:var(--bg-1);
}
.summary-item { display:flex; align-items:center; gap:8px; font-size:0.78rem; color:var(--muted); }

.term-card {
  display:flex; gap:24px; padding:24px 28px; border-radius:16px;
  border:1px solid var(--border-s); background:var(--bg-1);
  transition:border-color .2s, background .2s;
}
.term-card:hover { border-color:var(--border-m); background:rgba(14,116,144,0.05); }
.term-num { font-size:0.66rem; font-weight:500; color:var(--accent-light); letter-spacing:.08em; opacity:0.7; flex-shrink:0; padding-top:3px; width:26px; }
.term-title { font-size:0.86rem; font-weight:300; color:var(--heading); margin-bottom:8px; }
.term-text { font-size:0.8rem; color:var(--muted); line-height:1.7; }

.legal-footer {
  margin-top:40px; padding:20px 24px; border-radius:14px;
  border:1px solid var(--border-s); background:var(--bg-1);
  display:flex; flex-direction:column; gap:4px;
  font-size:0.78rem; color:var(--muted);
}

@media(max-width:640px){
  .term-card { padding:18px 16px;gap:14px }
  .summary-banner { flex-direction:column;gap:10px }
}
</style>
