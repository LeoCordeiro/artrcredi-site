<template>
  <div>

    <section style="padding-top:124px;padding-bottom:36px">
      <div class="container">
        <div class="page-anim page-anim-1" style="margin-bottom:20px">
          <span class="section-label">Contato</span>
          <div style="height:1px;background:linear-gradient(to right,var(--border-l),var(--border-s),transparent)"></div>
        </div>
        <h1 class="page-anim page-anim-2" style="font-size:clamp(2.2rem,5vw,4.2rem);font-weight:200;letter-spacing:-0.03em;line-height:1.08;color:var(--heading)">
          Fale com a<br /><span class="text-gradient">ArtrCredi</span>
        </h1>
        <p class="page-anim page-anim-3" style="margin-top:16px;max-width:460px;font-size:0.9rem;color:var(--muted);line-height:1.65">
          Simule seu credito ou tire suas duvidas. Atendemos empresas de todos os portes em todo o Brasil.
        </p>
      </div>
    </section>

    <section style="padding-top:8px;padding-bottom:80px">
      <div class="container">
        <div class="grid grid-cols-1 lg:grid-cols-5 gap-6">

          <div class="lg:col-span-3 form-card" v-reveal>
            <div v-if="submitted" style="padding:48px;text-align:center">
              <div style="width:60px;height:60px;border-radius:16px;background:rgba(14,116,144,0.1);border:1px solid var(--border-m);display:flex;align-items:center;justify-content:center;margin:0 auto 20px">
                <svg width="26" height="26" viewBox="0 0 24 24" fill="none" stroke="var(--accent-light)" stroke-width="2" stroke-linecap="round"><polyline points="20 6 9 17 4 12"/></svg>
              </div>
              <h2 style="font-size:1.15rem;font-weight:300;color:var(--heading);margin-bottom:8px">Mensagem enviada!</h2>
              <p style="font-size:0.84rem;color:var(--muted);max-width:340px;margin:0 auto;line-height:1.6">
                A ArtrCredi recebeu sua mensagem e entrara em contato em ate 48 horas.
              </p>
            </div>

            <div v-else style="padding:28px 32px">
              <h2 style="font-size:1rem;font-weight:300;color:var(--heading);margin-bottom:4px">Fale conosco</h2>
              <p style="font-size:0.8rem;color:var(--muted);margin-bottom:24px">Preencha os campos abaixo e entraremos em contato.</p>

              <form @submit.prevent="handleSubmit" style="display:flex;flex-direction:column;gap:18px">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                  <div>
                    <label class="field-label">Seu nome <span class="req">*</span></label>
                    <input v-model="form.nome" type="text" required placeholder="Nome completo" class="field-input" />
                  </div>
                  <div>
                    <label class="field-label">WhatsApp <span class="req">*</span></label>
                    <input v-model="form.whatsapp" type="tel" required placeholder="(11) 99999-9999" class="field-input" />
                  </div>
                </div>
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                  <div>
                    <label class="field-label">Empresa</label>
                    <input v-model="form.empresa" type="text" placeholder="Nome da empresa" class="field-input" />
                  </div>
                  <div>
                    <label class="field-label">E-mail corporativo</label>
                    <input v-model="form.email" type="email" placeholder="email@empresa.com.br" class="field-input" />
                  </div>
                </div>
                <div>
                  <label class="field-label">Mensagem</label>
                  <textarea v-model="form.descricao" rows="4" placeholder="Descreva sua necessidade de credito..." class="field-input" style="resize:none"></textarea>
                </div>
                <button type="submit" class="submit-btn">
                  ENVIAR MENSAGEM
                  <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round"><path d="M5 12h14m0 0-7-7m7 7-7 7"/></svg>
                </button>
              </form>
            </div>
          </div>

          <div class="lg:col-span-2" style="display:flex;flex-direction:column;gap:14px" v-reveal="{ delay: 100 }">
            <div class="sidebar-card">
              <h3 style="font-size:0.86rem;font-weight:300;color:var(--heading);margin-bottom:18px">O que acontece depois?</h3>
              <div style="display:flex;flex-direction:column;gap:14px">
                <div v-for="(s, i) in nextsteps" :key="i" style="display:flex;align-items:flex-start;gap:10px">
                  <span class="step-num-sm">{{ i+1 }}</span>
                  <p style="font-size:0.78rem;color:var(--muted);line-height:1.55">{{ s }}</p>
                </div>
              </div>
            </div>

            <a href="mailto:atendimentoartrcredi@artrcredi.com.br" class="wa-card">
              <div class="wa-icon">
                <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="var(--accent-light)" stroke-width="1.5" stroke-linecap="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
              </div>
              <div>
                <p style="font-size:0.86rem;color:var(--heading)">E-mail direto</p>
                <p style="font-size:0.72rem;color:var(--muted);margin-top:2px">atendimentoartrcredi@artrcredi.com.br</p>
              </div>
            </a>

            <div class="note-card">
              <div style="display:flex;align-items:center;gap:8px;margin-bottom:8px">
                <span style="width:6px;height:6px;border-radius:50%;background:var(--accent-light);display:inline-block"></span>
                <p style="font-size:0.84rem;font-weight:400;color:var(--heading)">Sem compromisso</p>
              </div>
              <p style="font-size:0.78rem;color:var(--muted);line-height:1.6">
                Simulacao sem custo. Voce so formaliza quando a proposta fizer sentido para sua empresa.
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
import { ref, reactive } from 'vue'
const submitted = ref(false)
const form = reactive({ nome:'', whatsapp:'', empresa:'', email:'', descricao:'' })

