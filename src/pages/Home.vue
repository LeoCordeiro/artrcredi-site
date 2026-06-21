<template>
  <div>

    <!-- HERO -->
    <section id="hero">
      <canvas ref="heroCanvas" id="heroCanvas"></canvas>
      <div class="hero-orb hero-orb-1"></div>
      <div class="hero-orb hero-orb-2"></div>
      <div class="hero-orb hero-orb-3"></div>
      <div class="hero-stars">
        <div class="hero-star hero-star-1"></div>
        <div class="hero-star hero-star-2"></div>
        <div class="hero-star hero-star-3"></div>
        <div class="hero-star hero-star-4"></div>
        <div class="hero-star hero-star-5"></div>
        <div class="hero-star hero-star-6"></div>
      </div>
      <div class="hero-orbits">
        <div class="hero-orbit hero-orbit-1"><div class="hero-orbit-dot"></div></div>
        <div class="hero-orbit hero-orbit-2"><div class="hero-orbit-dot"></div></div>
        <div class="hero-orbit hero-orbit-3"><div class="hero-orbit-dot"></div></div>
      </div>
      <div class="hero-content">
        <h1 class="hero-title">O credito certo para sua empresa,<br/><span class="text-gradient">sem perder tempo comparando.</span></h1>
        <p class="hero-subtitle">Conectamos sua empresa as melhores instituicoes financeiras do mercado -- propostas comparativas em ate 48 horas, sem custo para voce.</p>
        <div class="hero-ctas">
          <a href="#simulacao" class="btn-hero-primary" @click.prevent="scrollToForm">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><line x1="22" y1="2" x2="11" y2="13"/><polygon points="22 2 15 22 11 13 2 9 22 2"/></svg>
            Simular Credito
          </a>
          <router-link to="/como-funciona" class="btn-hero-ghost">
            <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><line x1="8" y1="6" x2="21" y2="6"/><line x1="8" y1="12" x2="21" y2="12"/><line x1="8" y1="18" x2="21" y2="18"/><line x1="3" y1="6" x2="3.01" y2="6"/><line x1="3" y1="12" x2="3.01" y2="12"/><line x1="3" y1="18" x2="3.01" y2="18"/></svg>
            Como Funciona
          </router-link>
        </div>
        <div class="hero-metrics">
          <div class="hero-metric"><span class="hero-metric-val">48h</span><span class="hero-metric-label">Resposta maxima</span></div>
          <div class="hero-metric-sep"></div>
          <div class="hero-metric"><span class="hero-metric-val">R$0</span><span class="hero-metric-label">Custo para empresa</span></div>
          <div class="hero-metric-sep"></div>
          <div class="hero-metric"><span class="hero-metric-val">50+</span><span class="hero-metric-label">Instituicoes parceiras</span></div>
          <div class="hero-metric-sep"></div>
          <div class="hero-metric"><span class="hero-metric-val">20+</span><span class="hero-metric-label">Linhas de credito</span></div>
        </div>
      </div>
    </section>

    <!-- TRUST BAR -->
    <section id="trust">
      <p class="trust-label" style="margin-bottom:12px">Rede de parceiros qualificados</p>
      <p style="max-width:540px;margin:0 auto 28px;color:var(--muted);font-size:0.86rem;line-height:1.7;text-align:center">Trabalhamos com fintechs, bancos digitais e fundos de recebiveis ja validados para garantir as melhores condicoes para sua empresa.</p>
      <div class="logo-bar-wrap">
        <div class="logo-track" ref="logoTrack">
          <span class="logo-item" v-for="(item, idx) in logoItems" :key="idx">{{ item }}</span>
        </div>
      </div>
    </section>

    <!-- POR QUE A ARTRCREDI -->
    <section class="section" id="features">
      <div class="section-sep"></div>
      <div class="container">
        <div class="section-header">
          <span class="section-label">Por que a ArtrCredi</span>
          <h2>Uma rede de instituicoes. Uma proposta<br/><span class="text-gradient">sob medida</span>.</h2>
          <p>Comparamos automaticamente as melhores ofertas de credito para o seu perfil de empresa -- sem que voce precise pesquisar em cada instituicao.</p>
        </div>
        <div class="bento-grid stagger-up" ref="bentoGrid">
          <div v-for="(card, i) in bentoCards" :key="card.title" class="bento-card reveal-child">
            <div class="bc-grid"></div><div class="bc-shimmer"></div>
            <div class="bc-corner bc-corner-tl"></div><div class="bc-corner bc-corner-br"></div>
            <div class="bc-header">
              <div class="bc-live-dot"></div>
              <span class="bc-header-title">{{ card.title }}</span>
              <span class="bc-header-tag">{{ card.tag }}</span>
            </div>
            <div class="bc-body">
              <p>{{ card.desc }}</p>
              <div class="bento-widget" v-if="card.widgetType === 'bars'" ref="barWidget">
                <div class="bw-status"><span class="bw-status-label">Instituicoes consultadas</span><span class="bw-status-val">10+</span></div>
                <div class="widget-bars">
                  <div class="widget-bar" v-for="(h, idx) in barHeights" :key="idx" :style="{ height: h + '%' }"></div>
                </div>
              </div>
              <div class="bento-widget" v-else-if="card.widgetType === 'donut'">
                <div class="bw-status"><span class="bw-status-label">Economia media</span><span class="bw-status-val">100%</span></div>
                <div class="widget-donut">
                  <svg class="donut-svg" viewBox="0 0 72 72"><circle cx="36" cy="36" r="28" fill="none" stroke="rgba(14,116,144,0.1)" stroke-width="8"/><circle cx="36" cy="36" r="28" fill="none" stroke="#0E7490" stroke-width="8" stroke-dasharray="126 176" stroke-dashoffset="44" stroke-linecap="round" opacity="0.9"/><circle cx="36" cy="36" r="28" fill="none" stroke="#22D3EE" stroke-width="8" stroke-dasharray="44 176" stroke-dashoffset="-82" stroke-linecap="round" opacity="0.5"/><text x="36" y="39" text-anchor="middle" fill="#22D3EE" font-family="Outfit" font-size="10" font-weight="300">R$0</text></svg>
                  <div class="donut-labels">
                    <div class="donut-item"><div class="donut-dot" style="background:#0E7490"></div>Remuneracao via parceiros</div>
                    <div class="donut-item"><div class="donut-dot" style="background:#22D3EE"></div>Custo para empresa</div>
                    <div class="donut-item"><div class="donut-dot" style="background:rgba(255,255,255,0.15)"></div>Taxas adicionais</div>
                  </div>
                </div>
              </div>
              <div class="bento-widget" v-else-if="card.widgetType === 'signals'">
                <div class="bw-status"><span class="bw-status-label">Tempo medio de resposta</span><span class="bw-status-val">48h</span></div>
                <div class="widget-signals" ref="signalWidget">
                  <div class="signal-row"><div class="signal-dot"></div>Empresa A -- proposta enviada</div>
                  <div class="signal-row"><div class="signal-dot hot"></div>Empresa B -- aguardando analise</div>
                  <div class="signal-row"><div class="signal-dot"></div>Empresa C -- credito aprovado</div>
                  <div class="signal-row"><div class="signal-dot warn"></div>Empresa D -- prazo de resposta hoje</div>
                  <div class="signal-row"><div class="signal-dot"></div>Empresa E -- proposta comparativa pronta</div>
                </div>
              </div>
              <div class="bento-widget" v-else-if="card.widgetType === 'badges'">
                <div class="bw-status"><span class="bw-status-label">Parceiros na rede</span><span class="bw-status-val">10+</span></div>
                <div class="widget-integrations">
                  <span class="int-badge">Fintechs</span>
                  <span class="int-badge">Bancos Digitais</span>
                  <span class="int-badge">FIDCs</span>
                  <span class="int-badge">Fundos de Recebiveis</span>
                  <span class="int-badge">Factorings</span>
                  <span class="int-badge">Securitizadoras</span>
                  <span class="int-badge">ESCs</span>
                  <span class="int-badge" style="color:var(--accent-light);border-style:dashed">+</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- PRODUTOS -->
    <section class="section section-alt" id="showcase">
      <div class="section-sep"></div>
      <div class="container showcase-container">
        <div class="section-header">
          <span class="section-label">Nossos Produtos</span>
          <h2>O credito certo para cada momento<br/><span class="text-gradient">da sua empresa</span></h2>
          <p>Conhca as linhas de credito disponiveis atraves da ArtrCredi.</p>
        </div>
        <div class="products-grid stagger-up" ref="productsGrid">
          <div v-for="prod in products" :key="prod.title" class="reveal-child" style="border-top:1px solid var(--border-s);padding-top:20px">
            <h3 style="margin-bottom:8px">{{ prod.title }}</h3>
            <p>{{ prod.desc }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- SIMULACAO -->
    <section class="section" id="simulacao">
      <div class="section-sep"></div>
      <div class="container">
        <div class="section-header">
          <span class="section-label">Simulacao</span>
          <h2>Simule seu credito <span class="text-gradient">agora</span>.</h2>
          <p>Preencha os dados abaixo e receba propostas comparativas das melhores instituicoes em ate 48 horas.</p>
        </div>

        <div class="sim-card">
          <div v-if="simSubmitted" class="sim-success">
            <div class="sim-success-icon">
              <svg width="28" height="28" viewBox="0 0 24 24" fill="none" stroke="#22D3EE" stroke-width="2.5" stroke-linecap="round"><polyline points="20 6 9 17 4 12"/></svg>
            </div>
            <h3 style="font-size:1.15rem;font-weight:300;color:var(--heading);margin-bottom:8px">Simulacao recebida!</h3>
            <p style="font-size:0.84rem;color:var(--muted);max-width:400px;margin:0 auto 24px;line-height:1.65">Em ate 48 horas voce recebe as melhores propostas comparativas para a sua empresa.</p>
            <button type="button" @click="resetForm" class="sim-btn-reset">Fazer nova simulacao</button>
          </div>

          <div v-else>
            <div class="sim-form-grid">
              <div class="sim-field">
                <label class="field-label">Tipo de credito desejado <span class="req">*</span></label>
                <select v-model="simForm.tipoCredito" class="field-input">
                  <option value="">Selecione...</option>
                  <option>Antecipacao de recebiveis</option>
                  <option>Capital de giro</option>
                  <option>Credito para expansao</option>
                  <option>Desconto de duplicatas</option>
                  <option>Nao sei, quero orientacao</option>
                </select>
              </div>
              <div class="sim-field">
                <label class="field-label">Valor desejado <span class="req">*</span></label>
                <select v-model="simForm.valor" class="field-input">
                  <option value="">Selecione...</option>
                  <option>Ate R$ 50 mil</option>
                  <option>R$ 50 a 150 mil</option>
                  <option>R$ 150 a 500 mil</option>
                  <option>Acima de R$ 500 mil</option>
                </select>
              </div>
              <div class="sim-field">
                <label class="field-label">Faturamento mensal <span class="req">*</span></label>
                <select v-model="simForm.faturamento" class="field-input">
                  <option value="">Selecione...</option>
                  <option>Ate R$ 50 mil</option>
                  <option>R$ 50 a 200 mil</option>
                  <option>R$ 200 a 1 milhao</option>
                  <option>Acima de R$ 1 milhao</option>
                </select>
              </div>
              <div class="sim-field">
                <label class="field-label">Tempo de CNPJ <span class="req">*</span></label>
                <select v-model="simForm.tempoCnpj" class="field-input">
                  <option value="">Selecione...</option>
                  <option>Menos de 1 ano</option>
                  <option>1 a 3 anos</option>
                  <option>Mais de 3 anos</option>
                </select>
              </div>
              <div class="sim-field">
                <label class="field-label">Nome completo <span class="req">*</span></label>
                <input v-model="simForm.nome" type="text" placeholder="Seu nome" class="field-input" />
              </div>
              <div class="sim-field">
                <label class="field-label">Empresa <span class="req">*</span></label>
                <input v-model="simForm.empresa" type="text" placeholder="Nome da empresa" class="field-input" />
              </div>
              <div class="sim-field">
                <label class="field-label">CNPJ <span class="req">*</span></label>
                <input :value="simForm.cnpj" @input="maskCNPJ" type="text" placeholder="00.000.000/0000-00" class="field-input" maxlength="18" />
              </div>
              <div class="sim-field">
                <label class="field-label">WhatsApp <span class="req">*</span></label>
                <input :value="simForm.whatsapp" @input="maskPhone" type="text" placeholder="(11) 9XXXX-XXXX" class="field-input" maxlength="15" />
              </div>
              <div class="sim-field sim-field-full">
                <label class="field-label">E-mail corporativo <span class="req">*</span></label>
                <input v-model="simForm.email" type="email" placeholder="email@empresa.com.br" class="field-input" />
              </div>
            </div>
            <div style="text-align:center;margin-top:28px">
              <button type="button" @click="submitSim" class="submit-btn" :disabled="!isFormValid">
                SIMULAR CREDITO
                <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M5 12h14m0 0-7-7m7 7-7 7"/></svg>
              </button>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- COMO FUNCIONA -->
    <section id="how" ref="howSection">
      <div class="section-sep"></div>
      <div class="how-sticky" ref="howSticky">
        <div class="how-bg-orb how-bg-orb-1" ref="howOrb1"></div>
        <div class="how-bg-orb how-bg-orb-2" ref="howOrb2"></div>
        <div class="how-bg-dots"></div>
        <div class="how-mobile-header">
          <span class="section-label">Como Funciona</span>
          <h2>Do briefing ao credito -- <span class="text-gradient">sem complicacao</span></h2>
        </div>
        <div class="how-inner">
          <div class="how-left">
            <span class="section-label" style="opacity:1">Como Funciona</span>
            <div class="how-step-counter">
              <div class="how-big-num" ref="howBigNum">01</div>
              <div class="how-big-num-fill" ref="howBigNumFill" :class="{ visible: howFillVisible }">01</div>
            </div>
            <div class="how-left-label" :class="{ visible: howLabelVisible }" ref="howLabel">Passo 1 de 5</div>
            <div class="how-left-title" :class="{ visible: howTitleVisible }" ref="howTitle">Voce conta o que precisa</div>
            <div class="how-progress"><div class="how-progress-fill" ref="howProgressFill" :style="{ width: howProgress + '%' }"></div></div>
            <div class="how-dots">
              <div v-for="(s, i) in howSteps" :key="i" class="how-dot" :class="{ active: currentHowStep === i }"></div>
            </div>
          </div>
          <div class="how-right">
            <div v-for="(panel, i) in howSteps" :key="i"
              class="how-panel"
              :class="{ active: currentHowStep === i, behind: i < currentHowStep }"
              :data-panel="i">
              <div class="hp-grid"></div><div class="hp-shimmer"></div>
              <div class="hp-corner hp-corner-tl"></div><div class="hp-corner hp-corner-tr"></div><div class="hp-corner hp-corner-br"></div>
              <div class="hp-header">
                <div class="hp-live-dot"></div>
                <span class="hp-header-title">{{ panel.panelTitle }}</span>
                <span class="hp-header-badge">{{ panel.badge }}</span>
              </div>
              <div class="hp-body">
                <p>{{ panel.desc }}</p>
                <div class="how-panel-widget">
                  <div class="hw-status-row">
                    <span class="hw-status-label">{{ panel.widgetLabel }}</span>
                    <span class="hw-status-val">{{ panel.widgetVal }}</span>
                  </div>
                  <div class="hw-actions">
                    <div v-for="(action, j) in panel.actions" :key="j" class="hw-action-row">
                      <div class="hw-action-dot" :class="j < 2 ? 'live' : 'done'"></div>
                      <span class="hw-action-text">{{ action }}</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- CTA FINAL -->
    <section id="cta-section">
      <div class="container" style="position:relative;z-index:1">
        <div>
          <span class="section-label">Simule agora</span>
          <h2 class="cta-title">Sua empresa merece a melhor condicao<br/><span class="text-gradient">de credito do mercado</span>.</h2>
          <p class="cta-sub">Simule agora e descubra em ate 48 horas qual instituicao oferece a melhor proposta para o seu momento.</p>
          <div class="cta-buttons">
            <a href="#simulacao" class="btn-cta-primary" @click.prevent="scrollToForm">
              <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round"><path d="M22 11.08V12a10 10 0 11-5.93-9.14"/><polyline points="22 4 12 14.01 9 11.01"/></svg>
              SIMULAR CREDITO AGORA
            </a>
          </div>
          <p style="margin-top:24px;color:var(--muted);font-size:0.8rem;letter-spacing:0.02em">Resposta em ate 48 horas &middot; Sem custo para sua empresa &middot; Rede de parceiros qualificados</p>
        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
import { ref, reactive, computed, onMounted, onUnmounted, nextTick } from 'vue'

const heroCanvas = ref(null)
const howSection = ref(null)
const howBigNum = ref(null)
const howBigNumFill = ref(null)
const howLabel = ref(null)
const howTitle = ref(null)
const howProgressFill = ref(null)
const howOrb1 = ref(null)
const howOrb2 = ref(null)
const bentoGrid = ref(null)
const productsGrid = ref(null)

const currentHowStep = ref(0)
const howProgress = ref(0)
const howFillVisible = ref(true)
const howLabelVisible = ref(true)
const howTitleVisible = ref(true)

const barHeights = ref([55, 69, 84, 65, 48, 52, 41, 57])

const simSubmitted = ref(false)
const simForm = reactive({
  tipoCredito: '', valor: '', faturamento: '', tempoCnpj: '',
  nome: '', empresa: '', cnpj: '', whatsapp: '', email: '',
})

const isFormValid = computed(() =>
  simForm.tipoCredito && simForm.valor && simForm.faturamento &&
  simForm.tempoCnpj && simForm.nome && simForm.empresa &&
  simForm.cnpj && simForm.whatsapp && simForm.email
)

function scrollToForm() {
  const el = document.getElementById('simulacao')
  if (el) el.scrollIntoView({ behavior: 'smooth' })
}

function maskPhone(e) {
  let v = e.target.value.replace(/\D/g, '')
  if (v.length > 11) v = v.substring(0, 11)
  let m = ''
  if (v.length > 0) m = '(' + v.substring(0, 2)
  if (v.length > 2) m += ') ' + v.substring(2, 7)
  if (v.length > 7) m += '-' + v.substring(7)
  simForm.whatsapp = m
}

function maskCNPJ(e) {
  let v = e.target.value.replace(/\D/g, '')
  if (v.length > 14) v = v.substring(0, 14)
  let m = ''
  if (v.length > 0) m = v.substring(0, 2)
  if (v.length > 2) m += '.' + v.substring(2, 5)
  if (v.length > 5) m += '.' + v.substring(5, 8)
  if (v.length > 8) m += '/' + v.substring(8, 12)
  if (v.length > 12) m += '-' + v.substring(12)
  simForm.cnpj = m
}

function submitSim() {
  const msg = `Ola! Quero simular um credito pela ArtrCredi.\n\nTipo de credito: ${simForm.tipoCredito}\nValor desejado: ${simForm.valor}\nFaturamento mensal: ${simForm.faturamento}\nTempo de CNPJ: ${simForm.tempoCnpj}\n\nNome: ${simForm.nome}\nEmpresa: ${simForm.empresa}\nCNPJ: ${simForm.cnpj}\nWhatsApp: ${simForm.whatsapp}\nE-mail: ${simForm.email}`
  window.open(`https://wa.me/5511920158232?text=${encodeURIComponent(msg)}`, '_blank')
  simSubmitted.value = true
}

function resetForm() {
  simSubmitted.value = false
  Object.assign(simForm, { tipoCredito: '', valor: '', faturamento: '', tempoCnpj: '', nome: '', empresa: '', cnpj: '', whatsapp: '', email: '' })
}

const logoItems = [
  'Fintechs', 'Bancos Digitais', 'FIDCs', 'Factorings', 'Securitizadoras', 'ESCs',
  'Fundos de Recebiveis', 'Cooperativas', 'Bancos Comerciais', 'Credito Direto',
  'Fintechs', 'Bancos Digitais', 'FIDCs', 'Factorings', 'Securitizadoras', 'ESCs',
  'Fundos de Recebiveis', 'Cooperativas', 'Bancos Comerciais', 'Credito Direto',
]

const bentoCards = [
  {
    title: 'Comparacao Automatica',
    tag: 'Exclusivo',
    desc: 'Em vez de voce bater de porta em porta em bancos e fintechs, nos comparamos as melhores ofertas disponiveis para o seu perfil de empresa.',
    widgetType: 'bars',
  },
  {
    title: 'Sem Custo',
    tag: 'Gratuito',
    desc: 'Nossa remuneracao vem das instituicoes financeiras parceiras -- voce nao paga nenhuma taxa adicional por usar a ArtrCredi.',
    widgetType: 'donut',
  },
  {
    title: 'Resposta em 48h',
    tag: '48h',
    desc: 'Receba propostas comparativas com taxa, prazo e valor de cada instituicao parceira em ate 48 horas uteis.',
    widgetType: 'signals',
  },
  {
    title: 'Parceiros Qualificados',
    tag: 'Qualidade',
    desc: 'Trabalhamos com fintechs, bancos digitais e fundos de recebiveis ja validados -- sem letras miudas ou condicoes escondidas.',
    widgetType: 'badges',
  },
]

const products = [
  { title: 'Antecipacao de Recebiveis', desc: 'Antecipe valores de cartao, boletos ou duplicatas a receber e tenha capital de giro rapido sem comprometer sua linha de credito bancaria.' },
  { title: 'Capital de Giro', desc: 'Linhas de credito para financiar a operacao do dia a dia -- estoque, fornecedores e folha de pagamento em momentos de sazonalidade.' },
  { title: 'Credito para Expansao', desc: 'Financiamento para abrir filiais, comprar equipamentos ou ampliar a operacao, com valores e prazos maiores.' },
  { title: 'Desconto de Duplicatas', desc: 'Venda antecipada de duplicatas a receber de clientes -- alternativa agil para empresas que vendem a prazo para outras empresas.' },
]

const howSteps = [
  {
    num: '01', label: 'Passo 1 de 5', title: 'Voce conta o que precisa',
    panelTitle: 'Briefing', badge: 'Passo 1',
    desc: 'Valor, finalidade e perfil da sua empresa. Pode ser pelo formulario do site ou pelo WhatsApp.',
    widgetLabel: 'Campos do briefing', widgetVal: 'Simples e rapido',
    actions: ['Tipo de credito informado', 'Valor desejado definido', 'Dados da empresa preenchidos', 'Simulacao enviada'],
  },
  {
    num: '02', label: 'Passo 2 de 5', title: 'Comparamos as melhores ofertas',
    panelTitle: 'Comparacao', badge: 'Ate 48h',
    desc: 'Consultamos nossa rede de parceiros e comparamos as melhores ofertas disponiveis para o seu perfil.',
    widgetLabel: 'Instituicoes consultadas', widgetVal: '10+',
    actions: ['Rede de parceiros acionada', 'Propostas recebidas', 'Comparativo montado', 'Melhor oferta destacada'],
  },
  {
    num: '03', label: 'Passo 3 de 5', title: 'Voce recebe propostas comparativas',
    panelTitle: 'Propostas', badge: 'Comparativo',
    desc: 'Em ate 48 horas, voce recebe as propostas com taxa, prazo e valor de cada instituicao parceira.',
    widgetLabel: 'Status', widgetVal: 'Propostas prontas',
    actions: ['Taxas comparadas', 'Prazos alinhados', 'Valores confirmados', 'Relatorio enviado'],
  },
  {
    num: '04', label: 'Passo 4 de 5', title: 'Escolhe a melhor opcao',
    panelTitle: 'Escolha', badge: 'Decisao',
    desc: 'Compare as propostas e escolha a que melhor se adequa a sua empresa. Formalize direto com a instituicao.',
    widgetLabel: 'Formalizacao', widgetVal: 'Direto com a instituicao',
    actions: ['Proposta escolhida', 'Documentacao enviada', 'Contrato formalizado', 'Aprovacao confirmada'],
  },
  {
    num: '05', label: 'Passo 5 de 5', title: 'Credito liberado na sua empresa',
    panelTitle: 'Liberacao', badge: 'Concluido',
    desc: 'Apos a aprovacao da instituicao parceira, o credito e liberado diretamente para a sua empresa.',
    widgetLabel: 'Status do credito', widgetVal: 'Liberado',
    actions: ['Aprovacao confirmada', 'Credito liberado', 'Valor depositado', 'Operacao concluida'],
  },
]

let barAnimInterval = null
let glCleanup = null

function animateBars() {
  barHeights.value = barHeights.value.map(() => Math.floor(Math.random() * 60) + 30)
}

function onHowScroll() {
  if (!howSection.value) return
  const rect = howSection.value.getBoundingClientRect()
  const sectionH = howSection.value.offsetHeight
  const viewH = window.innerHeight
  const scrolled = -rect.top
  const scrollRange = sectionH - viewH
  if (scrollRange <= 0) return
  const progress = Math.max(0, Math.min(1, scrolled / scrollRange))
  howProgress.value = progress * 100

  const totalSteps = howSteps.length
  const step = Math.min(totalSteps - 1, Math.floor(progress * totalSteps))
  if (step !== currentHowStep.value) {
    currentHowStep.value = step
    const s = howSteps[step]
    if (howBigNum.value) howBigNum.value.textContent = s.num
    if (howBigNumFill.value) howBigNumFill.value.textContent = s.num

    howFillVisible.value = false
    howLabelVisible.value = false
    howTitleVisible.value = false
    setTimeout(() => {
      if (howLabel.value) howLabel.value.textContent = s.label
      if (howTitle.value) howTitle.value.textContent = s.title
      howFillVisible.value = true
      howLabelVisible.value = true
      howTitleVisible.value = true
    }, 120)

    if (howOrb1.value && howOrb2.value) {
      const ox = step * 15
      const oy = step * 10
      howOrb1.value.style.transform = `translate(${ox}px, ${-oy}px)`
      howOrb2.value.style.transform = `translate(${-ox}px, ${oy}px)`
    }
  }
}

function initWebGL() {
  const canvas = heroCanvas.value
  if (!canvas) return
  const gl = canvas.getContext('webgl', { alpha: true, antialias: false, premultipliedAlpha: false })
  if (!gl) return

  let mx = 0.5, my = 0.5, tmx = 0.5, tmy = 0.5
  let rafId = null

  function resize() {
    const dpr = Math.min(window.devicePixelRatio, 1.5)
    const W = canvas.parentElement.clientWidth
    const H = canvas.parentElement.clientHeight
    canvas.width = W * dpr
    canvas.height = H * dpr
    canvas.style.width = W + 'px'
    canvas.style.height = H + 'px'
    gl.viewport(0, 0, canvas.width, canvas.height)
  }

  const VERT = 'attribute vec2 p;void main(){gl_Position=vec4(p,0,1);}'
  const FRAG = `
precision highp float;
uniform float u_t;
uniform vec2 u_r;
uniform vec2 u_m;
vec3 mod289(vec3 x){return x-floor(x*(1./289.))*289.;}
vec4 mod289(vec4 x){return x-floor(x*(1./289.))*289.;}
vec4 perm(vec4 x){return mod289(((x*34.)+1.)*x);}
float snoise(vec3 v){
  const vec2 C=vec2(1./6.,1./3.);
  const vec4 D=vec4(0,.5,1,2);
  vec3 i=floor(v+dot(v,C.yyy));
  vec3 x0=v-i+dot(i,C.xxx);
  vec3 g=step(x0.yzx,x0.xyz);
  vec3 l=1.-g;
  vec3 i1=min(g,l.zxy);
  vec3 i2=max(g,l.zxy);
  vec3 x1=x0-i1+C.xxx;
  vec3 x2=x0-i2+C.yyy;
  vec3 x3=x0-D.yyy;
  i=mod289(i);
  vec4 p=perm(perm(perm(i.z+vec4(0,i1.z,i2.z,1))+i.y+vec4(0,i1.y,i2.y,1))+i.x+vec4(0,i1.x,i2.x,1));
  float n_=1./7.;
  vec3 ns=n_*D.wyz-D.xzx;
  vec4 j=p-49.*floor(p*ns.z*ns.z);
  vec4 x_=floor(j*ns.z);
  vec4 y_=floor(j-7.*x_);
  vec4 x=x_*ns.x+ns.yyyy;
  vec4 y=y_*ns.x+ns.yyyy;
  vec4 h=1.-abs(x)-abs(y);
  vec4 b0=vec4(x.xy,y.xy);
  vec4 b1=vec4(x.zw,y.zw);
  vec4 s0=floor(b0)*2.+1.;
  vec4 s1=floor(b1)*2.+1.;
  vec4 sh=-step(h,vec4(0));
  vec4 a0=b0.xzyw+s0.xzyw*sh.xxyy;
  vec4 a1=b1.xzyw+s1.xzyw*sh.zzww;
  vec3 p0=vec3(a0.xy,h.x);
  vec3 p1=vec3(a0.zw,h.y);
  vec3 p2=vec3(a1.xy,h.z);
  vec3 p3=vec3(a1.zw,h.w);
  vec4 norm=1.79284291400159-.85373472095314*vec4(dot(p0,p0),dot(p1,p1),dot(p2,p2),dot(p3,p3));
  p0*=norm.x;p1*=norm.y;p2*=norm.z;p3*=norm.w;
  vec4 m=max(.6-vec4(dot(x0,x0),dot(x1,x1),dot(x2,x2),dot(x3,x3)),0.);
  m=m*m;
  return 42.*dot(m*m,vec4(dot(p0,x0),dot(p1,x1),dot(p2,x2),dot(p3,x3)));
}
float fbm(vec3 p){
  float v=0.,a=.5;
  for(int i=0;i<5;i++){
    v+=a*snoise(p);
    p*=2.1;
    a*=.48;
  }
  return v;
}
void main(){
  vec2 uv=(gl_FragCoord.xy)/u_r;
  vec2 p=uv*2.-1.;
  p.x*=u_r.x/u_r.y;
  vec2 mp=u_m*2.-1.;
  mp.x*=u_r.x/u_r.y;
  float md=length(p-mp);
  float mInfluence=smoothstep(1.5,0.,md)*0.6;
  p+=normalize(p-mp+.001)*mInfluence*0.45;
  float t=u_t*0.25;
  float n1=fbm(vec3(p*1.2+vec2(t*0.4,t*0.3),t*0.2));
  float n2=fbm(vec3(p*2.5+vec2(-t*0.6,t*0.5),t*0.35+5.));
  float n3=fbm(vec3(p*1.8+mp*0.5,t*0.5+10.));
  float wave=sin(length(p)*4.0-t*2.0)*0.5+0.5;
  float n4=fbm(vec3(p*0.8+vec2(t*0.2,-t*0.15),t*0.1+20.))*wave;
  float n=n1*0.55+n2*0.3+n3*mInfluence*1.5+n4*0.35;
  vec3 c1=vec3(0.02,0.29,0.35);
  vec3 c2=vec3(0.05,0.46,0.57);
  vec3 c3=vec3(0.13,0.83,0.93);
  float intensity=smoothstep(-0.2,0.8,n);
  vec3 col=mix(c1,c2,intensity);
  col=mix(col,c3,smoothstep(0.5,1.0,intensity)*0.6);
  float glow=exp(-md*md*2.5)*0.5;
  col+=c3*glow;
  float vig=1.-smoothstep(0.4,1.5,length(uv*2.-1.));
  float alpha=intensity*0.32*vig+glow*0.7*vig;
  float centerGlow=exp(-dot(p,p)*0.6)*0.12;
  alpha+=centerGlow;
  gl_FragColor=vec4(col,alpha);
}`

  function compile(type, src) {
    const s = gl.createShader(type)
    gl.shaderSource(s, src)
    gl.compileShader(s)
    return s
  }
  const prog = gl.createProgram()
  gl.attachShader(prog, compile(gl.VERTEX_SHADER, VERT))
  gl.attachShader(prog, compile(gl.FRAGMENT_SHADER, FRAG))
  gl.linkProgram(prog)
  gl.useProgram(prog)

  const buf = gl.createBuffer()
  gl.bindBuffer(gl.ARRAY_BUFFER, buf)
  gl.bufferData(gl.ARRAY_BUFFER, new Float32Array([-1,-1,1,-1,-1,1,1,1]), gl.STATIC_DRAW)
  const pLoc = gl.getAttribLocation(prog, 'p')
  gl.enableVertexAttribArray(pLoc)
  gl.vertexAttribPointer(pLoc, 2, gl.FLOAT, false, 0, 0)

  const u_t = gl.getUniformLocation(prog, 'u_t')
  const u_r = gl.getUniformLocation(prog, 'u_r')
  const u_m = gl.getUniformLocation(prog, 'u_m')

  canvas.parentElement.addEventListener('mousemove', e => {
    const r = canvas.getBoundingClientRect()
    tmx = (e.clientX - r.left) / r.width
    tmy = 1.0 - (e.clientY - r.top) / r.height
  })

  resize()
  window.addEventListener('resize', resize)

  function frame(t) {
    rafId = requestAnimationFrame(frame)
    mx += (tmx - mx) * 0.12
    my += (tmy - my) * 0.12
    gl.clearColor(0, 0, 0, 0)
    gl.clear(gl.COLOR_BUFFER_BIT)
    gl.enable(gl.BLEND)
    gl.blendFunc(gl.SRC_ALPHA, gl.ONE)
    gl.useProgram(prog)
    gl.uniform1f(u_t, t * 0.001)
    gl.uniform2f(u_r, canvas.width, canvas.height)
    gl.uniform2f(u_m, mx, my)
    gl.drawArrays(gl.TRIANGLE_STRIP, 0, 4)
  }
  requestAnimationFrame(frame)

  glCleanup = () => {
    if (rafId) cancelAnimationFrame(rafId)
    window.removeEventListener('resize', resize)
  }
}

onMounted(() => {
  initWebGL()
  barAnimInterval = setInterval(animateBars, 2200)
  window.addEventListener('scroll', onHowScroll, { passive: true })
  onHowScroll()

  nextTick(() => {
    const io = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('active')
          entry.target.classList.add('is-visible')
        }
      })
    }, { threshold: 0.08, rootMargin: '0px 0px -20px 0px' })

    document.querySelectorAll('.reveal, .stagger-up, .section-header').forEach(el => io.observe(el))
  })
})

