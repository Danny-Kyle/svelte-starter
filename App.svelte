<!--First lesson: First Component -->
<script>
	const name = 'Svelte';
</script>

<h1>Hello {name.toUpperCase()}!</h1>

<!--Second lesson: Dynamic Attributes-->
<script>
	let src = '/image.gif';
	const name = 'Rick Astley';
</script>

<img {src} alt="{name} dances." />

<!--Third Lesson: Styling-->
<p>This is a paragraph.</p>

<style>
	p {
		color: goldenrod;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>

<!-- Fourth Lesson: Nested Components -->
<script>
	import Nested from './Nested.svelte';
</script>

<p>This is a paragraph.</p>
<Nested />

<style>
	p {
		color: goldenrod;
		font-family: 'Comic Sans MS', cursive;
		font-size: 2em;
	}
</style>

<!--Fifth Lesson: HTML Tags-->
<script>
	let string = `this string contains some <strong>HTML!!!</strong>`;
</script>

<p>{@html string}</p>


<!--Sixth Lesson: Reactivity-->
<script>
    let count = 0;

    function increment() {
        //event handler goes in here
        count += 1;
    }
</script>

<button on:click={increment}>
    Clicked {count}
    {count === 1 ? 'time' : 'times'}
</button>

<!--Seventh Lesson: Declarations-->
<script>
    let count = 0;
    $: doubled = count * 2;
    function increment() {
        count += 1;
    }
</script>

<button on:click={increment}>
    Clicked {count}
    {count === 1 ? 'time' : 'times'}
</button>

<p>{count} double is {doubled}</p>

<!--Eighth Lesson: Statements-->
<script>
    let count = 0;

    $: if(count > 10){
        alert('count is dangerously high');
        count = 0;
    }

    function handleClick(){
        count += 1;
    }
</script>

<button on:click={handleClick}>
    Clicked {count}
    {count === 1 ? 'time' : "times"}
</button>

<!--Ninth Lesson: Updating Arrays and objects-->
<script>
	let numbers = [1, 2, 3, 4];

	function addNumber() {
        //method one
		// numbers.push(numbers.length + 1);
        // numbers = numbers;

        //method two
        numbers  = [...numbers, numbers.length + 1];
	}

	$: sum = numbers.reduce((total, currentNumber) => total + currentNumber, 0);
</script>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>
	Add a number
</button>
