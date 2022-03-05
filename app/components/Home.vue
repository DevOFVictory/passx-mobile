<template>
<Page actionBarHidden="true">
    
    <Gridlayout class="coverImage" rows="*" columns="*">
        <Stacklayout class="mainContainer">
            <Label text="PassX" fontSize="24px" color="white" horizontalAlignment="center"/>
            <Label text="A safe place for all your passwords!" fontSize="16px" color="white" horizontalAlignment="center"/>


            <Stacklayout class="inputbox">
                <Label text="Username" class="inputs label"/>
                <TextField hint="Enter Username" placeholderColor="white" autocorrect="false" autocapitalizationType="none" class="inputs"/>

                <Label text="Password" class="inputs label password"/>
                <TextField hint="Enter Password" placeholderColor="white" secure="true" autocorrect="false" autocapitalizationType="none" class="inputs"/>
                <Label text="Create a new account" horizontalAlignment="right" paddingRight="15" fontSize="14" color="rgb(120, 120, 120)"/>
            </Stacklayout>

            <Stacklayout marginTop="40" width="182">
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
  export default {
    computed: {
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
    color: white;
    
    font-size: 14;

    &.password {
        margin-top: 20;
    }

    &.label {
        padding-left: 15;
    }
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
