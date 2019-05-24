<template>
  <div class="chess-board">
    <div class="board">
      <div
        :class="[`row-${row}`, 'row']"
        v-for="row in 9"
        :key="row">
        <div
          v-for="col in 8"
          :key="col"
          :class="['col', `col-${col}`]">
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  
}
</script>

<style lang="stylus" scoped>
$boardColor = rgb(128, 64, 0)
$lineWidth = 2px
$obliqueLineWidth = 1px
$lineColor = black
$space = 5%
$size = 15%
.chess-board
  position ficed
  margin auto
  width .8 * min(100vw, 100vh)
  height .9 * min(100vw, 100vh)
  background $boardColor
  position relative
  .board
    position absolute
    background $lineColor
    left 5%
    right 5%
    top 5%
    bottom 5%
    display flex
    flex-direction column
    .row
      flex auto
      display flex
      .col
        position relative
        flex auto
        background $boardColor
        margin-left $lineWidth
        margin-top $lineWidth
        &:last-child
          margin-right $lineWidth
      &:last-child
        .col
          margin-bottom $lineWidth
    .row-5
      .col
        margin-left 0
        margin-right 0
      .col:first-child
        margin-left $lineWidth
    .row-1 .col-4, .row-2 .col-5, .row-8 .col-4, .row-9 .col-5,
    .row-1 .col-5, .row-2 .col-4, .row-8 .col-5, .row-9 .col-4
      &::after
        content ''
        position absolute
        width 141.4%
        height $obliqueLineWidth
        background $lineColor
        top 50%
        left 50%
        transform translate(-50%, -50%)  rotate(45deg)
    .row-1 .col-5, .row-2 .col-4, .row-8 .col-5, .row-9 .col-4
      &::after
        transform translate(-50%, -50%)  rotate(135deg)
    
    .row-2 .col-1, .row-2 .col-7, .row-7 .col-1, .row-7 .col-7,
    .row-3 .col-2, .row-3 .col-4, .row-3 .col-6, .row-3 .col-8,
    .row-6 .col-2, .row-6 .col-4, .row-6 .col-6, .row-6 .col-8
      &::before
        position absolute
        content ''
        border-right $lineWidth solid $lineColor
        border-bottom $lineWidth solid $lineColor
        bottom $space
        right $space
        width $size
        height $size
    .row-2 .col-2, .row-2 .col-8, .row-7 .col-2, .row-7 .col-8
    .row-3 .col-1, .row-3 .col-3, .row-3 .col-5, .row-3 .col-7
    .row-6 .col-1, .row-6 .col-3, .row-6 .col-5, .row-6 .col-7
      &:before
        position absolute
        content ''
        border-bottom $lineWidth solid $lineColor
        border-left $lineWidth solid $lineColor
        left $space
        bottom $space
        width $size
        height $size
    .row-3 .col-1, .row-3 .col-7, .row-8 .col-1, .row-8 .col-7,
    .row-4 .col-2, .row-4 .col-4, .row-4 .col-6, .row-4 .col-8
    .row-7 .col-2, .row-7 .col-4, .row-7 .col-6, .row-7 .col-8
      &:after
        position absolute
        content ''
        border-top $lineWidth solid $lineColor
        border-right $lineWidth solid $lineColor
        right $space
        top $space
        width $size
        height $size
    .row-3 .col-2, .row-3 .col-8, .row-8 .col-2, .row-8 .col-8,
    .row-4 .col-1, .row-4 .col-3, .row-4 .col-5, .row-4 .col-7,
    .row-7 .col-1, .row-7 .col-3, .row-7 .col-5, .row-7 .col-7
      &::after
        position absolute
        content ''
        border-top $lineWidth solid $lineColor
        border-left $lineWidth solid $lineColor
        width $size
        height $size
        left $space
        top $space
</style>


