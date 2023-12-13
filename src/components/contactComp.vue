<template>
    <div id="contactCompDiv">
        <div id="contactDiv">
			<div id="titleDiv">
				<v-icon icon="fas fa-envelope" />
				<h2>
					{{ $t('contact.contact') }}
				</h2>
			</div>
            <form action="https://formspree.io/f/xpzgvgwa" method="post" id="contactFormContainer">
                <div id="leftFormDiv">
                    <input type="text" name="lastName" id="lastName" class="inputText" :placeholder="$t('contact.lastName')" required>
                    <input type="text" name="firstName" id="firstName" class="inputText" :placeholder="$t('contact.firstName')" required>
                    <input type="email" name="email" id="email" class="inputText" :placeholder="$t('contact.mail')" required>
                    <input type="telephone" name="phone" id="email" class="inputText" :placeholder="$t('contact.phone')">
                    <textarea name="message" id="yourMessageTextArea" :placeholder="$t('contact.message')" required></textarea>
                </div>
                <div id="sendButtonDiv">
                    <button type="submit" id="sendButton">
                        Send
                    </button>
                </div>
            </form>
        </div>
    </div>
</template>

<script lang="ts">
export default {

}
</script>

<style scoped>

#contactCompDiv {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 75vh;
}

#contactDiv {
	width: 90vw;
	height: 60vh;
}

#titleDiv {
	display: flex;
	align-items: center;
	height: 8vh;
    margin-bottom: 4vh;
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
    width: 66vw;
}

.inputText {
    width: 32vw;
    height: 6vh;
    padding: 1vh; 
    margin: 0.3vh;
    background-color: #F8F6F2;
    color: #264097;
}

#yourMessageTextArea {
    height: 30vh;
    width: 64.3vw;
    padding: 1vh; 
    margin: 0.3vh;
    background-color: #F8F6F2;
    color: #264097;
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
}

@media (max-width: 1199px) {
    .inputText {
        width: 64.3vw;
    }

    #sendButtonDiv {
        width: 66vw;
        justify-content: end;
    }

    #sendButton {
        min-width: 100px;
    }

    #contactFormContainer {
        justify-content: center;
    }
}
</style>