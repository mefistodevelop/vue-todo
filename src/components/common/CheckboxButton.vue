<template>
  <div class="checkbox-button">
    <label class="label">
      <input
        class="checkbox"
        type="checkbox"
        :checked="isChecked"
        v-model="checked"
        @change="$emit('mark-completed', checked)"
      />
      <div class="checkmark" />
    </label>
  </div>
</template>

<script>
export default {
  name: 'Checkbox',
  props: {
    isChecked: {
      type: Boolean,
      default: false,
    },
  },
  data() {
    return {
      checked: this.isChecked,
    };
  },
};
</script>

<style scoped>
.checkbox-button {
  max-width: 2.75rem;
  width: 100%;
  max-height: 2.75rem;
  height: 100%;
}

.label {
  position: relative;
  width: 100%;
  cursor: pointer;
}

.label::before {
  content: '';
  position: absolute;
  top: -0.55rem;
  left: -0.625rem;
  width: 1.5rem;
  height: 1.5rem;
  border: 1px solid #757575;
  border-radius: 4px;
}

.checkmark::before {
  content: '\2713';
  display: none;
  position: absolute;
  top: -0.85rem;
  left: -0.625rem;
  width: 1.5rem;
  height: 1.5rem;
  color: #00c853;
  font-size: 1.5rem;
  font-weight: 700;
}

.checkbox {
  position: absolute;
  top: 0;
  left: 0;
  width: 0;
  height: 0;
  opacity: 0;
  cursor: pointer;
}

.checkbox:checked ~ .checkmark::before {
  display: block;
}
</style>