onUnmounted(() => {
  if (barAnimInterval) clearInterval(barAnimInterval)
  if (glCleanup) glCleanup()
  window.removeEventListener('scroll', onHowScroll)
})
</script>

<style scoped>
/* HERO */
#hero {
  position: relative;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  text-align: center;
  overflow: hidden;
  padding: 0 24px;
}
#heroCanvas {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  z-index: 0;
}
.hero-orb {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  pointer-events: none;
  z-index: 1;
  animation: hero-orb-drift 12s ease-in-out infinite alternate;
}
.hero-orb-1 {
  width: 600px; height: 600px;
  background: radial-gradient(circle, rgba(14,116,144,0.13), transparent 70%);
  top: 15%; left: 20%;
}
.hero-orb-2 {
  width: 500px; height: 500px;
  background: radial-gradient(circle, rgba(34,211,238,0.1), transparent 70%);
  bottom: 10%; right: 15%;
  animation-delay: -4s; animation-duration: 15s;
}
.hero-orb-3 {
  width: 350px; height: 350px;
  background: radial-gradient(circle, rgba(11,93,115,0.12), transparent 70%);
  top: 50%; left: 55%;
  animation-delay: -8s; animation-duration: 18s;
}
@keyframes hero-orb-drift {
  0% { transform: translate(0, 0) scale(1); }
  33% { transform: translate(30px, -20px) scale(1.05); }
  66% { transform: translate(-20px, 15px) scale(0.97); }
  100% { transform: translate(15px, -10px) scale(1.02); }
}
#hero::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 250px;
  background: linear-gradient(to bottom, transparent, var(--bg-0));
  pointer-events: none;
  z-index: 3;
}
#hero::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 120px;
  background: linear-gradient(to top, transparent, rgba(4,47,51,0.4));
  pointer-events: none;
  z-index: 3;
}
.hero-content { position: relative; z-index: 4; max-width: 780px; }
.hero-stars { position: absolute; inset: 0; pointer-events: none; z-index: 1; overflow: hidden; }
.hero-star {
  position: absolute;
  width: 80px; height: 1px;
  background: linear-gradient(90deg, transparent, rgba(34,211,238,0.6));
  border-radius: 1px; opacity: 0;
  transform: rotate(45deg);
  animation: hero-star-shoot linear infinite;
}
@keyframes hero-star-shoot {
  0% { translate: 0 0; opacity: 0; }
  5% { opacity: 1; }
  60% { opacity: 0.6; }
  100% { translate: 420px 420px; opacity: 0; }
}
.hero-star-1 { top: 8%; left: 5%; animation-duration: 3.5s; width: 90px; }
.hero-star-2 { top: 20%; right: 25%; animation-duration: 4.2s; animation-delay: 1.2s; width: 60px; }
.hero-star-3 { top: 45%; left: 10%; animation-duration: 3.8s; animation-delay: 2.8s; width: 70px; }
.hero-star-4 { top: 5%; left: 40%; animation-duration: 4.5s; animation-delay: 0.7s; width: 50px; }
.hero-star-5 { top: 30%; right: 15%; animation-duration: 3.2s; animation-delay: 2.0s; width: 85px; }
.hero-star-6 { top: 60%; left: 25%; animation-duration: 5s; animation-delay: 3.5s; width: 55px; }
.hero-orbits { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); pointer-events: none; z-index: 1; }
.hero-orbit { position: absolute; border-radius: 50%; border: 1px solid rgba(14,116,144,0.06); top: 50%; left: 50%; transform: translate(-50%, -50%); }
.hero-orbit-1 { width: 400px; height: 400px; }
.hero-orbit-2 { width: 650px; height: 650px; border-style: dashed; border-color: rgba(14,116,144,0.04); }
.hero-orbit-3 { width: 900px; height: 900px; }
.hero-orbit-dot { position: absolute; width: 6px; height: 6px; border-radius: 50%; background: var(--accent-light); box-shadow: 0 0 10px rgba(34,211,238,0.6); }
.hero-orbit-1 .hero-orbit-dot { top: -3px; left: 50%; transform: translateX(-50%); animation: orbit-spin-1 12s linear infinite; transform-origin: 50% calc(200px + 3px); }
.hero-orbit-2 .hero-orbit-dot { top: -3px; left: 50%; transform: translateX(-50%); animation: orbit-spin-2 20s linear infinite; transform-origin: 50% calc(325px + 3px); width: 4px; height: 4px; opacity: 0.6; }
.hero-orbit-3 .hero-orbit-dot { top: -3px; left: 50%; transform: translateX(-50%); animation: orbit-spin-3 30s linear infinite; transform-origin: 50% calc(450px + 3px); width: 3px; height: 3px; opacity: 0.4; }
@keyframes orbit-spin-1 { to { transform: translateX(-50%) rotate(360deg); } }
@keyframes orbit-spin-2 { to { transform: translateX(-50%) rotate(-360deg); } }
@keyframes orbit-spin-3 { to { transform: translateX(-50%) rotate(360deg); } }
.hero-metrics { display: flex; align-items: center; justify-content: center; gap: 32px; margin-top: 48px; flex-wrap: wrap; }
.hero-metric { display: flex; align-items: center; gap: 8px; }
.hero-metric-val { font-family: var(--font-head); font-size: 1.05rem; font-weight: 300; color: var(--accent-light); letter-spacing: -0.02em; }
.hero-metric-label { font-size: 0.62rem; color: var(--muted); letter-spacing: 0.03em; }
.hero-metric-sep { width: 1px; height: 24px; background: linear-gradient(to bottom, transparent, rgba(14,116,144,0.2), transparent); }
.hero-eyebrow {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(14,116,144,0.08); border: 1px solid rgba(14,116,144,0.2);
  border-radius: 999px; padding: 5px 14px;
  font-size: 0.68rem; font-weight: 500; letter-spacing: 0.1em; text-transform: uppercase;
  color: var(--accent-light); margin-bottom: 24px;
}
.hero-title { font-size: clamp(2.6rem, 5.5vw, 4rem); font-weight: 200; letter-spacing: -0.04em; line-height: 1.1; margin-bottom: 20px; color: var(--heading); }
.hero-subtitle { font-size: 0.92rem; font-weight: 300; color: var(--muted); max-width: 520px; margin: 0 auto 36px; line-height: 1.7; }
.hero-ctas { display: flex; align-items: center; justify-content: center; gap: 16px; flex-wrap: wrap; }
.btn-hero-primary {
  position: relative; display: inline-flex; align-items: center; gap: 8px;
  padding: 14px 28px; font-family: var(--font-body); font-size: 0.86rem; font-weight: 400;
  color: var(--heading); background: rgba(14,116,144,0.1);
  backdrop-filter: blur(10px); border-radius: 12px; cursor: pointer; border: none; z-index: 0;
  transition: transform 0.25s var(--ease-out), background 0.25s; overflow: hidden;
}
.btn-hero-primary::before {
  content: ''; position: absolute; inset: -2px; border-radius: 14px;
  background: conic-gradient(from var(--angle, 0deg), var(--accent-light), var(--accent), var(--accent-dark), transparent, var(--accent-dark), var(--accent), var(--accent-light));
  z-index: -2; animation: spin-border 3s linear infinite;
}
.btn-hero-primary::after {
  content: ''; position: absolute; inset: 1px; border-radius: 11px;
  background: rgba(4,47,51,0.9); z-index: -1;
}
.btn-hero-primary:hover {
  transform: translateY(-2px); background: rgba(14,116,144,0.15);
  box-shadow: 0 12px 36px rgba(34,211,238,0.25);
}
@property --angle { syntax: '<angle>'; initial-value: 0deg; inherits: false; }
@keyframes spin-border { to { --angle: 360deg; } }
.btn-hero-ghost {
  display: inline-flex; align-items: center; gap: 8px;
  padding: 14px 24px; font-family: var(--font-body); font-size: 0.86rem; font-weight: 400;
  color: var(--muted); background: transparent; border: 1px solid rgba(255,255,255,0.1);
  border-radius: 12px; cursor: pointer; transition: all 0.25s;
}
.btn-hero-ghost:hover { color: var(--heading); border-color: var(--border-m); background: rgba(255,255,255,0.03); }

