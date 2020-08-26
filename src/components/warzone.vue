<template>
  <div>
    <div id="example-1">
      <button @click="randomplay()" class="btn btn-dark">START</button>
    </div>
    <br />
    <br />
    <button v-bind:disabled="end" @click="randomdamage()" class="btn btn-danger">ATTACK</button>
    <br />
    <br />
    <div>
      <button v-bind:disabled="end" @click="randomspdamage()" class="btn btn-danger">SPECIAL ATTACK</button>
    </div>
    <div class="row text-danger">
      <div class="col-sm">
        <p>{{hpplayer}}</p>
        <p>{{nameplayer}}</p>
        <img :src="phoplayer" :height="hpplayer" />
      </div>
      <div class="col-sm">
        <br />
        <br />
        <img
          src="https://cdn.discordapp.com/attachments/709406382134263882/748051493784911972/pngegg_3.png"
        />
        <br />
        <br />
        <br />
        <p v-if="hpplayer<=0 & hpmonster<=0">Draw</p>
        <p v-else-if="hpmonster<=0">PLAYER WIN</p>
        <p v-else-if="hpplayer<=0">MONSTER WIN</p>
      </div>
      <div class="col-sm">
        <p>{{hpmonster}}</p>
        <p>{{namemonster}}</p>
        <img :src="phomonster" :height="hpmonster" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      randomNo1: "",
      randomNo2: "",
      hpplayer: "1",
      hpmonster: "1",
      phoplayer: "",
      phomonster: "",
      nameplayer: "",
      namemonster: "",
      damageplayer: "",
      damagemonster: "",
      end: false,

      player: [
        {
          name: "Naruto",
          Hp: 300,
          image:
            "https://cdn.discordapp.com/attachments/748191031870226462/748200133598117928/1.png",
        },
        {
          name: "Sasuke",
          Hp: 250,
          image:
            "https://cdn.discordapp.com/attachments/748191031870226462/748200653020725348/2.png",
        },
        {
          name: "Sakura",
          Hp: 200,
          image:
            "https://cdn.discordapp.com/attachments/748191031870226462/748199994200162323/3.png",
        },
      ],
      //play[1].hp -=20
      Monster: [
        {
          name: "Kisame",
          Hp: 300,
          image:
            "https://cdn.discordapp.com/attachments/748191031870226462/748200041612705842/4.png",
        },
        {
          name: "Hidan",
          Hp: 250,
          image:
            "https://cdn.discordapp.com/attachments/748191031870226462/748199749529763982/5.png",
        },
        {
          name: "Kakuzu",
          Hp: 200,
          image:
            "https://cdn.discordapp.com/attachments/748191031870226462/748203321080414419/pngegg_5.png",
        },
      ],
    };
  },
  props: {
    lable: String,
  },
  methods: {
    randomplay: function () {
      this.randomNo1 = Math.max(Math.floor(Math.random() * this.player.length));
      this.phoplayer = this.player[this.randomNo1].image;
      this.hpplayer = this.player[this.randomNo1].Hp;
      this.nameplayer = this.player[this.randomNo1].name;
      this.randomNo2 = Math.max(
        Math.floor(Math.random() * this.Monster.length)
      );
      this.phomonster = this.Monster[this.randomNo2].image;
      this.hpmonster = this.Monster[this.randomNo2].Hp;
      this.namemonster = this.Monster[this.randomNo2].name;
      this.end = false;
    },
    randomdamage: function () {
      this.damageplayer = Math.max(Math.floor(Math.random() * 10) + 1, 3);
      this.hpmonster -= this.damageplayer;

      this.damagemonster = Math.max(Math.floor(Math.random() * 15) + 1, 5);
      this.hpplayer -= this.damagemonster;
      if ((this.hpplayer <= 0) & (this.hpmonster <= 0)) {
        this.hpplayer = 0;
        this.hpmonster = 0;
        this.end = true;
      } else if (this.hpplayer <= 0) {
        this.hpplayer = 0;
        this.end = true;
      } else if (this.hpmonster <= 0) {
        this.hpmonster = 0;
        this.end = true;
      }
    },
    randomspdamage: function () {
      this.damageplayer = Math.max(Math.floor(Math.random() * 20) + 1, 10);
      this.hpmonster -= this.damageplayer;

      this.damagemonster = Math.max(Math.floor(Math.random() * 15) + 1, 5);
      this.hpplayer -= this.damagemonster;
      if ((this.hpplayer <= 0) & (this.hpmonster <= 0)) {
        this.hpplayer = 0;
        this.hpmonster = 0;
        this.end = true;
      } else if (this.hpplayer <= 0) {
        this.hpplayer = 0;
        this.end = true;
      } else if (this.hpmonster <= 0) {
        this.hpmonster = 0;
        this.end = true;
      }
    },
  },
};
</script>
<style>
</style>