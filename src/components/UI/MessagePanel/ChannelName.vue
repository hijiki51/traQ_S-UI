<template>
  <div :class="$style.path" :data-is-title="isTitle">
    {{ path }}
  </div>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  name: 'ChannelName',
  props: {
    path: {
      type: String,
      required: true
    },
    isTitle: {
      type: Boolean,
      default: false
    }
  },
  setup() {
    return {}
  }
})
</script>

<style lang="scss" module>
.path {
  @include color-ui-secondary;
  @include size-body2;
  overflow: hidden;
  text-overflow: ellipsis;
  white-space: nowrap;

  &[data-is-title] {
    @include color-ui-primary;
    @include size-body1;
    font-weight: bold;

    display: -webkit-box;
    -webkit-line-clamp: 2;
    -webkit-box-orient: vertical;
    white-space: normal;
    word-break: break-all;
  }
  &::before {
    content: '# ';
  }
}
</style>
