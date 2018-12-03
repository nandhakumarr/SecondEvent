<template lang="pug">
section.faq
  .container
    .general-faqs
      header
        h2 General FAQ's
      .faqs(v-for='item in faq' :class="{ active: isCurrent(item)}")
        .ques 
          a {{ item.ques }}
          .image
            img(src="https://img.icons8.com/metro/48/000000/expand-arrow.png" @click="select(item)")
            img(src="https://img.icons8.com/metro/48/000000/expand-arrow.png" @click="select(item)")
        .ans 
          p {{ item.ans }}  
    .enquiry-forms  
      h2 Enquiry  

</template>
<script>
export default {
  data(){
    return{
      faq: [
        { ques: '1. When Does Exhibit Conference 2020 Will Occur?',
          ans: 'How you transform your business as technology, consumer, habits industry dynamic s change? Find out from those leading the charge.'
        },
        {
          ques: '2. Where Does Eventime Take Place?',
          ans: 'How you transform your business as technology, consumer, habits industry dynamic s change? Find out from those leading the charge.'
        },
        {
          ques: '3. How Can I Get The Latest News On Exhibit 2020?',
          ans: 'Anim pariatur cliche reprehenderit, enim eiusmod high life accusamus terry richardson ad squid. 3 wolf moon officia aute, non cupidatat skateboard dolor brunch. Food truck quinoa nesciunt laborum eiusmod. Brunch 3 wolf moon tempor, sunt aliqua put a bird on it squid single-origin coffee nulla assumenda shoreditch et. Nihil anim keffiyeh helvetica, craft beer labore wes anderson cred nesciunt sapiente ea proident. Ad vegan excepteur butcher vice lomo. Leggings occaecat craft beer farm-to-table, raw denim aesthetic synth nesciunt you probably haven\'t heard of them accusamus labore sustainable VHS.'
        },
        {
          ques: '4. How Can My Company Sponsor This Event 2018?',
          ans: 'How you transform your business as technology, consumer, habits industry dynamic s change? Find out from those leading the charge'
        }        
      ],
      selected: null
    }
  },
  methods: {
    select(item) {
      this.selected = this.isCurrent(item) ? null : item
    },
    isCurrent(item) {
      return this.selected && this.selected.ques === item.ques
    }
  }
}
</script>
<style lang="sass" scoped>
@import 'assets/styles/includes'
section.faq
  .container
    @include flex
    .general-faqs
      margin: 20px
      width: 70%
      .faqs
        padding: $space
        .ques
          
          border: 0.5px solid
          display: block
          padding: $space
          font-weight: 800
          a
            color: $black
          img
            width: $space 
            float: right

        .ans
          padding: $space
          display: none
      .faqs.active
        margin: 20px
        background: $event-pink
        .ques
          color: $white
          border: none
        .ans
          display: block

      
</style>
