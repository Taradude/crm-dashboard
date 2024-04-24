<template>
  <div class="person">
    <span>{{ name }}</span>
    <span>{{ company }}</span>
    <span>{{ phone }}</span>
    <span>{{ email }}</span>
    <span>{{ country }}</span>
    <p :class="color">{{ status }}</p>
  </div>
</template>

<script lang="ts">
import { Component, Vue, Prop } from 'vue-property-decorator'

@Component
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
  display: flex;
  flex-direction: row;
  padding: 12px;
  justify-content: space-around;
  text-align: left;
}
.person span,
.person p {
  font-size: 18px;
  flex: 1;
  text-align: center;
}
p.red {
  background-color: rgb(255, 108, 108);
  border-radius: 12px;
  padding: 4px;
}
p.green {
  padding: 4px;
  border-radius: 12px;
  background-color: rgb(112, 249, 112);
}
</style>
