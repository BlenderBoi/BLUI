
<script>

    export let align = false

</script>

<div class="layout {align ? "align" : "noAlign"}">
    <slot><!-- optional fallback --></slot>
</div>


<style>
    .layout{
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(10px, 1fr));


    }
    .align{
        gap: 0;
    }

    .noAlign{
        gap: 1em;
    }

    .noAlign > :global(*){
        border-radius: 5px;
    }

    .align > :global(:first-child){
        border-top-left-radius: 5px;
        border-bottom-left-radius: 5px;
    }

    .align > :global(:last-child){
        border-top-right-radius: 5px;
        border-bottom-right-radius: 5px;
    }


</style>