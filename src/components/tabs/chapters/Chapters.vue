<template>
  <div class="chapters-tab" id="tab-chapters">
    <chapter-entry-component
      v-for="(chapter, index) in chapters"
      :chapter="chapter"
      :index="index"
      :key="index">
    </chapter-entry-component>
  </div>
</template>

<script>
  import { mapState } from 'redux-vuex'
  import { selectChapters } from 'store/selectors'

  import ChapterEntryComponent from './ChapterEntry'

  export default {
    data: mapState({
      chapters: selectChapters
    }),
    components: {
      ChapterEntryComponent
    }
  }
</script>

<style lang="scss">
  @import '~styles/variables';

  .chapters-tab {
    width: 100%;
    padding: $padding 0;
  }
</style>