/* TRUST */
#trust {
  position: relative; padding: 48px 0;
  background: var(--bg-1); border-top: 1px solid var(--border-s); border-bottom: 1px solid var(--border-s);
  overflow: hidden;
}
#trust::before {
  content: ''; position: absolute; inset: 0;
  background: radial-gradient(ellipse 60% 100% at 50% 50%, rgba(14,116,144,0.04), transparent);
  pointer-events: none;
}
.trust-label { text-align: center; font-size: 0.72rem; color: var(--muted); letter-spacing: 0.08em; text-transform: uppercase; margin-bottom: 28px; }
.logo-bar-wrap { position: relative; overflow: hidden; }
.logo-bar-wrap::before, .logo-bar-wrap::after {
  content: ''; position: absolute; top: 0; bottom: 0; width: 120px; z-index: 2; pointer-events: none;
}
.logo-bar-wrap::before { left: 0; background: linear-gradient(to right, var(--bg-1), transparent); }
.logo-bar-wrap::after { right: 0; background: linear-gradient(to left, var(--bg-1), transparent); }
.logo-track {
  display: flex; align-items: center; gap: 0; width: max-content;
  animation: logo-scroll 28s linear infinite;
}
.logo-track:hover { animation-play-state: paused; }
.logo-item {
  display: flex; align-items: center; padding: 0 36px; white-space: nowrap;
  font-family: var(--font-head); font-size: 0.96rem; font-weight: 300; letter-spacing: -0.01em;
  color: rgba(255,255,255,0.25); transition: color 0.3s;
  border-right: 1px solid rgba(255,255,255,0.06);
}
.logo-track:hover .logo-item:hover { color: rgba(255,255,255,0.55); }
@keyframes logo-scroll { from { transform: translateX(0); } to { transform: translateX(-50%); } }

