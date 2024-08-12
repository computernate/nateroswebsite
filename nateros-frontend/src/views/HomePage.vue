<script>
export default {
  data() {
    return {
      currentEffect: ''
    };
  },
  computed: {
    parentClass() {
      return this.currentEffect;
    }
  },
  methods: {
    setParentEffect(effect) {
      this.currentEffect = effect;
    },
    resetParentEffect() {
      this.currentEffect = '';
    }
  },
  computed: {
  }
};
</script>

<template>
  <div class="allWrapper">
    <h1 class="first">Nathan</h1>
    <div :class="`${currentEffect} gridWrapper`">
      <div
        class="ch-display"
        @mouseover="setParentEffect('ch-focus')"
        @mouseout="resetParentEffect"
      ></div>
      <div
        class="tongues-display"
        @mouseover="setParentEffect('tongues-focus')"
        @mouseout="resetParentEffect"
      ></div>
      <div
        class="doomstop-display"
        @mouseover="setParentEffect('doomstop-focus')"
        @mouseout="resetParentEffect"
      ></div>
      <div
        class="ldsrag-display"
        @mouseover="setParentEffect('ldsrag-focus')"
        @mouseout="resetParentEffect"
      ></div>
      <div
        class="photo-display"
        @mouseover="setParentEffect('photo-focus')"
        @mouseout="resetParentEffect"
      ></div>
    </div>
    <h1>Roskelley</h1>
  </div>
</template>

<style scoped>
/*BASE*/
  .allWrapper{
    width:100%;
    height:100%;
    display:flex;
    justify-content: center;
    align-items: center;
    background-color:black;
  }
  .gridWrapper{
    width:800px;
    height:800px;
    display:grid;
    grid-template-columns:1fr 1fr 1fr;
    grid-template-rows: 1fr 1fr 1fr;
    transition: all 0.25s ease;
  }
  .ch-display{
    background-color:blue;
    grid-column: 1/3;
    grid-row: 1/2;
  }
  .tongues-display{
    background-color:purple;
    grid-column: 3/4;
    grid-row:1/3;
  }
  .doomstop-display{
    background-color:green;
    grid-column: 2/4;
    grid-row: 3/4;
  }
  .ldsrag-display{
    background-color:red;
    grid-row: 2/4;
    grid-column: 1/2;
  }
  .photo-display{
    background-color:orange;
  }
  h1.first{
    color:white;
    transform: rotate(-90deg);
  }
  h1{
    color:white;
    transform: rotate(90deg);
  }


  /*ch-display*/
  .gridWrapper.ch-focus{
    grid-template-rows: 4fr 1fr 1fr;
  }

  /*tongues-display*/
  .gridWrapper.tongues-focus{
    grid-template-columns:1fr 1fr 4fr;
  }

  /*doomstop-display*/
  .gridWrapper.doomstop-focus{
    grid-template-rows: 1fr 1fr 4fr;
  }

  /*ldsrag-display*/
  .gridWrapper.ldsrag-focus{
    grid-template-columns:4fr 1fr 1fr;
  }

  /*photo-display*/
  .gridWrapper.photo-focus{
    grid-template-columns:1fr 3fr 1fr;
    grid-template-rows:1fr 3fr 1fr;
  }

</style>
