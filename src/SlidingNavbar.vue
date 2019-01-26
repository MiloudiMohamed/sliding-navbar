<template>
  <nav
    class="nav"
    :class="{ 'nav--pinned': pinned }"
    :style="{
      height: `${navHeight}px`,
      top: `-${navHeight}px`,
      transition: `${duration}ms all ease`,
    }"
    >

    <slot/>
  </nav>
</template>

<script>
  export default {
    props: {
      navHeight: {
        default: 80,
        type: Number,
      },
      triggerAt: {
        default: 80,
        type: Number,
      },
      duration: {
        default: 200,
        type: Number,
      }
    },

    data () {
      return {
        pinned: true
      }
    },

    methods: {
      addScrollListener () {
        let pxTrigger = 0
        const triggerAt = this.triggerAt

        document.addEventListener('scroll', () => {
          const pxFromTop = window.scrollY || window.pageYOffset

          if ( pxFromTop > triggerAt ) {
            this.pinned = pxFromTop < pxTrigger

            pxTrigger = pxFromTop
          } else {
            this.pinned = true
          }

        })
      }
    },

    mounted () {
      this.addScrollListener()
    }
  }
</script>

<style scoped>
  .nav {
    position: fixed;
    width: 100%;
  }

  .nav--pinned {
    top: 0!important;
  }
</style>