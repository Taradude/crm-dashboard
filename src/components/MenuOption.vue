<template>
  <div class="option">
    <span>{{ text1 }}</span>
    <span>></span>
  </div>
</template>

<script lang="ts">
import { Vue, Prop } from 'vue-property-decorator'

export default class MenuOption extends Vue {
  @Prop({ default: '' }) text1!: string
}
</script>

<style scoped lang="scss"></style>
