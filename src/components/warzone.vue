<template>
  <div>
    <div id="example-1">
      <button @click="randomDamage(0,100)" class="btn btn-dark">START</button>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      counter: 0,
      fsize: 50,
      randomNo: 0,
      player: [
          {name: 'Naruto', Hp: 300, image:'https://www.clipartkey.com/view/bTiJih_naruto-ashura-png-clipart-last-sasuke'},
          {name: 'Sasuke', Hp: 250, image:''},
          {name: 'Sakura', Hp: 200, image:''},
      ],
      //play[1].hp -=20
      Monster: [
          {name: '', Hp: 300, image:''},
          {name: '', Hp: 250, image:''},
          {name: '', Hp: 200, image:''},
      ],
    };
  },
  props: {
    lable: String,
  },
  methods: {
      randomDamage: function(min, max) {            
    this.randomNo = Math.max(Math.floor(Math.random() * max) + 1, min);
     },
    },
};
</script>
<style>
</style>