<script>
    import marked from "marked";

    let source = "# New document";
    $: markdown = marked(source);
</script>

<div class="markdown-editor" style="-webkit-app-region: drag;">
    <div class="markdown-editor__left-panel">
        <textarea
            bind:value="{source}"
            class="markdown-editor__source"
        ></textarea>
    </div>

    <div class="markdown-editor__right-panel">
        <div class="markdown-editor__output">{@html markdown}</div>
    </div>
</div>

<!-- style -->

<style>
    body {
        background-color:#1b1b1b;
        
    }

    textarea{
        background-color:#282828;
        color:#dddddd;
    }

    .markdown-editor {
        margin-top: 36px;
        width: 100%;
        display: flex;
        align-items: flex-start;
        justify-content: space-evenly;
        background-color:#1b1b1b;
        color:#dddddd;
    }

    .markdown-editor__left-panel,
    .markdown-editor__right-panel {
        width: 50%;
        border: solid 1px black;
        height: 90vh;
    }

    .markdown-editor__right-panel {
        overflow: auto;
    }

    .markdown-editor__source {
        border: none;
        width: 100%;
        height: 100%;
    }

    .markdown-editor__source:focus {
        outline: none;
    }

    .markdown-editor__output {
        width: 100%;
        padding: 0 2em;
    }
</style>
