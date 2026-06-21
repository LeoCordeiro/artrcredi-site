<template>
  <footer>
    <div class="container">
      <div class="footer-grid">
        <div class="footer-brand">
          <div class="footer-logo">
            <img class="footer-logo-img" src="/logo-footer.png" alt="ArtrCredi" />
          </div>
          <p>Acesso a credito e antecipacao de recebiveis para empresas. Conectamos sua empresa as melhores condicoes do mercado, com comparacao automatica e resposta rapida.</p>
        </div>
        <div>
          <p class="footer-col-title">Empresa</p>
          <ul class="footer-links">
            <li><router-link to="/">Inicio</router-link></li>
            <li><router-link to="/como-funciona">Como Funciona</router-link></li>
            <li><router-link to="/sobre">Sobre</router-link></li>
            <li><router-link to="/contato">Contato</router-link></li>
          </ul>
        </div>
        <div>
          <p class="footer-col-title">Contato</p>
          <ul class="footer-links">
            <li>
              <a href="mailto:atendimentoartrcredi@artrcredi.com.br" class="footer-contact-link">
                <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="var(--accent-light)" stroke-width="1.5" stroke-linecap="round"><rect x="2" y="4" width="20" height="16" rx="2"/><path d="m2 7 10 7 10-7"/></svg>
                atendimentoartrcredi@artrcredi.com.br
              </a>
            </li>
            <li>
              <a href="https://wa.me/5511920158232" target="_blank" class="footer-contact-link">
                <svg width="13" height="13" viewBox="0 0 24 24" fill="var(--accent-light)"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374A9.86 9.86 0 012.157 12c0-5.45 4.436-9.884 9.884-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/></svg>
                (11) 92015-8232
              </a>
            </li>
            <li>
              <a href="https://www.instagram.com/artrcredi/" target="_blank" class="footer-contact-link">
                <svg width="13" height="13" viewBox="0 0 24 24" fill="var(--accent-light)"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 1.17.054 1.97.24 2.43.403a4.088 4.088 0 011.47.958c.453.453.78.898.958 1.47.163.46.349 1.26.404 2.43.058 1.266.07 1.646.07 4.85s-.012 3.584-.07 4.85c-.055 1.17-.241 1.97-.404 2.43a4.088 4.088 0 01-.958 1.47 4.088 4.088 0 01-1.47.958c-.46.163-1.26.349-2.43.404-1.266.058-1.646.07-4.85.07s-3.584-.012-4.85-.07c-1.17-.055-1.97-.241-2.43-.404a4.088 4.088 0 01-1.47-.958 4.088 4.088 0 01-.958-1.47c-.163-.46-.349-1.26-.404-2.43C2.175 15.584 2.163 15.204 2.163 12s.012-3.584.07-4.85c.055-1.17.241-1.97.404-2.43a4.088 4.088 0 01.958-1.47A4.088 4.088 0 015.065 2.293c.46-.163 1.26-.349 2.43-.404C8.761 1.831 9.141 1.819 12 1.819V2.163zM12 0C8.741 0 8.333.014 7.053.072 5.775.131 4.903.333 4.14.63a5.876 5.876 0 00-2.126 1.384A5.876 5.876 0 00.63 4.14C.333 4.903.131 5.775.072 7.053.014 8.333 0 8.741 0 12s.014 3.667.072 4.947c.059 1.278.261 2.15.558 2.913a5.876 5.876 0 001.384 2.126 5.876 5.876 0 002.126 1.384c.763.297 1.635.499 2.913.558C8.333 23.986 8.741 24 12 24s3.667-.014 4.947-.072c1.278-.059 2.15-.261 2.913-.558a5.876 5.876 0 002.126-1.384 5.876 5.876 0 001.384-2.126c.297-.763.499-1.635.558-2.913.058-1.28.072-1.688.072-4.947s-.014-3.667-.072-4.947c-.059-1.278-.261-2.15-.558-2.913a5.876 5.876 0 00-1.384-2.126A5.876 5.876 0 0019.86.63C19.097.333 18.225.131 16.947.072 15.667.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/></svg>
                @artrcredi
              </a>
            </li>
            <li class="footer-response-time">Resposta em ate 48 horas</li>
          </ul>
        </div>
        <div>
          <p class="footer-col-title">Legal</p>
          <ul class="footer-links">
            <li><router-link to="/privacidade">Politica de Privacidade</router-link></li>
            <li><router-link to="/termos">Termos de Uso</router-link></li>
            <li><router-link to="/comissao">Politica de Comissao</router-link></li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        <span class="footer-copy">&copy; {{ year }} ArtrCredi &middot; artrcredi.com.br &middot; Sao Paulo, SP &middot; CNPJ 67.089.141/0001-01</span>
      </div>
    </div>
  </footer>
</template>

<script setup>
const year = new Date().getFullYear()
</script>

<style scoped>
footer {
  background: var(--bg-1);
  border-top: 1px solid var(--border-s);
  padding: 64px 0 0;
  position: relative;
}
footer::before {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse 60% 40% at 50% 0%, rgba(14,116,144,0.04), transparent);
  pointer-events: none;
}
.footer-grid {
  display: grid;
  grid-template-columns: 1.8fr 1fr 1.2fr 1fr;
  gap: 48px;
  padding-bottom: 48px;
  border-bottom: 1px solid var(--border-s);
  position: relative;
}
.footer-brand p {
  font-size: 0.78rem;
  color: var(--muted);
  max-width: 240px;
  line-height: 1.7;
  margin-top: 12px;
}
.footer-logo {
  display: flex;
  align-items: center;
}
.footer-logo-img {
  height: 56px;
  width: auto;
  object-fit: contain;
  mix-blend-mode: lighten;
}
.footer-col-title {
  font-size: 0.72rem;
  font-weight: 500;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  color: var(--muted);
  margin-bottom: 16px;
}
.footer-links {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.footer-links a {
  font-size: 0.8rem;
  color: rgba(255,255,255,0.35);
  transition: color 0.2s;
}
.footer-links a:hover { color: var(--text); }
.footer-contact-link {
  display: flex;
  align-items: flex-start;
  gap: 6px;
  word-break: break-all;
  line-height: 1.4;
}
.footer-contact-link svg {
  flex-shrink: 0;
  margin-top: 2px;
}
.footer-response-time {
  font-size: 0.72rem;
  color: var(--accent-light);
  margin-top: 4px;
  display: flex;
  align-items: center;
  gap: 6px;
}
.footer-response-time::before {
  content: '';
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background: var(--accent-light);
  flex-shrink: 0;
}
.footer-bottom {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 20px 0;
  position: relative;
}
.footer-copy {
  font-size: 0.72rem;
  color: rgba(255,255,255,0.25);
}

@media (max-width: 991px) {
  .footer-grid { grid-template-columns: 1fr 1fr; gap: 32px; }
}
@media (max-width: 574px) {
  .footer-grid { grid-template-columns: 1fr; }
}
</style>
