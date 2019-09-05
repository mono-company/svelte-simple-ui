<script>

    import ButtonInnerLayout from './ButtonInnerLayout.svelte';

    // type="button" or type="submit"
    export let type = false;
    export let classValue = null;

    // if it contains a link
    export let href = false;
    export let value = "Default value";
    export let disabled = false;
    export let style = null;
    export let icon = null;
    export let layout = null;

</script>

<style>

    a, button {
        font-size: 1.4rem;
        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
    }

    a, button {
        background: #F0F0F0;
        border: 1px solid #CCC;
        border-radius: 0.3rem;
        padding: 0.7rem;
        align-items: center;
        display: inline-flex;
        justify-content: center;
        vertical-align: baseline;
        color: #333;
        white-space: nowrap;
    }

    button[disabled] {
        opacity: 0.4;
    }

    a:focus, button:focus {
        background: #FFF;
        outline: 0;
        border-color: #3A75CB;
        box-shadow: 0 0 0 0.1rem #3A75CB, 0 0 0 0.4rem #C3DCFF;
        transition: 0.1s ease-in-out all;
    }

</style>

{#if href}
    <a href="{href}" {style} {classValue}>
        <ButtonInnerLayout {icon} {layout}><slot></slot></ButtonInnerLayout>
   </a>
{:else}
    {#if type == "submit"}
        <button type="submit" {disabled} {classValue} {style} on:submit on:click>
            <ButtonInnerLayout {icon} {layout}><slot></slot></ButtonInnerLayout>
    	</button>
    {:else}
        <button type="button" {disabled} {classValue} {style} on:submit|preventDefault on:click>
            <ButtonInnerLayout {icon} {layout}><slot></slot></ButtonInnerLayout>
    	</button>
    {/if}
{/if}
