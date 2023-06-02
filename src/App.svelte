<script lang="ts">
    let inputValue: string = '';
    let resultText: string = '';
    let isSubmitted: boolean = false;

    let numbers = [1, 2, 3, 4, 5];

    function submitAnswer() {
        isSubmitted = true;
        if (inputValue.toLowerCase() === 'олег') {
            resultText = 'Не повезло!';
        } else if (inputValue.length === 0) {
            resultText = 'Введите слово!';
        } else {
            resultText = 'Хороший выбор!';
        }
    }
</script>

<main>
    <h1>Как вас зовут?</h1>
    <input placeholder="Например, Олег" class="input" bind:value={inputValue} />
    <button on:click={submitAnswer}>Подтвердить</button>
    <h2>
        {#if isSubmitted}
            <span>{resultText}</span>
        {/if}
    </h2>
    <ul />
</main>

<style>
    .input {
        padding: 1rem;
        font-size: 1.2rem;
    }
</style>
