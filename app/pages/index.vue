<script setup lang="ts">
import { useRouter } from "#app";

// Get the router instance
const router = useRouter();

// Retrieve an array containing all normalized route records
const getNotes = () =>
    router.getRoutes().filter((x) => x.path.startsWith("/notes/"));
</script>
<template>
    <p>
        Hello, I'm Martin Nester. a software developer from Virginia, United
        States. I'm most familiar with web dev, but also enjoy operating
        systems, distrubited programming, information retrieval, chasos
        engineering, local-first, databases, functional programming, language
        design, DX/UI/UX, game development, and more.
    </p>
    <p>
        There is so much out there I want to learn about, change, contribute to
        and improve. I hope to start sharing my progress here.
    </p>
    <br />
    <p>Recently I've been most interested in:</p>
    <ul>
        <li><a href="https://www.ripple-ts.com/">Ripple TS</a></li>
        <li><a href="https://www.unison-lang.org/">Unison</a></li>
        <li><a href="https://electric.ax/sync/">Electric Sync</a></li>
    </ul>
    <br />
    <p>Notes I'm taking:</p>
    <ul>
        <li v-for="note in getNotes()">
            <a :href="note.path">{{ note.name }}</a>
        </li>
    </ul>
</template>
