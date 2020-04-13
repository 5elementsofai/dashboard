
<template>
<div class="d-flex mt-auto">
    <button-with-icon v-if="previousUrl"
        variant="secondary"
        iconClass="la la-angle-double-left"
        class=" px-4"
        style="min-width: 110px;"
        :href="urlPrefix + previousUrl"> Previous </button-with-icon>
    <button-with-icon v-if="nextUrl"
        variant="theme1"
        iconClass="la la-angle-double-right"
        class="ml-auto px-4"
        style="min-width: 110px;"
        :href="urlPrefix + nextUrl"> Next </button-with-icon>

</div>
</template>
<script>
import ButtonWithIcon from '@/components/Base/Button/ButtonWithIcon'

export default {
  components: {
    ButtonWithIcon
  },
  props: ['previousUrl', 'nextUrl'],
  computed: {
    urlPrefix () {
      const metaPage = this.$router.currentRoute.meta
      return metaPage.layout ? '/' + metaPage.layout : ''
    }
  }

}

</script>



