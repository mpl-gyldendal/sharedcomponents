<template>
  <section class="copyright ce-frame mx-auto" :class="[isSearchPage ? 'ce-frame--widescreen' : '']">
    <div class="copyright__content">
      <p class="text-15 mb-0">
        <!-- {{
          $t('labels.generic.copyright', {
            ISBN13: isbn,
            PUBLISHER: publisher,
            YEAR: copyrightYear
          })
        }} -->
      </p>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue';

// import { useT3Store } from '@/stores/typo3';
// import type { Settings, Metadata, RootPage } from '~/types/pageContract';

// const store = useT3Store();
// const route = useRoute();

defineProps({
  isbn: {
    type: String,
    required: !true
  },
  publisher: {
    type: String,
    required: !true
  }
});

const isSearchPage = ref<boolean>(false);

// const settings: ComputedRef<Settings> = computed(
//   () => store.initialData?.site.settings
// );
// const metadata: ComputedRef<Metadata> = computed(
//   () => store.initialData?.site.metadata
// );
// const rootPage: ComputedRef<RootPage> = computed(
//   () => store.pageData as unknown as RootPage
// );

// const copyrightYear: ComputedRef<string> = computed(() => {
//   if (metadata.value?.copyright_year !== '') {
//     return metadata.value?.copyright_year;
//   }
//   return new Date().getFullYear().toString();
// });

// watch(
//   () => route.fullPath,
//   () => {
//     if (rootPage.value) {
//       const rootPageIsEmpty = Object.keys(rootPage.value).length === 0;
//       if (!rootPageIsEmpty) {
//         isSearchPage.value =
//           rootPage.value.page.id === settings.value.searchPageId;
//       } else {
//         isSearchPage.value = false;
//       }
//     }
//   }
// );
</script>

<style lang="scss" scoped>
.copyright {
  margin-bottom: 6rem;
  /*
  @include md-up {
    margin-bottom: 8rem;
  }
  */
}

.copyright__content {
  border-top: solid 1px #f1f1f1;
  padding-top: 3.2rem;

  p {
    // @include text-brand-text-quinary;

    .v-theme--dark & {
      // @include text-white;
    }
  }
}
</style>
