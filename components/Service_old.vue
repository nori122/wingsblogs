<template>
  <v-container fluid class="primary--text">
    <v-row align="center" justify="center" class="ma-2 my-6"
      ><v-col>
        <v-row>
          <v-col> <h1>サービスの流れ</h1></v-col></v-row
        >
        <v-row>
          <v-col>
            <v-card>
              <v-card-title>1. 翻訳のお申し込み</v-card-title>
              <v-img align="center" class="pa-3">
                <img class="service-image" src="../assets/img/contact.svg"
              /></v-img>
              <v-card-text
                >コンタクトフォームからお申し込みください。</v-card-text
              >
            </v-card>
            <v-row align="center" justify="center" class="py-8"
              ><v-icon size="30">mdi-arrow-down-thick</v-icon></v-row
            >
            <v-card align="center">
              <v-card-title>2. 機械翻訳を実施</v-card-title>
              <v-img class="service-image pa-3" src="img/mt.svg" />
              <v-card-text>DeepLを使用して機械翻訳を行います。</v-card-text>
            </v-card>
            <v-row align="center" justify="center" class="py-8"
              ><v-icon size="30">mdi-arrow-down-thick</v-icon></v-row
            >
            <v-card>
              <v-card-title>3. ネイティブチェック</v-card-title>
              <v-img align="center" class="pa-3">
                <img class="service-image" src="../assets/img/check.svg"
              /></v-img>
              <v-card-text
                >英語を母語とするネイティブスピーカーにより、より自然な英語へと校正します。</v-card-text
              >
            </v-card>
            <v-row align="center" justify="center" class="py-8"
              ><v-icon size="30">mdi-arrow-down-thick</v-icon></v-row
            >
            <v-card>
              <v-card-title>4. 翻訳完了</v-card-title>
              <v-img align="center" class="pa-3">
                <img class="service-image" src="../assets/img/done.svg"
              /></v-img>
              <v-card-text
                >翻訳されたコンテンツをお渡しします。Mediumや、Indiehackersに投稿したり、ご自身のブログに掲載し、世界中の話者へ届けましょう。</v-card-text
              >
            </v-card>
          </v-col>
        </v-row>
      </v-col></v-row
    >
  </v-container>
</template>

<script>
export default {}
</script>
<style scoped>
.service-image {
  width: 60%;
}
</style>
