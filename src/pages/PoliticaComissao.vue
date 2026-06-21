<template>
  <div>

    <section style="padding-top:124px;padding-bottom:36px">
      <div class="container" style="max-width:900px">
        <div class="page-anim page-anim-1 eyebrow-row">
          <span class="eyebrow-label">Legal</span>
          <div class="eyebrow-line"></div>
        </div>
        <h1 class="page-anim page-anim-2 page-h1">Politica de <span class="text-gradient">Remuneracao</span></h1>
        <p class="page-anim page-anim-3 page-sub">Ultima atualizacao: Junho de 2026 · Aplicavel a instituicoes financeiras parceiras</p>
      </div>
    </section>

    <section style="padding-bottom:28px">
      <div class="container" style="max-width:900px">
        <div class="summary-banner page-anim page-anim-4">
          <div class="summary-item">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round"><polyline points="20 6 9 17 4 12"/></svg>
            <span>Remuneracao via instituicoes parceiras</span>
          </div>
          <div class="summary-item">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round"><path d="M14 2H6a2 2 0 00-2 2v16a2 2 0 002 2h12a2 2 0 002-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>
            <span>Contrato formal com cada parceiro</span>
          </div>
          <div class="summary-item">
            <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round"><circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/></svg>
            <span>Sem custo para a empresa solicitante</span>
          </div>
        </div>
      </div>
    </section>

    <section style="padding-bottom:80px">
      <div class="container" style="max-width:900px">
        <div style="display:flex;flex-direction:column;gap:14px">
          <div v-for="(s, i) in sections" :key="s.title" class="pol-card" v-reveal="{ delay: i * 50 }">
            <div class="pol-num">{{ String(i + 1).padStart(2, '0') }}</div>
            <div>
              <h2 class="pol-title">{{ s.title }}</h2>
              <p class="pol-text">{{ s.text }}</p>
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
const sections = [
  {
    title: 'Modelo de operacao',
    text: 'A ArtrCredi atua como facilitadora de acesso a credito, conectando empresas solicitantes a instituicoes financeiras parceiras. A empresa solicitante nao paga nenhuma taxa pela utilizacao do servico.',
  },
  {
    title: 'Remuneracao da ArtrCredi',
    text: 'A ArtrCredi e remunerada pelas instituicoes financeiras parceiras por meio de comissao sobre operacoes de credito originadas atraves da plataforma. O percentual e definido em contrato individual com cada instituicao parceira.',
  },
  {
    title: 'Transparencia',
    text: 'O modelo de remuneracao via instituicoes parceiras garante que a empresa solicitante receba propostas genuinamente comparativas, sem viés comercial. A ArtrCredi nao favorece nenhuma instituicao no processo de comparacao.',
  },
  {
    title: 'Formalizacao',
    text: 'Cada parceria com instituicoes financeiras e formalizada por contrato especifico, com clausulas de compliance, protecao de dados e obrigacoes reciprocas.',
  },
  {
    title: 'Contestacoes',
    text: 'Qualquer divergencia deve ser comunicada formalmente em ate 10 dias uteis. A ArtrCredi se compromete a analisar e responder em ate 5 dias uteis.',
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

.pol-card {
  display:flex; gap:24px; padding:24px 28px; border-radius:16px;
  border:1px solid var(--border-s); background:var(--bg-1);
  transition:border-color .2s, background .2s;
}
.pol-card:hover { border-color:var(--border-m); background:rgba(14,116,144,0.05); }
.pol-num { font-size:0.66rem; font-weight:500; color:var(--accent-light); letter-spacing:.08em; opacity:0.7; flex-shrink:0; padding-top:3px; width:26px; }
.pol-title { font-size:0.86rem; font-weight:300; color:var(--heading); margin-bottom:8px; }
.pol-text { font-size:0.8rem; color:var(--muted); line-height:1.7; }

.legal-footer {
  margin-top:40px; padding:20px 24px; border-radius:14px;
  border:1px solid var(--border-s); background:var(--bg-1);
  display:flex; flex-direction:column; gap:4px;
  font-size:0.78rem; color:var(--muted);
}

@media(max-width:640px){
  .pol-card { padding:18px 16px;gap:14px }
  .summary-banner { flex-direction:column;gap:10px }
}
</style>
