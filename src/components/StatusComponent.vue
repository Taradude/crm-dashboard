<template>
  <div class="status" :class="{ color }">
    <span> {{ status }}</span>
  </div>
</template>

<script lang="ts">
import { Vue, Prop } from 'vue-property-decorator'

export default class StatusComponent extends Vue {
  @Prop({ default: '' }) status!: string
  @Prop({ default: '' }) color!: string
}
</script>

<style scoped lang="scss">
.status {
  padding: 8px;
  border-radius: 12px;
}
.red {
  background-color: red;
}
.green {
  background-color: green;
}
</style>
