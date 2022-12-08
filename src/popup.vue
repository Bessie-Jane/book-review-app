<template>
  <v-dialog v-model="dialog" width="500px">    
      <template v-slot:activator = "{ on, attrs }">
            <v-btn
                color="red"
                dark
                v-bind = "attrs"
                v-on = "on" 
                width="150"
            >
                Pop this
            </v-btn> 
      </template> 
        
      <v-card>
          <v-card-title>
              <h3> A pop-up </h3>
          </v-card-title>
          <v-card-text>
              <v-form class="px-3">
                    <v-text-field label="title" 
                                  outlined
                                  v-model="title"
                    >
                    </v-text-field>
              </v-form>
           </v-card-text>
           
            <v-card-actions>
                <v-spacer></v-spacer> 
                <v-btn 
                    color="primary"
                    text
                    outlined
                    @click="dialog = false"
                >
                    Submit
                </v-btn>  
            </v-card-actions>
      </v-card>
  </v-dialog>
</template>

<script>
export default {
    data: () => {
        return {
            dialog: false
        }
    }
}
</script>

<style>

</style>