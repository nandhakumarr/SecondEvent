<template lang="pug">
section.faq
  .container
    .general-faqs
      header
        h2 General FAQ's
      .faqs(v-for='(item) in faq' :class="{ active: isCurrent(item)}")
        .ques(@click="select(item)")
          a {{ item.ques }}               
        .ans 
          p {{ item.ans }}  
    .enquiry-forms  
      input(type="text" placeholder="Your Name")
      input(type="text" placeholder="Your Email")
      textarea(placeholder="Youy Question")
      button.btn Send Question
      .services
        h3 Our Services
        .images
          img(src="https://img.icons8.com/ios/48/3498db/facebook-circled-filled.png")
          img(src="https://img.icons8.com/ios/48/3498db/twitter-circled-filled.png")
          img(src="https://img.icons8.com/color/48/3498db/google-plus.png")
          img(src="https://img.icons8.com/ios/48/3498db/linkedin-circled-filled.png")
          img(src="https://img.icons8.com/ios/48/e74c3c/instagram-new-filled.png")

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
    align-items: flex-start
    @media (max-width: $breakpoint-tab-4)
      flex-direction: column
    .general-faqs
      width: 60%
      @media (max-width: $breakpoint-tab-4)
        width: 100%
      .faqs
        padding: $space
        .ques       
          display: block
          border: 0.1px solid grey
          padding: $space
          font-weight: 800
          a
            color: $black
          img
            width: $space 
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
    .enquiry-forms
      padding: $space         
      width: 40%  
      @media (max-width: $breakpoint-tab-4)
        width: 100%
      input, textarea
        margin-bottom: $space
        width: 100%
        padding: $space 
      .btn     
        margin-left: 1rem
    .services
      margin-top: $space*1.5
      padding: $space*2
      background: #f8f8f8
      width: 15rem
      height: 8rem
      @media (max-width: $breakpoint-tab-4)
        display: none
      .images
        img
          padding: $space/4
          width: $space*2

</style>
