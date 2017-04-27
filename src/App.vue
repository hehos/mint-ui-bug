<template>
  <div id="app">

    <mt-tab-container v-model="selected">

      <mt-tab-container-item id="1">

        <mt-cell-swipe
          class="margin-b-10"
          :right="rightBtnConfig()"
          v-for="n in 10" title="swipe me tab1" :key="n">
        </mt-cell-swipe>

      </mt-tab-container-item>

      <mt-tab-container-item id="2">

        <mt-cell-swipe
          class="margin-b-10"
          :right="rightBtnConfig()"
          v-for="n in 10" title="swipe me tab2" :key="n">
        </mt-cell-swipe>

      </mt-tab-container-item>

      <mt-tab-container-item id="3">

        <mt-cell-swipe
          class="margin-b-10"
          :right="rightBtnConfig()"
          v-for="n in 10" title="swipe me tab3" :key="n">
        </mt-cell-swipe>

      </mt-tab-container-item>

    </mt-tab-container>


    <mt-tabbar v-model="selected" fixed>
      <mt-tab-item id="1">
        <i class="icon-certification-o" slot="icon"></i>
        tab1
      </mt-tab-item>
      <mt-tab-item id="2">
        <i class="icon-users2-o" slot="icon"></i>
        tab2
      </mt-tab-item>
      <mt-tab-item id="3">
        <i class="icon-users2-o" slot="icon"></i>
        tab3
      </mt-tab-item>
    </mt-tabbar>

  </div>
</template>

<script>
import Hello from './components/Hello'

export default {
  name: 'app',
  data() {
    return {
      selected: '2',
    }
  },
  created() {

    this.rightBtnConfig = function () {
      return [
        {
          content: '删除',
          style: { background: 'red', color: '#fff' },
//            handler: () => {
//              this.$messagebox.confirm('确定删除?').then(action => {
//              });
//            }
          handler: () => this.$messagebox('delete')
        }
      ];
    }
  },
  components: {
    Hello
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
