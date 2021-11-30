<template>
  <button
    :type="type"
    class="inline-flex items-center justify-center px-2 sm:px-4 font-semibold leading-5 text-white transition duration-150 ease-in-out border border-transparent rounded-md focus:outline-none focus:border-blue-300 focus:shadow-outline-blue active:bg-blue-700 group disabled:cursor-not-allowed"
    :class="[
      color === 'secondary'
        ? 'bg-gray-200 text-blue-500 disabled:text-gray-400 hover:bg-gray-100 disabled:bg-gray-100 '
        : color === 'yellow'
        ? 'bg-yellow-500 hover:bg-yellow-400 text-dark-blue-500'
        : 'bg-blue-500 hover:bg-blue-400 text-white disabled:bg-blue-400 disabled:opacity-75',
      size === 'small' ? 'text-sm leading-5 py-2' : ' leading-6 py-3',
      fontSize,
    ]"
    :disabled="disabled"
    :name="name"
    @click="callback($event)"
  >
    <!-- <progress-circular
      v-if="loading"
      :color="color === 'secondary' ? 'text-blue-500' : 'text-white'"
      class="mr-2"
    /> -->
    <span>
      <slot name="icon" />
    </span>
    <span>{{ title }}</span>
  </button>
</template>
<script>
export default {
  name: 'CustomButton',
  props: {
    title: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: 'button',
    },
    color: {
      type: String,
      default: 'primary',
    },
    loading: {
      type: Boolean,
      default: false,
    },
    size: {
      type: String,
      default: '',
    },
    fontSize: {
      type: String,
      default: 'text-sm',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    name: {
      type: String,
      default: '',
    },
  },
  methods: {
    callback() {
      this.$emit('click')
    }
  },
  emits: ['click']
}
</script>