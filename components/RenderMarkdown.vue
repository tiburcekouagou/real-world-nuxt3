<script setup lang="ts">
import VueMarkdown from 'vue-markdown-render';
import hljs from 'highlight.js/lib/core';
import javascript from 'highlight.js/lib/languages/javascript';
import xml from 'highlight.js/lib/languages/xml';
import 'highlight.js/styles/obsidian.css'

const {source} = defineProps<{
    source: string
}>()


// register the languages you need from Highlight.js
hljs.registerLanguage('javascript', javascript);
hljs.registerLanguage('xml', xml);

/* HighlightJs options */
const options = {
    highlight: function (str: string, lang: string) {
        if (!hljs.getLanguage(lang)) {
            return
        }
        return hljs.highlight(str, {language: lang}).value
    }
}
</script>

<template>
    <div>
        <vue-markdown :source="source" :options="options" />
    </div>
</template>