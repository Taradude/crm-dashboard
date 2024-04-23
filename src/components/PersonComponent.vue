<template>
  <div class="person">
    <span>{{ name }}</span>
    <span>{{ company }}</span>
    <span>{{ phone }}</span>
    <span>{{ email }}</span>
    <span>{{ country }}</span>
    <StatusComponent :color="color" :status="status" />
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'
import StatusComponent from './StatusComponent.vue'

@Component({
  components: {
    StatusComponent,
  },
})
export default class PersonComponent extends Vue {
  @Prop({ default: '' }) name!: string
  @Prop({ default: '' }) email!: string
  @Prop({ default: '' }) phone!: number
  @Prop({ default: '' }) company!: string
  @Prop({ default: '' }) country!: string
  @Prop({ default: '' }) color!: string
  @Prop({ default: '' }) status!: string
}
</script>

<style scoped lang="scss">
.person {
  padding: 12px;
  display: flex;
  flex: 1;
  flex-direction: row;
  justify-content: space-around;
}
</style>
