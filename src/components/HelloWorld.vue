<template>
  <div>
    <div class="cardtop">WELCOME TO PLAY GAME</div><br>
    <button @click="randomStart()" class="btn btn-info">Start{{Label}}</button>
    <div class="row">
      <div class="col-6 ">
        <br><button @click="randomSDamage()" class="btn btn-danger ml-3">Special Attack{{Label}}</button>
        <button @click="randomDamage()" class="btn btn-danger ml-3">Attack{{Label}}</button>
      </div>
    </div>
    
    <p v-if="hp1 <= -1 ">
      <img src="https://cdn.discordapp.com/attachments/392353546332405763/746076980524613713/pngegg.png" height="400" width="400"/>
    </p>
    <p v-else-if="hp2 <= -1 ">
      <img src="https://cdn.discordapp.com/attachments/392353546332405763/746080751300247642/pngegg_2.png" height="500" width="500"/>
      
    </p>
    
    

    <div class="row">
      <div class="col-4 ">
        <br><p>{{randomPlayer}}</p>
        <p>HP : {{hp1}}</p> 
        <img :src="image1">
      </div>
      
      <div class="col-4"><br><br>
        <br><br><img src="https://cdn.discordapp.com/attachments/392353546332405763/746090155282006126/pngegg_6.png" height ="150" width="150">
      </div>

      <div class="col-4">
        <br><p>{{randomMonster}}</p>
        <p>HP : {{hp2}}</p>
        <img :src="image2">
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  data: function () {
    return {
      randomPlayerAttack: "",
      randomMonsterAttack: "",
      randomSAttack: "",
      image1:"",
      image2:"",
      hp1:" ",
      hp2:" ",
      
      player: [
        { name: "Bat Man", hp: 180, image: "https://cdn.discordapp.com/attachments/718057277239722058/748758142082613268/Background_6.png" },
        { name: "Captain", hp: 190, image: "https://cdn.discordapp.com/attachments/718057277239722058/748758141155541032/Background_7.png" },
        { name: "Thor",   hp: 200, image: "https://cdn.discordapp.com/attachments/718057277239722058/748758146063007744/Background_3.png" },
      ],
      randomPlayer: "",
 
      monster: [
        { name: "Honey Queen", hp: 205, image: "https://cdn.discordapp.com/attachments/718057277239722058/748758143462408212/Background_5.png" },
        { name: "Thanos", hp: 230, image: "https://cdn.discordapp.com/attachments/718057277239722058/748758151041515550/Background_1.png" },
        { name: "LO KI",  hp: 210, image: "https://cdn.discordapp.com/attachments/718057277239722058/748759308476350534/Background_8.png" },
        { name: "๋Joker",  hp: 220, image: "https://cdn.discordapp.com/attachments/718057277239722058/748758147866427402/Background_2.png" },
      ],
      randomMonster: "",
    };
  },

  props: {
    Label: String,
  },

  methods: {
    randomStart: function () {
      var chosenNumber1 = Math.floor(Math.random() * this.player.length);
      this.randomPlayer = this.player[chosenNumber1].name;
      this.hp1=this.player[chosenNumber1].hp;
      this.image1=this.player[chosenNumber1].image;

      var chosenNumber2 = Math.floor(Math.random() * this.monster.length);
      this.randomMonster = this.monster[chosenNumber2].name;
      this.hp2=this.monster[chosenNumber2].hp;
      this.image2=this.monster[chosenNumber2].image;

    },

    randomDamage: function () {
      this.randomPlayerAttack = Math.max(Math.floor(Math.random() * 10) + 1, 3);
      this.hp2 -= this.randomPlayerAttack

      this.randomMonsterAttack = Math.max(Math.floor(Math.random() * 15) + 1, 5);
      this.hp1 -= this.randomMonsterAttack    
      
      
    },

    randomSDamage: function () {
      this.randomPlayerAttack = Math.max(Math.floor(Math.random() * 20) + 1, 10);
      this.hp2 -= this.randomPlayerAttack

      this.randomMonsterAttack = Math.max(Math.floor(Math.random() * 15) + 1, 5);
      this.hp1 -= this.randomMonsterAttack 
    },
  },
};
</script>

<style>
</style>

  