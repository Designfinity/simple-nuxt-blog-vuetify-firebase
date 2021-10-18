<template>
  <div :class="['app-label', classes]">
    <slot name="default" />
  </div>
</template>

<script>
export default {
  name: 'AppLabel',
  props: {
    color: {
      type: String,
      default: "",
    },
    size: {
      type: String,
      default: "",
    },
    rounded: {
      type: Boolean,
      default: false,
    },
  },
  computed: {
    classes(): any {
      return {
        "app-label":
          true,
        "app-label--rounded": this.rounded,
        "app-label--info": this.color === "info",
        "app-label--success": this.color === "success",
        "app-label--warning": this.color === "warning",
        "app-label--danger": this.color === "danger",
        "app-label--gray": this.color === "gray",
        "app-label--sm": this.size === "sm",
        "app-label--xs": this.size === "xs",
      };
    },
  },
}
</script>
<style lang="scss">
.app-label {
  &--info {
    @apply bg-blue-100 text-blue-800;
  }
  &--success {
    @apply bg-green-100 text-green-800;
  }
  &--warning {
    @apply bg-yellow-100 text-yellow-800;
  }
  &--danger {
    @apply bg-red-100 text-red-800;
  }
  &--gray {
    @apply bg-gray-400 text-white;
  }
  &--rounded {
    @apply rounded-full;
  }
  &--sm {
    padding: 3px 8px;
  }
  &--xs {
    padding: 2px 8px;
  }
}
</style>
