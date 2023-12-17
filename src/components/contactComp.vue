<template>
    <div id="contactCompDiv">
        <div id="contactDiv">
            <div id="contactTitleDiv">
                <v-icon icon="fas fa-envelope" />
                <h2>
                    {{ $t('contact.contact') }}
                </h2>
            </div>
            <div id="formDiv">
                <VForm action="https://formspree.io/f/xpzgvgwa" method="post" id="contactFormContainer" @submit="onSubmit">
                    <div id="leftFormDiv">
                        <div class="inputDiv">
                            <ErrorMessage name="lastName" class="inputError"/>
                            <VField type="text" name="lastName" class="inputText" :placeholder="$t('contact.lastName')" :rules="validateLastName"/>
                        </div>
                        
                        <div class="inputDiv">
                            <ErrorMessage name="firstName" class="inputError"/>
                            <VField type="text" name="firstName" class="inputText" :placeholder="$t('contact.firstName')" :rules="validateFirstName"/>
                        </div>

                        <div class="inputDiv">
                            <ErrorMessage name="email" class="inputError"/>
                            <VField type="email" name="email" class="inputText" :placeholder="$t('contact.mail')" :rules="validateEmail"/>
                        </div>

                        <div class="inputDiv">
                            <VField type="telephone" name="phone" class="inputText" :placeholder="$t('contact.phone')" />
                        </div>

                        <div>
                            <textarea name="message" id="yourMessageTextArea" :placeholder="$t('contact.message')"></textarea>
                        </div>
                    </div>
                    <div id="sendButtonDiv">
                        <button type="submit" id="sendButton">
                            {{ $t('contact.send') }}
                        </button>
                    </div>
                </VForm>
            </div>
        </div>
    </div>
    <div id="colorBoxDiv">
        <!-- just a colored box -->
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
                return this.$t('contact.fieldRequired')
            }

            const regex = /^[A-Z0-9._%+-]+@[A-Z0-9.-]+\.[A-Z]{2,4}$/i;
            if (!regex.test(value)) {
                return this.$t('contact.fieldValidEmail')
            }
            return true;
        },
        validateLastName(value: any) {
            if (!value) {
                return this.$t('contact.fieldRequired')
            }
            return true
        },
        validateFirstName(value: any) {
            if (!value) {
                return this.$t('contact.fieldRequired')
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
}

#contactTitleDiv {
    display: flex;
    align-items: center;
    height: 8vh;
    margin-bottom: 1vh;
    margin-top: 2vw;
}

h2 {
    margin-left: 2vw;
}

#formDiv{
    height: 57vh;
    margin-bottom: 10vh;
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

.inputDiv {
    display: flex;
    flex-direction: column;
    justify-content: end;
    width: 32vw;
    height: 10vh;
    color: #972626;
}

.inputError {
    font-size: small;
    margin-left: 1vw;
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
    margin-top: 4vh;
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

#colorBoxDiv {
    height: 6vh;
    background-color: #E3D1E6;
}

@media (max-width: 1199px) {
    #formDiv{
        height: 82vh;
        margin-bottom: 10vh;
    }

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