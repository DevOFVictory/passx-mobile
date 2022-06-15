<template>
<Page actionBarHidden="true">
    
    <Gridlayout class="coverImage" rows="*" columns="*">
        <Stacklayout class="mainContainer">
            <label fontSize="24px" textWrap="true" horizontalAlignment="center" style="text-align: center;">
                    <FormattedString>
                        <Span text="Pass" color="white"/>
                        <Span text="X" color="#10a889" fontWeight="bold"/>
                    </FormattedString>
            </label>
            <Label text="A safe place for all your passwords!" fontSize="16px" color="white" horizontalAlignment="center"/>


            <Stacklayout class="inputbox">
                <Label text="Username" class="inputs label"/>
                <TextField id="username-input" hint="Enter Username" placeholderColor="white" autocorrect="false" autocapitalizationType="none" class="inputFields"/>

                <Label text="Password" class="inputs label password"/>
                <TextField id="password-input" hint="Enter Password" placeholderColor="white" secure="true" autocorrect="false" autocapitalizationType="none" class="inputFields"/>
                <Label text="Create a new account" horizontalAlignment="right" paddingRight="15" fontSize="14" color="rgb(120, 120, 120)"/>
            </Stacklayout>


            <!-- Login Button -->
            <Stacklayout marginTop="40" width="182" @tap="btnClick()">
                <label class="loginButton line horizontal top" horizontalAlignment="left"/>
                <StackLayout orientation="horizontal">
                    <label class="loginButton line vertical left"/>
                    <Label text="LOGIN" class="loginButton"/>
                    <label class="loginButton line vertical right"/>
                </StackLayout>
                <label class="loginButton line horizontal bottom" horizontalAlignment="right"/>
            </Stacklayout>

        </Stacklayout>
    </Gridlayout>
</Page>
    
</template>

<script>
    import { Http } from '@nativescript/core'
    var view = require("./Home.vue");

  export default {

    mounted() {
        console.log('Hi');
    },
      
    computed: {
    },
    
    methods: {
        btnClick: function(args) {
            
            console.log('login');

            Http.request({
            method: "POST",
            url: 'http://api.cuodex.net:8080/passx/v2/auth/login',
            content: JSON.stringify({
                username: view.getViewById("username-input").text,
                passwordTest: view.getViewById("password-input").text
            }),
            headers: {"Content-Type": "application/json"},
            timeout: 5000,
        }).then(response => { // handle replay
            const responseAsJson = response.content.toJSON();
            console.log('dispatchAsync\n\tresponse:', responseAsJson);
        }, reason => {
            console.error(`[ERROR] httpModule, msg: ${reason.message}`);
        });


    }

    }
  };
</script>

<style scoped lang="scss">
.mainContainer {
    background-color: rgb(0, 0, 0, 0.5);
    width: 90%;
    height: 90%;
    padding: 20;
}

.inputs {
    color: lightgray;
    
    font-size: 14;

    &.password {
        margin-top: 20;
    }

    &.label {
        padding-left: 15;
    }
}

.inputFields {
    color: white;
    placeholder-color: white;
    font-size: 14;
}

.inputbox {
    margin-top: 50;
}

.loginButton {
    background-color: #B01999;
    padding: 15 0;
    width: 170;
    text-align: center;
    color: white;


    &.line {
        background-color: #B01999;
        &.horizontal {
            height: 3;
            width: 150px;
            
            &.top {
                margin-bottom: 3;
            }

            &.bottom {
               margin-top: 3;
            }
        }

        &.vertical {
            height: 25;
            width: 3;

            &.left {
                vertical-align: top;
                margin-right: 3;
            }

            &.right {
                vertical-align: bottom;
                margin-left: 3;
            }
        }
    }

}

.coverImage {
    background-image: url('res://background');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
}

</style>
