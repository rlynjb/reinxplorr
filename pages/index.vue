<template>
<div class="index-page">
  <div class="index-page__header">
    <img class="index-page__header-logo" :src="state.logo" />
    <h1>{{ state.title }}</h1>
  </div><!-- /index-page__header -->

  <div class="index-page__content">
    <div class="index-page__card"
      v-for="(item, itemIndex) in state.links"
      :key="'itemIndex'+itemIndex">
      <img :src="item.image" />

      <div class="index-page__desc">
        <h6>{{ item.name }}</h6>
        <p>{{ item.desc }}</p>
        <a :href="item.link" target="_blank">
          visit item
        </a>
      </div>
    </div>
  </div><!-- /index-page__content -->
</div><!-- /index-page -->
</template>

<script>
import { reactive, computed } from "vue";

export default {
  props: {
    testTitle: String,
  },

  setup(props, { emit }) {
    const state = reactive({
      title: "Resource Page",
      logo: "Rein.png",
      links: [
        {
          id: 'testid',
          name: 'testname',
          image: 'https://via.placeholder.com/200',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sed arcu a erat placerat bibendum id nec enim.',
          link: 'https://google.com',
        },
        {
          id: 'testid',
          name: 'testname',
          image: 'https://via.placeholder.com/200',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sed arcu a erat placerat bibendum id nec enim.',
          link: 'https://google.com',
        },
        {
          id: 'testid',
          name: 'testname',
          image: 'https://via.placeholder.com/200',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sed arcu a erat placerat bibendum id nec enim.',
          link: 'https://google.com',
        },
        {
          id: 'testid',
          name: 'testname',
          image: 'https://via.placeholder.com/200',
          desc: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed sed arcu a erat placerat bibendum id nec enim.',
          link: 'https://google.com',
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
.index-page__header-logo {
  @apply mb-4 ml-auto mr-auto;
  max-width: 14em;
}
.index-page__header h1 {
  @apply text-indigo-900;
}
.index-page__content {
  @apply col-span-4 grid grid-cols-4 gap-4 p-4;
}
.index-page__card {
  @apply col-span-2 p-3;
  border: 1px solid #000;
}
.index-page__desc h6 {
  @apply mt-3 mb-1;
}
.index-page__desc p {
  font-size: 0.8em;
  line-height: 1.3;
}
.index-page__desc a {
  @apply mt-4 p-2 bg-indigo-50 text-indigo-900;
  font-size: 0.7em;
  text-align: center;
  display: block;
}
</style>