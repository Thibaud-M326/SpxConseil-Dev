<template>
    <div id="contactCompDiv">
        <div id="contactDiv">
            <div id="titleDiv">
                <v-icon icon="fas fa-envelope" />
                <h2>
                    {{ $t('contact.contact') }}
                </h2>
            </div>
            <VForm action="#" method="post" id="contactFormContainer" @submit="onSubmit" v-slot="{ errors }">
                <div id="leftFormDiv">
                    <div class="inputError">
                        <ErrorMessage name="lastName"/>
                        <VField type="text" name="lastName" class="inputText" :placeholder="$t('contact.lastName')" :rules="validateLastName"/>
                    </div>
                    
                    <div class="inputError">
                        <ErrorMessage name="firstName"/>
                        <VField type="text" name="firstName" class="inputText" :placeholder="$t('contact.firstName')" :rules="validateFirstName"/>
                    </div>

                    <div class="inputError">
                        <ErrorMessage name="email"/>
                        <VField type="email" name="email" class="inputText" :placeholder="$t('contact.mail')" :rules="validateEmail"/>
                    </div>

                    <div class="inputError">
                        <VField type="telephone" name="phone" class="inputText" :placeholder="$t('contact.phone')" />
                    </div>

                    <div>
                        <textarea name="message" id="yourMessageTextArea" :placeholder="$t('contact.message')"></textarea>
                    </div>
                </div>
                <div id="sendButtonDiv">
                    <button type="submit" id="sendButton">
                        Send
                    </button>
                </div>
            </VForm>
        </div>
    </div>
</template>

<script lang="ts">
import { Form, Field, ErrorMessage } from 'vee-validate'

export default {
    components: {
        VForm: Form,
        VField: Field,
        ErrorMessage,
    },
    methods: {
        onSubmit(values: Object) {
            console.log(JSON.stringify(values, null, 2));
        },
        validateEmail(value: any) {
            if (!value) {
                return 'This field is required'
            }

            const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
            if (!regex.test(value)) {
                return 'This field must be a valid email'
            }

            return true;
        },
        validateLastName(value: any) {
            if (!value) {
                return 'This field is required'
            }
            
            return true
        },
        validateFirstName(value: any) {
            if (!value) {
                return 'This field is required'
            } 

            return true
        },
    },
}
</script>

<style scoped>
#contactCompDiv {
    display: flex;
    justify-content: center;
    align-items: center;
}

#contactDiv {
    width: 90vw;
    height: 60vh;
}

#titleDiv {
    display: flex;
    align-items: center;
    height: 8vh;
    margin-bottom: 1vh;
    margin-top: 2vw;
}

h2 {
    margin-left: 2vw;
}

#contactFormContainer {
    height: 44vh;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: center;
}

#leftFormDiv {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    width: 66vw;
}

.inputError {
    display: flex;
    flex-direction: column;
    justify-content: end;
    width: 32vw;
    height: 10vh;
    color: #972626;
    /* background-color: #93a4db; */
}

.inputText {
    width: 31vw;
    height: 6vh;
    padding: 1vh;
    margin: 0.3vh;
    background-color: #F8F6F2;
    color: #264097;
}

#yourMessageTextArea {
    display: flex;
    
    height: 30vh;
    width: 63.3vw;
    padding: 1vh;
    margin: 0.3vh;
    margin-top: 2vh;
    background-color: #F8F6F2;
    color: #264093;
}

#sendButtonDiv {
    width: 10vw;
    display: flex;
    align-items: end;
}

#sendButton {
    height: 8vh;
    width: 9vw;
    margin: 0.2vh;
    background-color: #F8F6F2;
    color: #3B57B1;
    border:1px solid #264093;
    border-radius: 3px;
}

@media (max-width: 1199px) {

    #leftFormDiv {
        justify-content: center;
        flex-direction: column;
        align-items: baseline;
    }

    .inputText {
        width: 63.3vw;
    }

    #sendButtonDiv {
        width: 66vw;
        justify-content: start;
        margin-top: 2vh;
    }

    #sendButton {
        min-width: 100px;
    }

    #contactFormContainer {
        justify-content: center;
    }
}
</style>