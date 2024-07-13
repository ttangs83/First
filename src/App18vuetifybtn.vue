<template>
  <v-app>
    <v-btn color="success" > success </v-btn> &nbsp;
    <v-btn color="error">error</v-btn> &nbsp;
    <v-btn color="warning">warning</v-btn> &nbsp;
    <v-btn color="info">info</v-btn> &nbsp;
    
    <div class ="text-xs-center">
      <v-btn color="secondary">secondary</v-btn> &nbsp;
      <v-btn color="blue-grey">blue-grey</v-btn> &nbsp;
      <v-btn color="blue">blue</v-btn> &nbsp;
      <v-btn color="red">red</v-btn> &nbsp;
    </div>
    
    <div> 

      <v-btn icon="$vuetify" color="red">저장</v-btn>
      <v-btn icon="$vuetify" color="blue">삭제</v-btn>
      <v-btn icon="$vuetify" color="green">취소</v-btn>

    </div>


  <v-container>
    <v-row align="center" justify="center">
      <v-col cols="auto">
        <v-btn density="compact" icon="mdi-minus"></v-btn>
      </v-col>

      <v-col cols="auto">
        <v-btn density="comfortable" icon="$vuetify"></v-btn>
      </v-col>

      <v-col cols="auto">
        <v-btn density="default" icon="mdi-open-in-new"></v-btn>
      </v-col>
    </v-row>
  
  </v-container>
  </v-app>


</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
}
</script>
