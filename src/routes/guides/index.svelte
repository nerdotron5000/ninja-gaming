<script context="module">
    export async function load({ fetch }) {
        const res = await fetch('https://jsonplaceholder.typicode.com/posts');
        const guides = await res.json()

        if (res.ok) {
            return {
                props: {
                    guides
                }
            }
        }

        return {
            status: res.status,
            error: new Error('Could not fetch the guides.')
        }
    }
</script>

<script>
    export let guides;
</script>

<div class="guides">
    <h1>List of Guides</h1>
    <ul>
        {#each guides as guide}
            <li>
                {guide.id} <a href={`/guides/${guide.id}`}>{guide.title}</a></li>
        {/each}
    </ul>
</div>

<style>
    .guides {
        margin-top: 20px;
    }
    .guides ul {
        list-style: none;
        padding:0;
    }
    .guides li {
        font-size: 1.2em;
    }
    .guides a {
        display: inline-block;
        margin-top: 10px;
        padding: 10px;
        border: 1px dotted white;
    }
    .guides h1 {
        text-align: center;
    }
</style>