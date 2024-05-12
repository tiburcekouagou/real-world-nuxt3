<script setup lang="ts">
const source = "**This is a bold text.**"
</script>

<template>
    <main>
        <RenderMarkdown :source="source" />
    </main>
</template>