<template>
<div class="index-page">
  <div class="index-page__header">
    <h1>ReinXplorr</h1>
  </div><!-- /header -->

  <div class="index-page__content">

  </div><!-- /content -->
</div>
</template>

<style lang="postcss" scoped>
.index-page {
  @apply grid grid-cols-4 gap-3;
}
.index-page__header {
  @apply col-span-4 text-center p-4 text-red-700;
}
.index-page__content {
  @apply col-span-4 grid grid-cols-4;
}
</style>