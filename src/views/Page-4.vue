<template>
  <div style="width: 50vw">
    <chess-board position="start" />

    <ChessBoardLoader v-if="mounted" />
  </div>
</template>

<script>
import { defineAsyncComponent } from "@vue/runtime-core";

export default {
  data() {
    return {
      mounted: false,
    }
  },

  components: {
    ChessBoardLoader: defineAsyncComponent(() =>
      import("@/components/ChessBoardLoader.vue")
    ),
  },

  mounted () {
    setTimeout(() => {
      this.mounted = true;
    }, 250);
  },
};
</script>