const nextsteps = [
  'A ArtrCredi recebe sua mensagem e analisa sua necessidade.',
  'Consultamos nossa rede de parceiros para encontrar as melhores ofertas.',
  'Voce recebe propostas comparativas em ate 48 horas.',
  'Escolha a melhor opcao e formalize direto com a instituicao.',
]

function handleSubmit() {
  const msg = `Ola! Quero falar com a ArtrCredi.\n\nNome: ${form.nome}\nEmpresa: ${form.empresa||'Nao informado'}\nE-mail: ${form.email||'Nao informado'}\n\n${form.descricao||''}`
  window.open(`https://wa.me/5511920158232?text=${encodeURIComponent(msg)}`, '_blank')
  submitted.value = true
}
</script>

<style scoped>
.form-card { border-radius:18px; border:1px solid var(--border-s); background:var(--bg-1); overflow:hidden; }
.field-label { display:block; font-size:0.74rem; font-weight:400; color:var(--muted); margin-bottom:7px; letter-spacing:.01em; }
.field-label .req { color:var(--accent-light); }
.field-input {
  display:block; width:100%; padding:11px 14px; border-radius:10px;
  background:rgba(255,255,255,0.03); border:1px solid var(--border-s);
  color:var(--text); font-size:0.84rem; font-family:var(--font-body);
  outline:none; transition:border-color .2s, background .2s;
  -webkit-appearance:none; appearance:none;
}
.field-input::placeholder { color:rgba(255,255,255,0.25); }
.field-input:focus { border-color:var(--accent-light); background:rgba(14,116,144,0.06); }
.field-input option { background:var(--bg-1); color:var(--text); }
.submit-btn {
  display:flex; align-items:center; justify-content:center; gap:8px;
  width:100%; padding:14px; border-radius:999px;
  font-size:0.84rem; font-weight:400; font-family:var(--font-body);
  color:#fff; border:none; cursor:pointer;
  background:linear-gradient(135deg, var(--accent-dark), var(--accent));
  box-shadow:0 0 16px rgba(34,211,238,0.25);
  transition:transform .25s var(--ease-out), box-shadow .25s;
}
.submit-btn:hover { box-shadow:0 0 28px rgba(34,211,238,0.4); transform:translateY(-1px); }
.sidebar-card { padding:22px 24px; border-radius:16px; border:1px solid var(--border-s); background:var(--bg-1); }
.step-num-sm {
  min-width:24px; height:24px; border-radius:50%;
  background:rgba(14,116,144,0.1); border:1px solid var(--border-m);
  display:flex; align-items:center; justify-content:center;
  font-size:0.68rem; font-weight:500; color:var(--accent-light);
  flex-shrink:0; margin-top:1px;
}
.wa-card {
  display:flex; align-items:center; gap:14px; padding:18px 20px;
  border-radius:16px; border:1px solid var(--border-s); background:var(--bg-1);
  transition:border-color .2s, background .2s;
}
.wa-card:hover { border-color:var(--border-m); background:rgba(14,116,144,0.05); }
.wa-icon {
  width:44px; height:44px; border-radius:12px;
  background:rgba(14,116,144,0.12); border:1px solid rgba(14,116,144,0.25);
  display:flex; align-items:center; justify-content:center; flex-shrink:0;
}
.note-card {
  padding:18px 20px; border-radius:16px;
  border:1px solid var(--border-m); background:rgba(14,116,144,0.05);
}
</style>