/* FEATURES BENTO GRID */
#features { background: var(--bg-1); }
#features::before {
  content: ''; position: absolute; inset: 0;
  background: radial-gradient(ellipse 50% 60% at 80% 20%, rgba(14,116,144,0.05), transparent), radial-gradient(ellipse 40% 50% at 10% 80%, rgba(11,93,115,0.04), transparent);
  pointer-events: none;
}
#features::after {
  content: ''; position: absolute; inset: 0;
  background-image: radial-gradient(circle, rgba(14,116,144,0.05) 1px, transparent 1px);
  background-size: 24px 24px; pointer-events: none; opacity: 0.6; z-index: 0;
}
.bento-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 16px; }
.bento-card {
  position: relative; background: rgba(4,47,51,0.8); border: none; border-radius: 16px; padding: 0;
  backdrop-filter: blur(16px); box-shadow: 0 8px 40px rgba(0,0,0,0.3), 0 0 0 1px rgba(14,116,144,0.04);
  transition: transform 0.35s var(--ease-out), box-shadow 0.35s; overflow: hidden; z-index: 1;
}
.bento-card::before {
  content: ''; position: absolute; inset: 0; border-radius: 16px; padding: 1px;
  background: linear-gradient(160deg, rgba(14,116,144,0.45), rgba(14,116,144,0.06) 40%, transparent 60%, rgba(34,211,238,0.25));
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor; mask-composite: exclude; pointer-events: none; z-index: 3; transition: opacity 0.35s;
}
.bento-card::after {
  content: ''; position: absolute; top: -1px; left: 15%; right: 15%; height: 60px;
  background: radial-gradient(ellipse 100% 100% at 50% 0%, rgba(14,116,144,0.1), transparent);
  pointer-events: none; z-index: 1;
}
.bento-card:hover { transform: translateY(-3px); box-shadow: 0 20px 60px rgba(14,116,144,0.1), 0 0 0 1px rgba(14,116,144,0.12); }
.bc-grid {
  position: absolute; inset: 0;
  background-image: linear-gradient(rgba(14,116,144,0.025) 1px, transparent 1px), linear-gradient(90deg, rgba(14,116,144,0.025) 1px, transparent 1px);
  background-size: 20px 20px; pointer-events: none; z-index: 0;
  mask-image: linear-gradient(to bottom, black 0%, transparent 50%); border-radius: 16px;
}
.bc-shimmer {
  position: absolute; top: 0; left: 0; width: 40%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(14,116,144,0.05), rgba(255,255,255,0.02), transparent);
  pointer-events: none; z-index: 2; transform: translateX(-100%) skewX(-15deg);
}
.bento-card:hover .bc-shimmer { animation: bc-shimmer-sweep 0.8s var(--ease-out) forwards; }
@keyframes bc-shimmer-sweep { to { transform: translateX(350%) skewX(-15deg); } }
.bc-corner { position: absolute; width: 12px; height: 12px; z-index: 4; pointer-events: none; }
.bc-corner::before, .bc-corner::after { content: ''; position: absolute; background: rgba(14,116,144,0.3); }
.bc-corner::before { width: 12px; height: 1px; }
.bc-corner::after { width: 1px; height: 12px; }
.bc-corner-tl { top: 8px; left: 8px; }
.bc-corner-tl::before { top: 0; left: 0; }
.bc-corner-tl::after { top: 0; left: 0; }
.bc-corner-br { bottom: 8px; right: 8px; }
.bc-corner-br::before { bottom: 0; right: 0; left: auto; top: auto; }
.bc-corner-br::after { bottom: 0; right: 0; left: auto; top: auto; }
.bc-header {
  display: flex; align-items: center; gap: 8px;
  padding: 14px 20px 12px; border-bottom: 1px solid rgba(14,116,144,0.06);
  position: relative; z-index: 2;
}
.bc-live-dot { width: 5px; height: 5px; border-radius: 50%; background: var(--accent-light); box-shadow: 0 0 6px var(--accent-light); animation: pulse-dot 2s ease-in-out infinite; }
.bc-header-title { font-family: var(--font-head); font-size: 0.88rem; font-weight: 300; color: var(--heading); letter-spacing: -0.01em; }
.bc-header-tag { margin-left: auto; font-size: 0.5rem; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; color: var(--accent-light); background: rgba(14,116,144,0.08); border: 1px solid rgba(14,116,144,0.15); border-radius: 999px; padding: 2px 7px; }
.bc-body { padding: 14px 20px 18px; position: relative; z-index: 2; }
.bento-card p { font-size: 0.74rem; color: var(--muted); line-height: 1.65; margin-bottom: 14px; }
.bento-widget { border-radius: 8px; background: rgba(0,0,0,0.25); border: 1px solid rgba(14,116,144,0.08); overflow: hidden; height: 140px; position: relative; display: flex; flex-direction: column; }
.bento-widget::after { content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 30px; background: linear-gradient(to bottom, transparent, rgba(0,0,0,0.5)); pointer-events: none; z-index: 2; }
.bw-status { display: flex; align-items: center; justify-content: space-between; padding: 6px 10px; border-bottom: 1px solid rgba(14,116,144,0.05); font-size: 0.52rem; letter-spacing: 0.06em; text-transform: uppercase; flex-shrink: 0; }
.bw-status-label { color: var(--muted); }
.bw-status-val { color: var(--accent-light); font-weight: 500; }
.widget-bars { display: flex; align-items: flex-end; gap: 5px; padding: 8px 10px 0; flex: 1; min-height: 0; }
.widget-bar { flex: 1; border-radius: 3px 3px 0 0; background: linear-gradient(to top, var(--accent-dark), var(--accent-light)); opacity: 0.85; transition: height 1.2s var(--ease-out); min-height: 8px; }
.widget-donut { display: flex; align-items: center; justify-content: center; flex: 1; min-height: 0; gap: 14px; padding: 12px; }
.donut-svg { width: 72px; height: 72px; flex-shrink: 0; }
.donut-labels { display: flex; flex-direction: column; gap: 5px; }
.donut-item { display: flex; align-items: center; gap: 6px; font-size: 0.65rem; color: var(--muted); }
.donut-dot { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }
.widget-signals { display: flex; flex-direction: column; gap: 4px; padding: 8px 10px; overflow: hidden; }
.signal-row { display: flex; align-items: center; gap: 7px; font-size: 0.62rem; color: var(--muted); }
.signal-dot { width: 5px; height: 5px; border-radius: 50%; background: var(--accent-light); flex-shrink: 0; animation: pulse-dot 2s ease-in-out infinite; }
.signal-dot.warn { background: #F59E0B; }
.signal-dot.hot { background: #EF4444; }
@keyframes pulse-dot { 0%,100% { opacity:1; transform:scale(1); } 50% { opacity:0.5; transform:scale(0.7); } }
.widget-integrations { display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: 8px; padding: 12px; }
.int-badge { background: rgba(255,255,255,0.04); border: 1px solid rgba(255,255,255,0.08); border-radius: 6px; padding: 4px 8px; font-size: 0.58rem; color: rgba(255,255,255,0.4); letter-spacing: 0.04em; }

/* SHOWCASE / PRODUCTS */
#showcase { background: var(--bg-1); padding: 64px 0; }
#showcase::before {
  content: ''; position: absolute; inset: 0;
  background: radial-gradient(ellipse 70% 50% at 50% 30%, rgba(14,116,144,0.06), transparent);
  pointer-events: none;
}
.products-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 40px; }

