
<script>
import blui from "$lib/blui.css";
export let text="Button"
export let section = "solo"

</script>


<button class={section}>{text}</button>


<style>

button{
    background-color: var(--main-bg-color);
    color: var(--main-font-color);
    border: none;
    height: 3em;
    padding: 0 2em;
    width: 100%;
}

.solo{
    /* border-radius: 5px; */
}
.left {
    /* border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
    border-top-right-radius: 0;
    border-bottom-right-radius: 0; */
}
.right{
    /* border-top-left-radius: 0px;
    border-bottom-left-radius: 0px;
    border-top-right-radius: 5px;
    border-bottom-right-radius: 5px; */
}
.center{
    border-radius: 0;
}

button:hover{
    
    background-color: var(--main-bg-color-hover);
}

button:active{
    
    background-color: var(--button-active);
}
</style>