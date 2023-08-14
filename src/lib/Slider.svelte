
<script>
import { browser } from '$app/environment';

import blui from "$lib/blui.css";

export let value = 0
export let max
export let min
export let softmax
export let softmin


export let section = "solo"

let textMode = false
let textEdit = false
let dragMode = false
let mousedown = false

export let role = "solo"

let showButton = false
if (browser){
    document.onkeydown = e=>{if (e.key=="Escape"){textMode=false}}
    // document.oncontextmenu= e=> {e.preventDefault(); if (textEdit){textEdit=false}}

}


</script>



<!-- <div class="{showButton&&!textEdit?"exteriorShow": "exteriorHide" }" on:mouseenter={(e)=>{showButton=true}} on:mouseleave={(e)=>{showButton=false}}> -->

    <div class="container" on:mouseenter={(e)=>{showButton=true}} on:mouseleave={(e)=>{showButton=false}}>
        <!-- {#if !dragMode}
        <input type="text" bind:value={value} class="textEdit" bind:this={textEdit} autofocus on:focusout={e=>{textMode=false}}>
        {:else} -->
        {#if showButton}
        <button class="stepBtn" on:click={e=>{value-=1}}>&#60;</button>
        {/if}
        <button class="textEdit drag" on:mousedown={e=>{e.target.requestPointerLock(); mousedown=true}} on:mousemove={e=>{if(mousedown){if(e.shiftKey){value+=Math.ceil(e.movementX/100)}else{value+=e.movementX}; if (e.movementX+e.movementY>1)dragMode = true;}}} on:mouseup={e=>{if (browser){document.exitPointerLock(); if (!dragMode){textMode=true}; dragMode=false}; mousedown=false}}  >
        <p>{value}</p>
        </button>
        {#if showButton}
        <button class="stepBtn" on:click={e=>{value+=1}}>&#62;</button>
        {/if}
        <!-- {/if} -->

    </div>


        <!-- <button class="slideBtn" on:click={e=>{value-=1}}>&#60;</button> -->
        <!-- <p>{value}</p> -->
        <!-- <button class="slideBtn" on:click={e=>{value+=1}}>&#62;</button> -->
    
    <!-- </button> -->
<!-- </div> -->


<style>
    .stepBtn{
        background-color: transparent;
        border: none;
        color: var(--main-font-color);
        outline: none;
        width: 1.5em;

    }
    .container{

        display: flex;
        justify-content: space-around;
        background-color: var(--main-bg-color);
        color: var(--main-font-color);
        border: none;
        padding: 0;
        margin: 0;
        border: 1px solid white;
    }

    .textEdit:hover{
        background-color: var(--main-bg-color-hover);
    }
    .drag{
        cursor: ew-resize;
    }

    .textEdit{

        flex: 1;
        background-color: transparent;
        color: var(--main-font-color);
        padding: 0;
        padding-left: 1em;
        margin: 0;
        height: 3em;
        outline: none;
        border: none;
    }
    





</style>