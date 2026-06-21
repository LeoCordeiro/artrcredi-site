<template>
  <div>

    <!-- Header -->
    <section style="padding-top:124px;padding-bottom:36px">
      <div class="container" style="max-width:900px">
        <div class="page-anim page-anim-1 eyebrow-row">
          <span class="eyebrow-label">Legal</span>
          <div class="eyebrow-line"></div>
        </div>
        <h1 class="page-anim page-anim-2 page-h1">Política de Privacidade</h1>
        <p class="page-anim page-anim-3 page-sub">Última atualização: Junho de 2026 · Em conformidade com a LGPD</p>
      </div>
    </section>

    <!-- LGPD badge + princípios -->
    <section style="padding-bottom:28px">
      <div class="container" style="max-width:900px">
        <div class="lgpd-banner page-anim page-anim-4">
          <div class="lgpd-badge">
            <svg width="15" height="15" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
            <span>LGPD Compliant</span>
          </div>
          <p class="lgpd-text">Seus dados são tratados com responsabilidade e transparência. Coletamos apenas o necessário para prestar o serviço de representação.</p>
        </div>
      </div>
    </section>

    <!-- Seções de privacidade -->
    <section style="padding-bottom:80px">
      <div class="container" style="max-width:900px">
        <div style="display:flex;flex-direction:column;gap:14px">
          <div v-for="(s, i) in sections" :key="s.title" class="priv-card" v-reveal="{ delay: i * 50 }">
            <div class="priv-icon">
              <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="1.5" stroke-linecap="round" v-html="s.icon"></svg>
            </div>
            <div>
              <h2 class="priv-title">{{ s.title }}</h2>
              <p class="priv-text">{{ s.text }}</p>
            </div>
          </div>
        </div>

        <!-- Direito de acesso -->
        <div class="access-card" v-reveal>
          <h3 style="font-size:14px;font-weight:300;color:var(--heading);margin-bottom:12px">Exercer seus direitos</h3>
          <p style="font-size:13.5px;color:var(--muted);line-height:1.65;margin-bottom:16px">
            Para acessar, corrigir ou solicitar exclusao dos seus dados, entre em contato diretamente pelo e-mail abaixo.
          </p>
          <div style="display:flex;flex-wrap:wrap;gap:10px">
            <a href="mailto:contato@artrcredi.com.br" class="contact-link">
              <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5" stroke-linecap="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
              contato@artrcredi.com.br
            </a>
          </div>
        </div>

        <!-- Empresa -->
        <div class="legal-footer" v-reveal>
          <p>ArtrCredi · CNPJ 67.089.141/0001-01 · Sao Paulo, SP</p>
        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
const sections = [
  {
    title: 'Dados que coletamos',
    text: 'Coletamos apenas dados fornecidos voluntariamente: nome completo, e-mail, telefone, descrição do produto ou negócio e segmento de atuação. Não coletamos dados sem sua ciência.',
    icon: '<path d="M20 21v-2a4 4 0 00-4-4H8a4 4 0 00-4 4v2"/><circle cx="12" cy="7" r="4"/>',
  },
  {
    title: 'Como usamos seus dados',
    text: 'Os dados são usados exclusivamente para: entrar em contato com você, apresentar nossa rede de compradores, formalizar a representação comercial e oferecer suporte contínuo.',
    icon: '<circle cx="12" cy="12" r="3"/><path d="M12 1v4M12 19v4M4.22 4.22l2.83 2.83M16.95 16.95l2.83 2.83M1 12h4M19 12h4M4.22 19.78l2.83-2.83M16.95 7.05l2.83-2.83"/>',
  },
  {
    title: 'Compartilhamento',
    text: 'Não compartilhamos seus dados pessoais com terceiros sem consentimento. Compradores são notificados apenas sobre produtos relevantes, sem acesso aos seus dados completos.',
    icon: '<path d="M4 12v8a2 2 0 002 2h12a2 2 0 002-2v-8"/><polyline points="16 6 12 2 8 6"/><line x1="12" y1="2" x2="12" y2="15"/>',
  },
  {
    title: 'Segurança das informações',
    text: 'Adotamos medidas técnicas e organizacionais para proteger seus dados contra acesso não autorizado, alteração, divulgação ou destruição indevida.',
    icon: '<path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/>',
  },
  {
    title: 'Retenção de dados',
    text: 'Mantemos seus dados pelo tempo necessário para prestar o serviço contratado ou cumprir obrigações legais. Após esse período, os dados são excluídos com segurança.',
    icon: '<circle cx="12" cy="12" r="10"/><polyline points="12 6 12 12 16 14"/>',
  },
  {
    title: 'Seus direitos (LGPD)',
    text: 'Você tem direito de acessar, corrigir, portar ou solicitar a exclusão de seus dados a qualquer momento. Atendemos solicitações em até 15 dias úteis.',
    icon: '<polyline points="9 11 12 14 22 4"/><path d="M21 12v7a2 2 0 01-2 2H5a2 2 0 01-2-2V5a2 2 0 012-2h11"/>',
  },
]
</script>

