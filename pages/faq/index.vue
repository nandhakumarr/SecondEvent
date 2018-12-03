<template lang="pug">
.page
  page-hero(pageTitle="Event FAQ's", pageSubTitle="Home/ Faq")
  faq
</template>
<script>
import PageHero from '~/components/PageHero/PageHero.vue'
import Faq from '~/components/sections/faq/Faq.vue'

export default {
  components: {
    PageHero,
    Faq
  }
}
</script>
<style lang="sass" scoped>

</style>
