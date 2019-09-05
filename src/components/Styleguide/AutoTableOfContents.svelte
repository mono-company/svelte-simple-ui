<script>

    // Generate a table of contents automatically from a heading structure

    import { onMount } from 'svelte';

    function updateToc() {

        var c = function() {
            return({
                log: function(msg) {
                consoleDiv = document.getElementById('console');
                para = document.createElement('p');
                text = document.createTextNode(msg);
                para.appendChild(text);
                consoleDiv.appendChild(para);
                }
            });
        }();

        var toc = "";
        var level = 1;
        var maxLevel = 3;

        document.getElementById("components").innerHTML =
            document.getElementById("components").innerHTML.replace(
                /<h([\d])>([^<]+)<\/h([\d])>/gi,
                function (str, openLevel, titleText, closeLevel) {
                    if (openLevel != closeLevel) {
                    c.log(openLevel)
                        return str + ' - ' + openLevel;
                    }

                    if (openLevel > level) {
                        toc += (new Array(openLevel - level + 1)).join("<ol>");
                    } else if (openLevel < level) {
                        toc += (new Array(level - openLevel + 1)).join("</ol>");
                    }

                    level = parseInt(openLevel);

                    var anchor = titleText.replace(/ /g, "_");
                    toc += "<li><a href=\"#" + anchor + "\">" + titleText
                        + "</a></li>";

                    return "<h" + openLevel + "><a name=\"" + anchor + "\">"
                        + titleText + "</a></h" + closeLevel + ">";
                }
            );

        if (level) {
            toc += (new Array(level + 1)).join("</ol>");
        }

        document.getElementById("toc").innerHTML += toc;
    }

    onMount( () => {
        updateToc();
    });

</script>

<style>

    :global(#toc ol) {
        margin: 0;
        padding: 0;
    }

    :global(#toc ol ol) {
        margin: 0;
        padding: 0 0 0 2.4rem;
    }

    :global(#toc ol li) {
        list-style: none;
        margin: 0;
        padding: 0;
    }

    :global(#toc a) {
        display: block;
        padding: 0.6rem;
        text-decoration: none;
        color: #333;
    }

    :global(#toc a:hover) {
        background: #EEE;
    }

</style>

<div id="toc"></div>