/* SIMULACAO */
.sim-card {
  max-width: 800px; margin: 0 auto;
  border-radius: 18px; border: 1px solid var(--border-s);
  background: var(--bg-1); padding: 32px;
}
.sim-form-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 18px; }
.sim-field { display: flex; flex-direction: column; gap: 6px; }
.sim-field-full { grid-column: 1 / -1; }
.field-label { display: block; font-size: 0.74rem; font-weight: 400; color: var(--muted); margin-bottom: 4px; letter-spacing: 0.01em; }
.field-label .req { color: var(--accent-light); }
.field-input {
  display: block; width: 100%; padding: 11px 14px; border-radius: 10px;
  background: rgba(255,255,255,0.03); border: 1px solid var(--border-s);
  color: var(--text); font-size: 0.84rem; font-family: var(--font-body);
  outline: none; transition: border-color 0.2s, background 0.2s;
  -webkit-appearance: none; appearance: none;
}
.field-input::placeholder { color: rgba(255,255,255,0.25); }
.field-input:focus { border-color: var(--accent-light); background: rgba(14,116,144,0.06); }
.field-input option { background: var(--bg-1); color: var(--text); }
.submit-btn {
  display: inline-flex; align-items: center; justify-content: center; gap: 8px;
  padding: 14px 32px; border-radius: 999px; font-size: 0.84rem; font-weight: 400;
  font-family: var(--font-body); color: #fff; border: none; cursor: pointer;
  background: linear-gradient(135deg, var(--accent-dark), var(--accent));
  box-shadow: 0 0 16px rgba(34,211,238,0.25);
  transition: transform 0.25s var(--ease-out), box-shadow 0.25s;
}
.submit-btn:hover:not(:disabled) { box-shadow: 0 0 28px rgba(34,211,238,0.4); transform: translateY(-1px); }
.submit-btn:disabled { opacity: 0.5; cursor: not-allowed; }
.sim-success { padding: 48px; text-align: center; }
.sim-success-icon {
  width: 60px; height: 60px; border-radius: 16px;
  background: rgba(14,116,144,0.1); border: 1px solid var(--border-m);
  display: flex; align-items: center; justify-content: center; margin: 0 auto 20px;
}
.sim-btn-reset {
  padding: 10px 24px; font-size: 0.84rem; font-weight: 400;
  color: var(--text); background: transparent; border: 1px solid var(--border-m);
  border-radius: 999px; cursor: pointer; transition: all 0.25s;
}
.sim-btn-reset:hover { border-color: var(--accent-light); color: var(--accent-light); }

