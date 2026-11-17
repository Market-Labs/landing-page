<script setup lang="ts">
import { useI18n } from 'vue-i18n'
const { t } = useI18n()
const videos = ['team', 'product'] as const
const videoSources = {
  team: 'https://www.youtube.com/embed/LbMoNAv3fP4',
  product: 'https://www.youtube.com/embed/D0y_F9tcJrs',
}
</script>

<template>
  <section id="videos" class="section video-section">
    <div class="container">
      <div class="section-header">
        <p class="section-pill">{{ t('videos.eyebrow') }}</p>
        <h2>{{ t('videos.title') }}</h2>
        <p>{{ t('videos.subtitle') }}</p>
      </div>
      <div class="video-grid">
        <article v-for="video in videos" :key="video" class="video-card" :class="`video-card--${video}`">
          <div class="video-thumb">
            <iframe
              :src="videoSources[video]"
              :title="t(`videos.${video}.title`)"
              allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
              allowfullscreen
              loading="lazy"
              referrerpolicy="strict-origin-when-cross-origin"
            ></iframe>
          </div>
          <div class="video-body">
            <span>{{ t(`videos.${video}.kicker`) }}</span>
            <h3>{{ t(`videos.${video}.title`) }}</h3>
            <p>{{ t(`videos.${video}.description`) }}</p>
          </div>
        </article>
      </div>
    </div>
  </section>
</template>
