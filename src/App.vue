<template>
  <div id="app">
    <div class="first" v-if="isFirstDisplay">
      <a-card
        hoverable
        style="width: 300px;margin-top: 60px;margin-left: 60px; "
        v-on:click="isFirstDisplay = false"
      >
        <img slot="cover" alt="example" src="./assets/logoImg.jpg" />

        <div
          style="overflow: hidden;
    color: rgba(0,0,0,.85);
    font-weight: 500;
    font-size: 16px;
    white-space: nowrap;
    text-overflow: ellipsis;"
        >
          Gift for Dr.ZHAO Chen
        </div>
        <div>by 张卓韧</div>
      </a-card>
    </div>
    <div class="second" v-if="!isFirstDisplay">
      <a-row style="height: 100%">
        <a-col :span="8" style="background-color:#f0f0f0;height: 100%;padding-top: 60px;">
          <a-radio-group v-model="value" @change="onChange">
            <template v-for="(item) in list">
            <a-radio  :value="{item}" :key="item">
              {{item}}
            </a-radio>

            </template>
            <a-radio :value="2">
              Option B
            </a-radio>
            <a-radio :value="3">
              Option C
            </a-radio>
          </a-radio-group>
        </a-col>
        <a-col :span="16">
          col-12
        </a-col>
      </a-row>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  data() {
    return {
      list: ['asd', 'sdff'],
      isFirstDisplay: true,
      value: null,
      onChange: null,
    };
  },
  name: "App",
  onChange(e){
    console.log(e);
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100%;
}
.ant-card-body {
  background-color: #f0f0f0;
}
.second {
  margin: 0% 15%;
  height: 100%;
}
.ant-radio-wrappero{
  margin: 7px;
}
.radioStyle{
  display: block;
    height: 30px;
    line-height: 30px;
}
</style>
