<template>
  <div class="sc-suggestions-row" :style="{background: colors.messageList.bg}">
    <button
      v-for="(suggestion, idx) in suggestions"
      :key="idx"
      class="sc-suggestions-element"
      :style="{
        borderColor: colors.sentMessage.bg,
        color: colors.sentMessage.bg
      }"
      @click="$emit('sendSuggestion', suggestion)"
    >
      {{ suggestion }}
    </button>
  </div>
</template>

<script>
export default {
  props: {
    suggestions: {
      type: Array,
      default: () => []
    },
    colors: {
      type: Object,
      required: true
    }
  },
  data() {
    return {}
  }
}
</script>

<style>
.sc-suggestions-row {
  text-align: center;
  background: inherit;
  margin-bottom: 10px;
}

.sc-suggestions-element {
  margin: 3px;
  padding: 5px 10px 5px 10px;
  border: 1px solid;
  border-radius: 15px;
  font-size: 14px;
  background: inherit;
  cursor: pointer;
  -webkit-animation: zoomIn 0.5s cubic-bezier(0.42, 0, 0.58, 1);
  animation: zoomIn 0.5s cubic-bezier(0.42, 0, 0.58, 1);
}

/*Animation*/
@-webkit-keyframes zoomIn {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
    opacity: 0;
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
    opacity: 1;
  }
}

@keyframes zoomIn {
  0% {
    -webkit-transform: scale(0);
    transform: scale(0);
    opacity: 0;
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
    opacity: 1;
  }
}
</style>