/* HOW IT WORKS */
#how { position: relative; height: 520vh; padding: 0; overflow: visible; background: var(--bg-0); }
#how .section-sep { position: sticky; top: 0; }
.how-sticky { position: sticky; top: 0; height: 100vh; display: flex; align-items: center; justify-content: center; overflow: hidden; perspective: 1200px; }
.how-bg-orb { position: absolute; border-radius: 50%; filter: blur(80px); pointer-events: none; transition: transform 1.4s var(--ease-out), opacity 1.4s; will-change: transform, opacity; }
.how-bg-orb-1 { width: 500px; height: 500px; background: radial-gradient(circle, rgba(14,116,144,0.1), transparent 70%); top: 10%; left: -5%; }
.how-bg-orb-2 { width: 400px; height: 400px; background: radial-gradient(circle, rgba(34,211,238,0.08), transparent 70%); bottom: 5%; right: -5%; }
.how-bg-dots { position: absolute; inset: 0; background-image: radial-gradient(circle, rgba(14,116,144,0.05) 1px, transparent 1px); background-size: 32px 32px; pointer-events: none; mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 20%, transparent 80%); opacity: 0.6; }
.how-inner { position: relative; z-index: 2; width: 100%; max-width: 1100px; padding: 0 40px; display: grid; grid-template-columns: 1fr 1fr; gap: 64px; align-items: center; }
.how-left { display: flex; flex-direction: column; align-items: flex-start; gap: 24px; }
.how-step-counter { position: relative; width: 100%; }
.how-big-num {
  font-family: var(--font-head); font-size: clamp(8rem, 18vw, 14rem); font-weight: 200; line-height: 0.85; letter-spacing: -0.06em;
  color: transparent; -webkit-text-stroke: 1px rgba(14,116,144,0.12); position: relative;
  transition: all 0.8s var(--ease-out); user-select: none;
}
.how-big-num-fill {
  position: absolute; inset: 0; font-family: var(--font-head); font-size: clamp(8rem, 18vw, 14rem); font-weight: 200; line-height: 0.85; letter-spacing: -0.06em;
  background: linear-gradient(135deg, var(--accent-light) 0%, var(--accent) 50%, var(--accent-dark) 100%);
  -webkit-background-clip: text; -webkit-text-fill-color: transparent; background-clip: text;
  opacity: 0; transform: scaleX(0); transform-origin: left center;
  transition: opacity 0.6s var(--ease-out), transform 1s var(--ease-out);
}
.how-big-num-fill.visible { opacity: 1; transform: scaleX(1); }
.how-left-label { font-size: 0.68rem; font-weight: 500; letter-spacing: 0.12em; text-transform: uppercase; color: var(--accent-light); margin-bottom: 4px; opacity: 0; transform: translateY(8px); transition: all 0.6s var(--ease-out); }
.how-left-label.visible { opacity: 1; transform: translateY(0); }
.how-left-title { font-family: var(--font-head); font-size: clamp(1.8rem, 3vw, 2.4rem); font-weight: 200; color: var(--heading); letter-spacing: -0.03em; line-height: 1.15; opacity: 0; transform: translateY(16px); transition: all 0.7s var(--ease-out) 0.08s; }
.how-left-title.visible { opacity: 1; transform: translateY(0); }
.how-progress { width: 100%; height: 2px; background: rgba(14,116,144,0.1); border-radius: 2px; overflow: hidden; margin-top: 8px; }
.how-progress-fill { height: 100%; background: linear-gradient(90deg, var(--accent-light), var(--accent)); box-shadow: 0 0 8px rgba(34,211,238,0.4); border-radius: 2px; transition: width 0.15s linear; }
.how-dots { display: flex; gap: 10px; margin-top: 4px; }
.how-dot { width: 8px; height: 8px; border-radius: 50%; background: rgba(14,116,144,0.12); border: 1px solid rgba(14,116,144,0.2); transition: all 0.5s var(--ease-out); cursor: default; }
.how-dot.active { background: var(--accent-light); box-shadow: 0 0 12px rgba(34,211,238,0.5); border-color: var(--accent-light); transform: scale(1.3); }
.how-right { position: relative; height: 400px; perspective: 900px; }
.how-panel {
  position: absolute; inset: 0; background: rgba(4,47,51,0.85); border: none; border-radius: 20px; padding: 0;
  backdrop-filter: blur(20px); box-shadow: 0 20px 80px rgba(0,0,0,0.4), 0 0 0 1px rgba(14,116,144,0.06);
  display: flex; flex-direction: column; opacity: 0; transform: translateZ(-120px) rotateY(8deg) scale(0.92);
  transition: all 0.8s var(--ease-out); pointer-events: none; will-change: transform, opacity; overflow: hidden;
}
.how-panel::before {
  content: ''; position: absolute; inset: 0; border-radius: 20px; padding: 1px;
  background: linear-gradient(160deg, rgba(14,116,144,0.5), rgba(14,116,144,0.08) 40%, transparent 60%, rgba(34,211,238,0.3));
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor; mask-composite: exclude; pointer-events: none; z-index: 3;
}
.how-panel::after {
  content: ''; position: absolute; top: -1px; left: 10%; right: 10%; height: 80px;
  background: radial-gradient(ellipse 100% 100% at 50% 0%, rgba(14,116,144,0.12), transparent);
  pointer-events: none; z-index: 1;
}
.how-panel.active { opacity: 1; transform: translateZ(0) rotateY(0deg) scale(1); pointer-events: auto; }
.how-panel.behind { opacity: 0.12; transform: translateZ(-200px) rotateY(-4deg) scale(0.85); filter: blur(3px); }
.hp-grid {
  position: absolute; inset: 0;
  background-image: linear-gradient(rgba(14,116,144,0.03) 1px, transparent 1px), linear-gradient(90deg, rgba(14,116,144,0.03) 1px, transparent 1px);
  background-size: 24px 24px; pointer-events: none; z-index: 0;
  mask-image: linear-gradient(to bottom, black 0%, transparent 60%); border-radius: 20px;
}
.hp-shimmer {
  position: absolute; top: 0; left: 0; width: 40%; height: 100%;
  background: linear-gradient(90deg, transparent, rgba(14,116,144,0.06), rgba(255,255,255,0.03), transparent);
  pointer-events: none; z-index: 2; transform: translateX(-100%) skewX(-15deg);
}
.how-panel.active .hp-shimmer { animation: panel-shimmer 2.5s var(--ease-out) 0.3s 1; }
@keyframes panel-shimmer { 0% { transform: translateX(-100%) skewX(-15deg); } 100% { transform: translateX(300%) skewX(-15deg); } }
.hp-corner { position: absolute; width: 16px; height: 16px; z-index: 4; pointer-events: none; }
.hp-corner::before, .hp-corner::after { content: ''; position: absolute; background: rgba(14,116,144,0.35); }
.hp-corner::before { width: 16px; height: 1px; }
.hp-corner::after { width: 1px; height: 16px; }
.hp-corner-tl { top: 10px; left: 10px; }
.hp-corner-tl::before { top: 0; left: 0; }
.hp-corner-tl::after { top: 0; left: 0; }
.hp-corner-tr { top: 10px; right: 10px; }
.hp-corner-tr::before { top: 0; right: 0; left: auto; }
.hp-corner-tr::after { top: 0; right: 0; left: auto; }
.hp-corner-br { bottom: 10px; right: 10px; }
.hp-corner-br::before { bottom: 0; right: 0; left: auto; top: auto; }
.hp-corner-br::after { bottom: 0; right: 0; left: auto; top: auto; }
.hp-header { display: flex; align-items: center; gap: 10px; padding: 16px 24px 14px; border-bottom: 1px solid rgba(14,116,144,0.08); position: relative; z-index: 2; }
.hp-live-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--accent-light); box-shadow: 0 0 8px var(--accent-light); animation: pulse-dot 2s ease-in-out infinite; }
.hp-header-title { font-family: var(--font-head); font-size: 0.92rem; font-weight: 300; color: var(--heading); letter-spacing: -0.01em; }
.hp-header-badge { margin-left: auto; font-size: 0.55rem; font-weight: 500; letter-spacing: 0.08em; text-transform: uppercase; color: var(--accent-light); background: rgba(14,116,144,0.1); border: 1px solid rgba(14,116,144,0.2); border-radius: 999px; padding: 2px 8px; }
.hp-body { padding: 20px 24px; position: relative; z-index: 2; flex: 1; display: flex; flex-direction: column; }
.hp-body p { font-size: 0.78rem; color: var(--muted); line-height: 1.7; margin-bottom: 18px; }
.how-panel-widget { background: rgba(0,0,0,0.25); border: 1px solid rgba(14,116,144,0.08); border-radius: 10px; padding: 14px; position: relative; overflow: hidden; flex: 1; }
.how-panel-widget::after { content: ''; position: absolute; bottom: 0; left: 0; right: 0; height: 24px; background: linear-gradient(to bottom, transparent, rgba(0,0,0,0.4)); pointer-events: none; }
.hw-status-row { display: flex; align-items: center; justify-content: space-between; margin-bottom: 10px; padding-bottom: 8px; border-bottom: 1px solid rgba(14,116,144,0.06); }
.hw-status-label { font-size: 0.58rem; color: var(--muted); text-transform: uppercase; letter-spacing: 0.08em; }
.hw-status-val { font-size: 0.62rem; color: var(--accent-light); font-weight: 500; font-family: var(--font-head); }
.hw-actions { display: flex; flex-direction: column; gap: 8px; }
.hw-action-row {
  display: flex; align-items: center; gap: 10px; padding: 8px 10px;
  background: rgba(14,116,144,0.04); border-radius: 8px; border: 1px solid rgba(14,116,144,0.08);
  font-size: 0.62rem; color: rgba(255,255,255,0.55); position: relative; overflow: hidden;
  transition: border-color 0.3s, background 0.3s;
}
.hw-action-row:first-child { border-color: rgba(14,116,144,0.2); background: rgba(14,116,144,0.06); }
.hw-action-row::before { content: ''; position: absolute; left: 0; top: 20%; bottom: 20%; width: 2px; border-radius: 1px; background: var(--accent-light); opacity: 0; transition: opacity 0.3s; }
.hw-action-row:first-child::before { opacity: 1; }
.hw-action-dot { width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }
.hw-action-dot.live { background: var(--accent-light); box-shadow: 0 0 6px var(--accent-light); animation: pulse-dot 2s ease-in-out infinite; }
.hw-action-dot.done { background: rgba(255,255,255,0.12); }
.hw-action-text { flex: 1; }

