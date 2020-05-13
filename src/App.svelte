<script>
	import Score from './Score.svelte';
	import Factories from './Factories.svelte';
	import LeftBoard from './LeftBoard.svelte';
	import RightBoard from './RightBoard.svelte';
	import Floor from './Floor.svelte';
</script>

<h1>Let's play Bleu!</h1>
<Score score={0}/>

<Factories playerCount={4}/>
<table>
	<td><LeftBoard/></td>
	<td><RightBoard/></td>
</table>
<Floor/>
