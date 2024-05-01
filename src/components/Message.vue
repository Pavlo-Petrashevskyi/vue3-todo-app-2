<script>
export default {
  name: 'Message',
  props: {
    active: Boolean,
  },
  emits: ['hide'],
  methods: {
    hide() {
      this.$emit('hide');
    },
  }
}
</script>

<template>
  <article class="message"
    :class="{'message--hidden': !active}">
    <div class="message-header">
      <slot name="header"></slot>
      <button class="delete" @click="hide"></button>
    </div>

    <div class="message-body">
      <slot :x="1">Message</slot>
    </div>
  </article>
</template>