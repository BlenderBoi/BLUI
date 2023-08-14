
<script>
import blui from "$lib/blui.css";

</script>


<div class="panel">
    <slot><!-- optional fallback --></slot>
</div>

<style>

.panel {
    background-color: var(--panel-color);
    padding: 1em;
}

</style>