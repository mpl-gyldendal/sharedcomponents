<template>
  <section class="copyright ce-frame mx-auto" :class="[isSearchPage ? 'ce-frame--widescreen' : '']">
    <div class="copyright__content">
      <p class="text-15 mb-0">{{ copyrightText }}</p>
    </div>
  </section>
</template>

<script setup lang="ts">
import { ref, defineProps } from 'vue';

defineProps({
  copyrightText: {
    type: String,
    required: true
  }
});

const isSearchPage = ref<boolean>(false);

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
