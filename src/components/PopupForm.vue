<template>  
    <div>
        <v-dialog v-model="dialog" width="400">     
            <template v-slot:activator="{ on, attrs }">
                <v-btn  
                        v-bind="attrs"
                        v-on="on"
                        width="120"
                        color="rgb(255, 160, 192)"
                        v-if="!load"
                        v-show="show"
                >
                <div class="text-white">Get Review</div>
                    
                </v-btn> 
            </template>

            <v-card class="pt-4"> 
                <v-card-title>
                    <h2>Enter Details</h2>
                </v-card-title> 

                <v-card-text>
                    <v-form>
                        <v-text-field label="title" 
                                      outlined
                                      @input="[emitData('booktitle', $event)]"
                        >
                        </v-text-field>
                    </v-form>  
                </v-card-text>    
                            
                <v-card-text>
                    <v-form>
                        <v-text-field label="author" 
                                      outlined 
                                      @input="[emitData('bookauthor', $event)]"                   
                        >
                        </v-text-field>
                    </v-form>   
                </v-card-text>
                
                <v-card-text>
                    <v-form>
                        <v-text-field label="isbn" 
                                      outlined
                                      @input="[emitData('bookisbn', $event)]"
                        >
                        </v-text-field>
                    </v-form>  
                </v-card-text> 
                    
                <v-card-actions>
                    <v-spacer></v-spacer>
                    <v-btn 
                        class="button"
                        text
                        outlined
                        @click="submit"
                        color="rgb(255, 160, 192)"
                    >         
                        Submit
                    </v-btn>   
                </v-card-actions>
            </v-card>      
        </v-dialog>   
    </div>     
    
</template>

<script>
    export default {
        props: {
            load: {
                type: Boolean
            }
        },
        data: () => {
            return {
                dialog:false, 
                show:true 
            }
        }, 
        
        methods: {
            emitData(label, value) {
                this.$emit('input-update', { label, value })
            },
            submit() {
                this.dialog = false;
                this.$emit('submit')
            }
        }
    }
</script>

<style>
    .button,h2 {
        font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;    
    }    
</style>