<script>
    export let columns = 2;
</script>

<style>

    .grid-layout {
        display: grid;
        grid-gap: 10px;
        grid-template-columns: 30rem minmax(30rem, 1fr);
    }

</style>

<div class="grid-layout">
    <slot></slot>
</div>