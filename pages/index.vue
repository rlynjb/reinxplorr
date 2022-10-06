<template>
<div class="index-page">
  <div class="index-page__header">
    <h1>{{ state.title }}</h1>
  </div><!-- /header -->

  <div class="index-page__content">
    <div class="index-page__card">
      image,
      title,
      desc,
      link,
      id
    </div>
  </div><!-- /content -->
</div>
</template>

<script>
import { reactive, computed } from "vue";

export default {
  props: {
    testTitle: String,
  },

  setup(props, { emit }) {
    const state = reactive({
      title: "Rein Merch",
      affiliateLinks: [
        {
          id: '',
          name: '',
          image: '',
          desc: '',
          link: '',
        }
      ],
    });


    onMounted(() => {
      console.log('on mouuunted....', props.testTitle)
    });


    const publishedBooksMsg = computed(() => {
      return 123;
    });


    const methodTest = () => {
      console.log('method Test')

      emit('emitTest', {
        hello: 'world'
      });
    };


    return {
      state,
      methodTest,
      publishedBooksMsg,
    };
  },
}
</script>

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
.index-page__card {
  @apply col-span-1;
}
</style>