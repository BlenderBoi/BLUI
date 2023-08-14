
<script>

    export let align = false

</script>

<div class="layout {align ? "align" : "noAlign"}">
    <slot></slot>
</div>


<style>
    .layout{
        display: grid;
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

    .align > :global(:first-child > :first-child){
        border-top-left-radius: 5px;
        border-top-right-radius: 5px;
    }

    .align > :global(:last-child > :last-child){
        border-bottom-left-radius: 5px;
        border-bottom-right-radius: 5px;
    }

</style>