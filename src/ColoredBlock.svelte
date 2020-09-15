<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher();

    export let opacity = 1;
    export let color = 'gray';
</script>

<style>
    .color-block {
        display: inline-block;
        width: 100px;
        height: 100px;
    }
</style>

<div on:click class="color-block" style="background-color: {color}; opacity: {opacity}"></div>