/* CTA */
#cta-section {
  background: var(--bg-0); padding: 80px 0; text-align: center; position: relative; overflow: hidden;
}
#cta-section::before {
  content: ''; position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%);
  width: 800px; height: 400px; border-radius: 50%;
  background: radial-gradient(ellipse, rgba(14,116,144,0.1), transparent 70%);
  filter: blur(80px); pointer-events: none;
}
#cta-section::after {
  content: ''; position: absolute; inset: 0;
  background-image: radial-gradient(circle, rgba(14,116,144,0.07) 1px, transparent 1px);
  background-size: 24px 24px; pointer-events: none;
  mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black, transparent);
}
.cta-title { font-size: clamp(2rem, 4vw, 2.8rem); font-weight: 200; letter-spacing: -0.04em; margin-bottom: 16px; }
.cta-sub { font-size: 0.9rem; color: var(--muted); max-width: 440px; margin: 0 auto 36px; }
.cta-buttons { display: flex; align-items: center; justify-content: center; gap: 14px; flex-wrap: wrap; }
.btn-cta-primary {
  position: relative; display: inline-flex; align-items: center; gap: 8px;
  padding: 13px 26px; font-family: var(--font-body); font-size: 0.86rem; font-weight: 400;
  color: #fff; background: linear-gradient(135deg, var(--accent-dark), var(--accent));
  border: none; border-radius: 10px; cursor: pointer;
  box-shadow: 0 0 28px rgba(34,211,238,0.3); transition: all 0.25s;
}
.btn-cta-primary:hover { box-shadow: 0 0 44px rgba(34,211,238,0.45); transform: translateY(-2px); }

