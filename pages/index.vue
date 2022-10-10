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
      </div>

      <a class="index-page__desc-link"
        :href="item.link" target="_blank">
        visit
      </a>
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
  font-size: 0.5em;
  text-transform: uppercase;
  letter-spacing: 3px;
}
.index-page__content {
  @apply col-span-4 grid grid-cols-4 gap-4 p-4;
}
.index-page__card {
  @apply col-span-2;
  border: 1px solid #000;
  border-radius: 5px;
}
.index-page__desc {
  @apply p-3;
}
.index-page__desc h6 {
  @apply mb-1;
}
.index-page__desc p {
  font-size: 0.8em;
  line-height: 1.3;
}
.index-page__desc-link {
  @apply p-4 bg-indigo-50 text-indigo-900;
  text-align: center;
  display: block;
  font-size: 0.5em;
  text-transform: uppercase;
  letter-spacing: 3px;
}
</style>