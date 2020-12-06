<template>
  <div class="checkbox-button">
    <label for="" class="label" />
    <input
      type="checkbox"
      :checked="isChecked"
      v-model="checked"
      @change="$emit('mark-completed', checked)"
    />
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

/* .checkbox {
} */
</style>