/* MOBILE HEADER */
.how-mobile-header { display: none; }

/* RESPONSIVE */
@media (max-width: 991px) {
  .bento-grid { grid-template-columns: 1fr 1fr; }
  #how { height: auto !important; padding: 80px 0 !important; overflow: hidden !important; }
  .how-sticky { position: relative !important; height: auto !important; perspective: none !important; overflow: visible !important; }
  .how-bg-orb, .how-bg-dots { display: none; }
  .how-inner { grid-template-columns: 1fr; gap: 40px; padding: 0 24px; }
  .how-left { display: none; }
  .how-mobile-header { display: block !important; text-align: center; margin-bottom: 32px; }
  .how-right { height: auto !important; perspective: none !important; }
  .how-panel { position: relative !important; opacity: 1 !important; transform: none !important; filter: none !important; pointer-events: auto !important; margin-bottom: 16px; inset: auto !important; }
  .how-panel.behind { opacity: 1 !important; transform: none !important; filter: none !important; }
  .how-dots, .how-progress, .how-step-counter { display: none; }
  .hero-orbits { display: none; }
  .products-grid { grid-template-columns: 1fr; }
  .sim-form-grid { grid-template-columns: 1fr; }
}
@media (max-width: 574px) {
  .bento-grid { grid-template-columns: 1fr; }
  .hero-ctas { flex-direction: column; align-items: stretch; }
  .hero-metrics { gap: 16px; flex-direction: column; align-items: center; }
  .hero-metric-sep { display: none; }
  .btn-hero-primary, .btn-hero-ghost { justify-content: center; }
  .sim-card { padding: 24px 16px; }
}
</style>
