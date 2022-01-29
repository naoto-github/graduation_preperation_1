<template>
    <v-ons-page>
      <v-ons-toolbar>
        <div class="center">{{ title }}</div>
        <div class="right">
          <v-ons-toolbar-button>
            <v-ons-icon icon="ion-navicon, material: md-menu"></v-ons-icon>
          </v-ons-toolbar-button>
        </div>
      </v-ons-toolbar>
      <div style="text-align: center; padding-top:10px">{{ question }}</div>
      <p style="text-align: center">
        <v-ons-button @click="wrongDialog=true">A型</v-ons-button>
        <v-ons-button @click="wrong">B型</v-ons-button>
        <v-ons-button @click="correct">O型</v-ons-button>
        <v-ons-button @click="wrong">AB型</v-ons-button>
      </p>

      <v-ons-dialog cancelable :visible.sync="correctDialog">
        <p style="text-align: center">正解!</p>
      </v-ons-dialog>

      <v-ons-dialog cancelable :visible.sync="wrongDialog">
        <p style="text-align: center">不正解</p>
      </v-ons-dialog>
    </v-ons-page>

</template>
<script>
  export default{
    data() {
      return {
        title: 'クイズ',
        question: '向の血液型は？',
        correctDialog: false,
        wrongDialog: false
      };
    },
    methods: {
      correct() {
        //this.$ons.notification.alert('正解！');
        this.correctDialog = true;
      },
      wrong(){
        //this.$ons.notification.alert('不正解');
        this.wrongDialog = true;
      }
    }
  };
</script>
