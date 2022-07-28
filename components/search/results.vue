<template>
  <ui-card class="search-results" v-if="results">
    <div class="search-results-group" v-if="results.tokens">
      <div class="group-title">Tokens</div>
      <div class="group-list">
        <nuxt-link
          v-for="token in results.tokens"
          :key="token.id"
          :to="{ name: 'tokens-id', params: { id: token.id } }"
          class="group-list-item"
        >
          <logo-token :address="token.id" :symbol="token.symbol" />
          <span>{{ token.name }} ({{ token.symbol }})</span>
        </nuxt-link>
      </div>
    </div>
    <div class="search-results-group" v-if="results.pairs">
      <div class="group-title">Pools</div>
      <div class="group-list">
        <div v-for="pair in results.pairs" :key="pair.id">
          {{ pair.name }}
        </div>
      </div>
    </div>
  </ui-card>
</template>

<script>
export default {
  name: 'SearchResults',
  props: {
    results: {
      type: Object,
      default: () => ({}),
    },
  },
};
</script>

<style lang="scss" scoped>
.search-results {
  padding: 16px;
  min-width: 320px;
}

.group-list {
  &-item {
    display: flex;
    align-items: center;
    flex-flow: row nowrap;
  }
}
</style>