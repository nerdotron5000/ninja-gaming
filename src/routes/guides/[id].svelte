<script context="module">
    export async function load({ fetch, params }) {
        const id = params.id
        const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
        const guide = await res.json()

        if (res.ok) {
            return {
                props: {
                    guide
                }
            }
        }

        return {
            status: res.status,
            error: new Error('Could not fetch the guide.')
        }
    }
</script>

<script>
    export let guide;
</script>

<div class="guide">
    <h2>{guide.title}</h2>
    <p>{guide.body}</p>
</div>

<style>
    .guide {
        margin-top: 40px;
        padding: 10px 30px;
        border: 1px dotted white;
    }
</style>