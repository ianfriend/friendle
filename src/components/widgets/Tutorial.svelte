<script lang="ts">
	import { COLS, ROWS } from "../../utils";

	import { Tile } from "../board";
	export let visible: boolean;
</script>

<h3>how to play</h3>
<div>Guess the <strong>FRIENDLE</strong> in {ROWS} tries to reveal Baby Friend's name and gender.</div>
<div>Each guess must be a valid {COLS} letter name, and could be a boy or girls name. Hit the enter button to submit.</div>
<div>
	After each guess, the color of the tiles will change to show how close your guess was to the
	word.
</div>
<div class:complete={visible} class="examples">
	<div><strong>Examples</strong></div>
	<div class="row">
		<Tile value="d" state="🔳" />
		<Tile value="a" state="🟩" />
		<Tile value="v" state="🔳" />
		<Tile value="i" state="🔳" />
		<Tile value="d" state="🔳" />
	</div>
	<div>The letter <strong>A</strong> is in the word and in the correct spot.</div>
	<div class="row">
		<Tile value="a" state="🔳" />
		<Tile value="l" state="🔳" />
		<Tile value="e" state="🔳" />
		<Tile value="x" state="🟨" />
		<Tile value="a" state="🔳" />
	</div>
	<div>The letter <strong>X</strong> is in the word but in the wrong spot.</div>
	<div class="row">
		<Tile value="n" state="🔳" />
		<Tile value="i" state="🔳" />
		<Tile value="c" state="⬛"/>
		<Tile value="k" state="🔳" />
		<Tile value="y" state="🔳" />
	</div>
	<div>The letter <strong>C</strong> is not in the word in any spot.</div>
</div>
<div>
	A new FRIENDLE may be available in the future...
</div>

<style lang="scss">
	div {
		margin: 14px 0;
	}
	.examples {
		border-top: 1px solid var(--border-primary);
		border-bottom: 1px solid var(--border-primary);
		:global(.row > *) {
			height: 100%;
			aspect-ratio: 1;
		}
		&:not(.complete) :global(.row .back) {
			transition-delay: 0.3s;
		}
	}
	.row {
		height: 40px;
		display: flex;
		gap: 4px;
	}
</style>
