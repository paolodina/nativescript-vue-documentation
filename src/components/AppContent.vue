<template>
    <div class="AppContent">
        <ContentPane>
            <router-view />
        </ContentPane>

        <PreviewPane v-if="frontMatter.preview">
            {{ frontMatter.preview }}
        </PreviewPane>
    </div>
</template>

<script>
    import ContentPane from './ContentPane'
    import PreviewPane from './PreviewPane'
    import { mapState } from 'vuex'

    export default {
      computed: {
        ...mapState({
          frontMatter: state => state.current.matter
        })
      },

      components: {
        ContentPane,
        PreviewPane
      }
    }
</script>