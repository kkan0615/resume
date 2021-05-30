<template>
  <nav
    class="flex items-center h-12 px-2 w-full sm:h-12"
    :class="wrapperClasses"
  >
    <slot />
  </nav>
</template>

<script lang="ts">
import { computed, defineComponent } from 'vue'

export default defineComponent({
  name: 'TAppbar',
  props: {
    width:{
      required: false,
      type: Number,
      default: 16,
    },
    height:{
      required: false,
      type: Number,
      default: 12,
    },
    color:{
      required: false,
      type: String,
      default: 'app-bar',
    },
    textColor:{
      required: false,
      type: String,
      default: '',
    },
  },
  setup (props) {
    const wrapperClasses = computed(() =>{
      return {
        // [`w-${props.width}`]: true,
        [`h-${props.height}`]: true,
        [`bg-${props.color}`]: true,
        [`text-${props.textColor}`]: !!props.textColor,
      }
    })

    return {
      wrapperClasses,
    }
  }
})
</script>
