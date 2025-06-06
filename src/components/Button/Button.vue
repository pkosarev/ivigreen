<template>
  <button
    :class="[
      'btn',
      `btn--${variant}`,
      `btn--${size}`,
      { 'btn--disabled': disabled, 'btn--full-width': fullWidth }
    ]"
    :disabled="disabled"
    :type="type"
    @click="handleClick"
  >
    <slot></slot>
    <span v-if="$slots.icon" class="btn__icon">
      <slot name="icon"></slot>
    </span>
  </button>
</template>

<script setup lang="ts">
import type { PropType } from 'vue';

const props = defineProps({
  variant: {
    type: String as PropType<'primary' | 'secondary' | 'outline' | 'text' | 'text-dark'>,
    default: 'primary',
    validator: (value: string) =>
      ['primary', 'secondary', 'outline', 'text', 'text-dark'].includes(value)
  },
  size: {
    type: String as PropType<'small' | 'medium' | 'large' | 'adaptive'>,
    default: 'medium',
    validator: (value: string) =>
      ['small', 'medium', 'large', 'adaptive'].includes(value)
  },
  disabled: {
    type: Boolean,
    default: false
  },
  fullWidth: {
    type: Boolean,
    default: false
  },
  type: {
    type: String as PropType<'button' | 'submit' | 'reset'>,
    default: 'button'
  }
});

const emit = defineEmits<{
  (e: 'click', event: MouseEvent): void
}>();

const handleClick = (event: MouseEvent) => {
  if (!props.disabled) {
    emit('click', event);
  }
};
</script>

<style>
  .btn {
    padding: 1.156rem;
    font-size: 16px;
    font-weight: 700;
    line-height: 120%;
    width: 100%;
    height: 56px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    border-color: transparent;
    @media (min-width: 990px) {
      font-size: 20px;
    }
  }
  .btn--primary {
    background-color: #32CD7A;
    color: #fff;
  }
  .btn--text {
    border: none;
    background-color: transparent;
    color: #fff;
  }
  .btn--text-dark {
    border: none;
    background-color: transparent;
    color: #2C2C2C;
  }
  .btn--full-width {
    width: 100%;
  }
  .btn--medium {
    width: 260px;
  }
  .btn--adaptive {
    width: 100%;
    @media (min-width: 990px) {
      width: 260px !important;
      height: 56px;
    }
  }
</style>
