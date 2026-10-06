<template>
  <AppLayout>
    <div class="card-shop-shell">
      <div class="card-shop-toolbar">
        <div>
          <p class="card-shop-eyebrow">{{ t('cardShop.eyebrow') }}</p>
          <h1>{{ t('cardShop.title') }}</h1>
        </div>
        <a
          class="card-shop-external"
          :href="shopUrl"
          target="_blank"
          rel="noopener noreferrer"
        >
          {{ t('cardShop.openExternal') }}
          <Icon name="externalLink" size="sm" />
        </a>
      </div>

      <div class="card-shop-frame-wrap">
        <iframe
          :src="shopUrl"
          :title="t('cardShop.iframeTitle')"
          class="card-shop-frame"
          allow="payment"
          referrerpolicy="strict-origin-when-cross-origin"
        />
      </div>
    </div>
  </AppLayout>
</template>

<script setup lang="ts">
import { useI18n } from 'vue-i18n'
import AppLayout from '@/components/layout/AppLayout.vue'
import Icon from '@/components/icons/Icon.vue'

const { t } = useI18n()
const shopUrl = 'https://catfk.com/shop/CPJO6PL8'
</script>

<style scoped>
.card-shop-shell {
  display: flex;
  min-height: calc(100vh - 7rem);
  flex-direction: column;
  gap: 1rem;
}

.card-shop-toolbar {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 1rem;
}

.card-shop-eyebrow {
  margin: 0 0 0.25rem;
  color: rgb(100 116 139);
  font-size: 0.72rem;
  font-weight: 700;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

h1 {
  margin: 0;
  color: rgb(15 23 42);
  font-size: 1.35rem;
  font-weight: 700;
}

.card-shop-external {
  display: inline-flex;
  align-items: center;
  gap: 0.4rem;
  color: rgb(37 99 235);
  font-size: 0.875rem;
  font-weight: 600;
}

.card-shop-frame-wrap {
  min-height: 0;
  flex: 1;
  overflow: hidden;
  border: 1px solid rgb(226 232 240);
  border-radius: 0.75rem;
  background: white;
  box-shadow: 0 12px 32px rgb(15 23 42 / 0.06);
}

.card-shop-frame {
  display: block;
  width: 100%;
  min-height: calc(100vh - 11rem);
  border: 0;
}

:global(.dark) h1 {
  color: rgb(248 250 252);
}

:global(.dark) .card-shop-frame-wrap {
  border-color: rgb(51 65 85);
  background: rgb(15 23 42);
}

@media (max-width: 640px) {
  .card-shop-toolbar {
    align-items: flex-start;
    flex-direction: column;
  }

  .card-shop-frame {
    min-height: calc(100vh - 13rem);
  }
}
</style>
