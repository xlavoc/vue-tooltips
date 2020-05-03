<template>
  <div class="tooltip">
    <span v-html="content"></span>
      <svg aria-hidden="true" data-icon="times" class="close" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 384 512">
        <path fill="currentColor" d="M231.6 256l130.1-130.1c4.7-4.7 4.7-12.3 0-17l-22.6-22.6c-4.7-4.7-12.3-4.7-17 0L192 216.4 61.9 86.3c-4.7-4.7-12.3-4.7-17 0l-22.6 22.6c-4.7 4.7-4.7 12.3 0 17L152.4 256 22.3 386.1c-4.7 4.7-4.7 12.3 0 17l22.6 22.6c4.7 4.7 12.3 4.7 17 0L192 295.6l130.1 130.1c4.7 4.7 12.3 4.7 17 0l22.6-22.6c4.7-4.7 4.7-12.3 0-17L231.6 256z">
        </path>
      </svg>
    <div class="arrow" data-popper-arrow></div>
  </div>
</template>

<script>
export default {
  name: "TooltipPreview",
  props: ['content'],
  data() {
    return {

    }
  }
}
</script>

<style lang="scss">

$primary-darkest: #111;
$primary-medium: #ccc;
$primary-light: #eee;
$primary-lightest: #fafafa;

.tooltip {
  margin-left: 8px;
  display: inline-block;
  position: relative;
  background: #fff;
  color: $primary-darkest;
  padding: 0.8em 2em 0.8em 1.2em;
  font-size: 0.9rem;
  line-height: 1.4em;
  border: 1px solid $primary-medium;
  border-radius: 2px;
  box-shadow: 0 0 4px 2px $primary-light;
  white-space: nowrap;

  .close {
    top: 0.4em;
    right: 0.4em;
    position: absolute;
    width: 16px;
    height: 16px;
    color: $primary-medium;
    cursor: pointer;
    background: #fff;

    &:hover {
      color: $primary-darkest;
    }
  }
  .arrow, .arrow::before {
    position: absolute;
    left: -3px;
    top: 50%;
    margin-top: -5px;
    width: 10px;
    height: 10px;
    //z-index: -1;
  }

  .arrow::before {
    content: "";
    background: #fff;
    border-top: 1px solid $primary-medium;
    border-right: 1px solid $primary-medium;
    transform: rotate(-135deg)
  }
  h2, h3, h4 {
    padding: 0;
    margin: 0 0 0.5em 0;
  }
}

</style>