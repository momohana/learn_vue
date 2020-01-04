<template>
  <div> 
    <LikeHeader>
      <template v-slot:title="slotProps">
        <h2>こんにちは</h2>
        <h2>{{ slotProps.user.firstName }}</h2>
      </template>
      <template v-slot:number>
        <h3>{{ number }}</h3>
      </template>
    </LikeHeader>
    <LikeNumber :total-number="number" v-on:my-click="number = $event"></LikeNumber>
    <LikeNumber :total-number="number"></LikeNumber>
    <hr>
    <button @click="currentComponent = 'About'">About</button>
    <button @click="currentComponent = 'Home'">Home</button>
    <keep-alive>
      <component :is="currentComponent"></component>
    </keep-alive> 
    <div>
      <h2>イベントのフォーム</h2>
      <label for="maxNumber">最大人数</label>
      <input
        id="maxNumber"
        type="number"
        v-model.number="eventData.maxNumber"
        >
      <p>{{ eventData.maxNumber }}</p>
    </div> 
  </div>
</template>

<script>
import LikeHeader from './components/LikeHeader.vue'
import About from './components/About.vue'
import Home from './components/Home.vue'

export default {
  data() {
    return {
      number: 10,
      currentComponent: 'Home',
      eventData: {
        maxNumber: 0
      }
    }
  },
  components: {
    LikeHeader,
    About,
    Home
  }
}
</script>
