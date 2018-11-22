<template lang="pug">
section.blog
  .container
    .blog-title
      span INFO UPDATE
      h2 Latest News
    .blogs  
      .card(v-for="blog in blogs")
        .thumb
          img(:src="blog.img")
        .blog-author
          span {{ blog.author }}
          span {{ blog.date }}
        .card-title
          h2 {{ blog.title }}
          p {{ blog.deta   
        .readmore  
          a(href="#") Read More  
          img(src="/images/right-arrow.png")

</template>

<script>
export default {
  data(){
    return {
      blogs:[
        { img:'/images/blog1.jpg', author: 'BY ADMIN', date:'OCTOBER 8, 2018', title:'Check upcoming Events', details:'How you transform your business asap technology, consumer,'},
        { img:'/images/blog2.jpg', author: 'BY ADMIN', date:'OCTOBER 8, 2018', title:'Adding a New digital', details:'How you transform your business asap technology, consumer,'},
        { img:'/images/blog3.jpg', author: 'BY ADMIN', date:'OCTOBER 8, 2018', title:'West ElmAt Evantor', details:'How you transform your business asap technology, consumer,'}
      ]
    }
  }
}
</script>

<style lang="sass" scoped>
@import 'assets/styles/includes'
section.blog
  background: #f9fafc
  .container
    .blog-title
      text-align: center
    .blogs  
      padding: $space*2
      @media (min-width: $breakpoint-tab-4)
        @include flex
      .card
        box-shadow: 0 4px 8px 0 rgba(0,0,20,0.2) 
        box-sizing: border-box
        color: black
        padding: $space
        margin-bottom: $space*5
        @media (min-width: $breakpoint-tab-4)
          width: 31.33% 
        .thumb
          text-align: center
          img
            border-radius: 20px
            width: 100%
            // margin-bottom: $space
            position: relative
            top: -5rem
        .blog-author
          @include flex
          padding: $space
          span
            color: #ff007a 
        .card-title
          padding: $space
          h2
            font-size: $space*1.2
          p
            color: #888888 
        .readmore     
          @include flex
          justify-content: flex-start
          a
            padding: $space
            color: black
            
</style>

