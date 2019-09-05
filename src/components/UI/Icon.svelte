<script>
    // Possible icon types
    import IconDelete from './Icons/16/actions/delete.svg';
    import IconQuestion from './Icons/16/actions/question.svg';
    import IconAdd from './Icons/16/actions/add.svg';
    import IconRemove from './Icons/16/actions/remove.svg';
    import IconClose from './Icons/16/actions/close.svg';
    export let icon;
</script>

{#if icon == 'delete'}
    {@html IconDelete}
{/if}
{#if icon == 'question'}
    {@html IconQuestion}
{/if}
{#if icon == 'add'}
    {@html IconAdd}
{/if}
{#if icon == 'remove'}
    {@html IconRemove}
{/if}
{#if icon == 'close'}
    {@html IconClose}
{/if}
