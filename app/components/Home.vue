<template>
<Page>
    <ActionBar backgroundColor="#7c149c">
        <Label text="PassX" fontSize="32px" horizontalAlignment="center"/>
    </ActionBar>
    
    <Gridlayout backgroundColor="#a621cf" rows="*" columns="*">
        <Stacklayout class="mainContainer">
            <Label text="PassX" fontSize="24px" color="white" horizontalAlignment="center"/>
            <Label text="A safe place for all your passwords!" fontSize="16px" color="white" horizontalAlignment="center"/>


        <Stacklayout class="inputbox">
            <Label text="Username" class="inputs label"/>
            <TextField hint="Enter Username" autocorrect="false" autocapitalizationType="none" class="inputs"/>

            <Label text="Password" class="inputs label password"/>
            <TextField hint="Enter Password" secure="true" autocorrect="false" autocapitalizationType="none" class="inputs"/>
            <Label text="Create a new account" horizontalAlignment="right" paddingRight="15" fontSize="14" color="rgb(120, 120, 120)"/>
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

</style>
