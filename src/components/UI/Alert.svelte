<script>

    import Button from './Button.svelte';

    export let message = "Default message";
    export let type = null;;
    export let dismissible = null;
    export let show = true;

</script>

<style>

    .alert {
        padding: 1.6rem;
        border-radius: 0.3rem;
        margin: 0 0 1.6rem;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }

    .alert-default {
        background: #FFF;
        border: 1px solid #CCC;
    }

    .alert-error {
        background: #FFD0D0;
        border: 1px solid #EAA2A2;
        color: #C80000;
    }

    .alert-success {
        background: #D6F7D1;
        border: 1px solid #ABE2A2;
        color: #32542D;
    }

    :global(.alert button) {
        mix-blend-mode: multiply;
    }

</style>

{#if show}
    <div class="alert {type ? 'alert-'+type : 'alert-default'}" role="alert">
        <slot></slot>
        {#if dismissible}
            <Button icon="close" layout="icon-only" on:click="{() => show = false}">Close</Button>
        {/if}
    </div>
{/if}

