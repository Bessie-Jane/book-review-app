<template>        
    <div class="parent">
        <div class="holder">

            <div>
                <!-- <div mdi-email-box>Email</div> -->
                <v-icon medium
                        color="grey darken-2"     
                > 
                    mdi-email-outline
                </v-icon>
            </div> 
            
            <div class="verification">
                <h2 class="font-weight-bold">Verification Email</h2>
            </div>
            
            <div class="message">
                <p class="font-size-13
                            text-body-2"
                >
                    Thank you for signing up to use Enum. <br>
                    Folow the link to log into your <br> 
                    Enum account and we hope you enjoy using Enum.
                </p>
            </div>

            <button class='bg blue 
                            rounded-lg
                            pa-3
                            white--text
                            mb-2'
            > 
                Verify Email
            </button>    
        </div>   
    </div>
     
</template>

<script>

export default {

}
</script>

<style>
    .parent {    
        align-self: center;
        border: 1px solid black;
        margin-top: 50px;
        padding: 15px;
        border-radius: 10px;
    }

    .holder {
        display: flex;
        flex-direction: column;
        align-content: center;
        margin: 10px;
    }

    .verification {
        margin-top: 20px;
    }

    .message {
        margin-top: 10px;
        margin-bottom: 15px;

    }

    /* p {
        font-size: 13px;
    } */


</style>