<style scoped>
.eyebrow-row   { margin-bottom:18px }
.eyebrow-label { font-size:0.6rem;font-weight:500;letter-spacing:.12em;text-transform:uppercase;color:var(--accent-light);display:block;margin-bottom:10px }
.eyebrow-line  { height:1px;background:linear-gradient(to right,var(--border-l),var(--border-s),transparent) }
.page-h1       { font-size:clamp(2rem,5vw,3.6rem);font-weight:200;letter-spacing:-0.03em;line-height:1.08;color:var(--heading);margin-bottom:12px }
.page-sub      { font-size:0.86rem;color:var(--muted);line-height:1.65 }

.lgpd-banner {
  display:flex; align-items:flex-start; gap:18px; flex-wrap:wrap;
  padding:20px 24px; border-radius:14px;
  border:1px solid var(--border-m); background:rgba(14,116,144,0.05);
}
.lgpd-badge {
  display:flex; align-items:center; gap:7px; padding:6px 14px;
  border-radius:9999px; border:1px solid rgba(14,116,144,0.3);
  background:rgba(14,116,144,0.1); font-size:12px; font-weight:500;
  color:var(--accent-light); white-space:nowrap; flex-shrink:0;
}
.lgpd-text { font-size:0.8rem;color:var(--muted);line-height:1.65;flex:1;min-width:200px }

.priv-card {
  display:flex; gap:20px; padding:22px 26px; border-radius:16px;
  border:1px solid var(--border-s); background:var(--bg-1);
  transition:border-color .2s, background .2s;
}
.priv-card:hover { border-color:var(--border-m); background:rgba(14,116,144,0.05); }
.priv-icon {
  width:36px; height:36px; border-radius:10px;
  background:rgba(14,116,144,0.08); border:1px solid rgba(14,116,144,0.2);
  display:flex; align-items:center; justify-content:center; flex-shrink:0;
}
.priv-title { font-size:0.86rem;font-weight:300;color:var(--heading);margin-bottom:8px }
.priv-text  { font-size:0.8rem;color:var(--muted);line-height:1.7 }

.access-card {
  margin-top:28px; padding:24px 28px; border-radius:16px;
  border:1px solid var(--border-s); background:var(--bg-1);
}
.contact-link {
  display:inline-flex; align-items:center; gap:7px; padding:9px 16px;
  border-radius:10px; font-size:0.76rem; color:var(--muted);
  border:1px solid var(--border-s); background:rgba(255,255,255,0.03);
  text-decoration:none; word-break:break-all; transition:color .2s, border-color .2s;
}
.contact-link:hover { color:var(--heading); border-color:var(--border-m); }

.legal-footer {
  margin-top:24px; padding:16px 20px; border-radius:12px;
  border:1px solid var(--border-s); background:var(--bg-1);
  font-size:0.76rem; color:var(--muted);
}

@media(max-width:640px){
  .priv-card { padding:16px;gap:14px }
  .lgpd-banner { gap:12px }
  .access-card { padding:18px }
}
</style>
