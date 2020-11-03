<template>
  <div class="dzDiv">
    <!--    /*直播点赞动画*/-->
    <div class="btn" @click="like">点赞</div>
  </div>

</template>

<script>
export default {
  name: 'GiveTheThumbsUp',
  data() {
    return {
      count: 0
    }
  },
  methods: {
    like() {
      const dzDiv = document.querySelector('.dzDiv')
      const likeDom = document.createElement('div')
      this.count++
      console.log(this.count)
      likeDom.className = this.count % 2 === 0 ? 'like' : 'like like--is-second'
      likeDom.style.willChange = 'margin-top'
      dzDiv.appendChild(likeDom)
      setTimeout(() => {
        dzDiv.removeChild(likeDom)
      }, 3900)
    }
  }
}
</script>

<style  lang="scss">
  @import "src/components/give-the-thumbs-up.scss";
</style>
