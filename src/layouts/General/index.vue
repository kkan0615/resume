<template>
  <main
    class="h-full w-full"
  >
    <div
      class="sm:flex gap-x-2"
    >
      <my-info-general-layout
        class="sm:w-1/4"
      />
      <div
        class="sm:w-3/4"
      >
        <router-view
          v-slot="{ Component }"
        >
          <transition
            name="fade"
            mode="out-in"
          >
            <component :is="Component" />
          </transition>
        </router-view>
      </div>
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent, onMounted } from 'vue'
import useStore from '@/store'
import MyInfoGeneralLayout from '@/layouts/General/components/MyInfo.vue'

export default defineComponent({
  name: 'GeneralLayout',
  components: { MyInfoGeneralLayout },
  setup () {
    const store = useStore()

    return
  }
})
</script>
