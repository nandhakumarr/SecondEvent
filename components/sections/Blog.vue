<template lang="pug">
section.blog
  .container
    header
      span INFO UPDATE
      h2 Latest News
    main
      .card(v-for="(blog, i) in blogs", key="i")
        .blog
          .blog-image
            img(:src="blog.img")
          .blog-content
            .blog-author
              span {{ blog.author }}
              span {{ blog.date }}
            .blog-header
              h2 {{ blog.title }}
            .blog-description
              p {{ blog.details }}
            .blog-footer
              a(href="#") Read More
                span
                  img(src="/images/right-arrow.png")
  img.half-circle(src="/images/news-memphis1.png")
  img.lines(src="/images/news-memphis2.png")

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
    main
      padding: $space*2
      @media (min-width: $breakpoint-tab-4)
        @include flex



.blog
  .blog-image
    width: calc(100% - 40px)
    margin: 0 auto 5px auto
    position: relative
    img
      box-shadow: 0px 15px 20px 0px rgba(0, 0, 0, 0.25)
      border-radius: 5px
      max-width: 100%
      height: auto

.blog
  .blog-content
    background: $white
    box-shadow: 0px 5px 15px 0px rgba(0, 0, 0, 0.05)
    padding: 150px 20px 25px 30px
    margin: -130px 0px 30px
    border-radius: 5px
    transition: all 0.4s ease
    .blog-author
      font-size: 13px
      margin-bottom: 15px
      span
        margin-right: $space*1.5
        text-transform: uppercase
        color:  $event-color
    .blog-header
      h2
        font-size: 1.3rem !important
        margin-bottom: $space
    .blog-description
      p
        color: $neutral-light !important
    .blog-footer
      a
        color: $neutral
        font-size: 1rem
        span
          margin-left: $space/2
          position: relative
          top: 0.7rem
          img
            width: 2rem
section.blog
  position: relative
  .half-circle
    @include absolute-w
    top: 7rem
  .lines
    @include absolute-ne
    top: 7rem
</style>

