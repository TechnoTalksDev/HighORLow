<script>
    import { createEventDispatcher } from 'svelte';

    const dispatch = createEventDispatcher()

    function processRaw(event) {
        const formRaw = new FormData(event.target)
        event.target.reset()
        const guess = formRaw.get('guess')
        //console.log("this is shit")

        dispatch('input', guess)
    }
</script>

<form on:submit|preventDefault={processRaw}>
    <input type="number" id="input" name="guess">
</form>