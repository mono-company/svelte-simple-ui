<style>

    :global(.toolbar-item) {
        flex: 0 1 auto;
        margin-right: 1.6rem;
    }

    :global(.toolbar-item:last-child) {
        margin-right: 0
    }

    :global(.toolbar-item h1) {
        margin: 0.8rem 0;
      font-size: 2.4rem;
      font-weight: 700;
    }

</style>

 <div class="toolbar-item">
    <slot></slot>
</div>