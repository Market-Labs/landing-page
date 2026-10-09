<script setup lang="ts">
import { useI18n } from 'vue-i18n'
const { t } = useI18n()

const socialLinks = [
  {
    key: 'linkedin',
    href: 'https://www.linkedin.com/company/marketgo-lab',
    path: 'M6.94 8.98H3.72V20h3.22V8.98ZM5.33 7.49c1.03 0 1.67-.68 1.67-1.53-.02-.87-.64-1.53-1.65-1.53S3.68 5.09 3.68 5.96c0 .85.64 1.53 1.63 1.53h.02ZM20.32 20v-6.32c0-3.38-1.8-4.95-4.2-4.95-1.94 0-2.8 1.07-3.29 1.82h.02V8.98H9.63c.04 1.03 0 11.02 0 11.02h3.22v-6.16c0-.33.02-.66.12-.9.26-.66.85-1.34 1.85-1.34 1.31 0 1.83 1 1.83 2.46V20h3.67Z',
  },
  {
    key: 'x',
    href: 'https://x.com/MarketGoLab',
    path: 'M17.23 4h3.04l-6.64 7.59L21.44 20h-6.12l-4.79-5.92L5.05 20H2l7.1-8.12L1.6 4h6.27l4.33 5.41L17.23 4Zm-1.07 14.52h1.68L6.95 5.4H5.14l11.02 13.12Z',
  },
  {
    key: 'facebook',
    href: 'https://www.facebook.com/MarketGoLab',
    path: 'M14.02 8.18V6.66c0-.74.5-.91.86-.91h2.18V2.12L14.05 2.1c-3.35 0-4.11 2.5-4.11 4.1v1.98H7.8v3.74h2.14V22h4.08V11.92h2.76l.37-3.74h-3.13Z',
  },
]
</script>

<template>
  <footer class="site-footer">
    <div class="container footer-inner">
      <a class="footer-brand" href="#home">
        <img src="/assets/images/brand/logo-marketgo.png" alt="MarketGo logo" />
        <span>MarketGo</span>
      </a>
      <small>{{ t('footer.copy') }}</small>
      <div class="footer-links">
        <nav aria-label="Footer navigation">
          <a href="https://amesa.com.mx/wp-content/uploads/2025/04/terminos-y-condiciones.pdf" target="_blank" rel="noopener noreferrer">{{ t('footer.terms') }}</a>
          <a href="https://www.gob.mx/cms/uploads/attachment/file/92883/POLITICA_DE_PRIVACIDAD_INDAABIN.pdf" target="_blank" rel="noopener noreferrer">{{ t('footer.privacy') }}</a>
          <a href="https://www.gob.mx/cms/uploads/attachment/file/92883/POLITICA_DE_PRIVACIDAD_INDAABIN.pdf" target="_blank" rel="noopener noreferrer">{{ t('footer.support') }}</a>
        </nav>
        <nav class="footer-social" :aria-label="t('footer.social.label')">
          <a
            v-for="social in socialLinks"
            :key="social.key"
            :href="social.href"
            target="_blank"
            rel="noopener noreferrer"
            :aria-label="t(`footer.social.${social.key}`)"
          >
            <svg viewBox="0 0 24 24" aria-hidden="true" focusable="false">
              <path :d="social.path" />
            </svg>
          </a>
        </nav>
      </div>
    </div>
  </footer>
</template>

