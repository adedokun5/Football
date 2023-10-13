
<template>
    <div class="control-div">
        <span class="display-flex control-sect">
            <span class="display-flex control-text-sect">
                <span class="circle"></span>
                <span class="control-text">Lorem ipsum dolor sit adipisicing elit.</span>
            </span>
            <button :class="firstButton" id="switch-cont" @click="$emit( 'btnClick', firstButton )">
                <span :class="firstButton" id="switch"></span>
            </button>
        </span>

        <span class="display-flex control-sect">
            <span class="display-flex control-text-sect">
                <span class="circle"></span>
                <span class="control-text">Lorem ipsum dolor sit adipisicing elit.</span>
            </span>
            <button :class="secondButton" id="switch-cont" @click="$emit( 'btnClick', secondButton )">
                <span :class="secondButton" id="switch"></span>
            </button>
        </span>
    </div>  
</template>

<script>
    export default {
        name : 'control',
        props:[ 'firstButton', 'secondButton' ],
        emits:[ 'btnClick']
    }
</script>