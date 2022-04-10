<script context="module">
	/** @type {import('@sveltejs/kit').ErrorLoad} */
	export function load({ error, status }) {
		return {
			props: { error, status }
		};
	}
</script>

<script>
	/** @type {number} */
	export let status;

	/** @type {Error & {frame?: string} & {loc?: object}} */
	export let error;
    let src = "saddracula.jpg"
</script>

<div class="error">
    <h1>Error code: {status}</h1>

    <pre>{error.message}</pre>

    <img {src} alt="sad dracula" width="180px">
</div>


<style>
    .error {
        color: white;
        text-align: center;
        border: 1px dotted white;
        padding: 10px 20px 30px;
    }
    .error img {
        border-radius: 50px;
        margin-top: 20px;
    }
</style>