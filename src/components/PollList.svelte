<script>
    import {fade, slide, scale} from "svelte/transition";
    import { flip } from "svelte/animate";
    import PollStore from "../stores/PollStore";
    import PollDetails from "./PollDetails.svelte";
</script>

<div class="poll-list">
    {#each $PollStore as poll (poll.id)}
        <div transition:fade|local animate:flip={{duration: 500}}>
            <PollDetails poll={poll} />
        </div>
    {/each}
</div>

<style>
    .poll-list {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 20px;
    }
</style>