<template>
  <div class="landing-page">
    <div class="fullscreen-animation">
      <!-- Animation goes here -->
    </div>
    <div class="content">
      <div class="title animate__animated animate__fadeInDown">开始旅程</div>
      <SmileTwoTone @click="handleIconClick" :class="iconClass" twoToneColor="#88D7EB"/>
    </div>
  </div>
</template>

<script>
import { defineComponent } from 'vue';
import { SmileTwoTone } from '@ant-design/icons-vue';

export default defineComponent({
  data() {
    return {
      iconClass: 'smile animate__animated animate__fadeInUp',  // 初始类名
    };
  },

  components: {
    SmileTwoTone
  },
  methods: {
    handleIconClick() {
      console.log('Icon clicked!');
      // 在这里处理图标的点击事件
      this.iconClass = 'smile animate__animated animate__rubberBand'
    }
  }
});
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+SC:wght@700&display=swap');

.fullscreen-animation {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  z-index: -1;
}
@keyframes color-change {
  0% { background: #E4B7A0; }
  25% { background: #C38370; }
  50% { background: #A45C40; }
  75% { background: #C38370; }
  100% { background: #E4B7A0; } 
}

.fullscreen-animation {
  /* ... */
  animation: color-change 6s ease-in-out infinite;
}

.content {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  text-align: center;
}

.smile {
  margin-top: 0.2em;
  font-size: 72px;
}

.title {
    font-family: 'Noto Sans SC', sans-serif;
    font-size: 48px;
    color: azure;
    letter-spacing: .1em;
    text-shadow: 
      -1px -1px 1px #111, 
      2.5px 2.5px 1px #363636;
}
</style>