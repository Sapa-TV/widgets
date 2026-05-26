<script lang="ts">
	import { asset } from "$app/paths";
	import Slot from "./Slot.svelte";

	function run() {
		console.warn("run");
	}
</script>

<button onclick={run}>run</button>

<div class="roulette">
	<img class="track" src={asset("/roulette/track.png")} alt="Roulette track" />
	<img class="arrow" src={asset("/roulette/arrow.png")} alt="Roulette arrow" />
	<div class="track-wrapper">
		<div class="track-scroller animate">
			<Slot variant="common" />
			<Slot variant="uncommon" />
			<Slot variant="rare" />
			<Slot variant="legendary" />
			<Slot variant="mythic" />
			<Slot variant="common" />
			<Slot variant="uncommon" />
			<Slot variant="rare" />
			<Slot variant="legendary" />
			<Slot variant="mythic" />
			<Slot variant="common" />
			<Slot variant="uncommon" />
			<Slot variant="rare" />
			<Slot variant="legendary" />
			<Slot variant="mythic" />
			<Slot variant="common" />
			<Slot variant="uncommon" />
			<Slot variant="rare" />
			<Slot variant="legendary" />
			<Slot variant="mythic" />
		</div>
	</div>
</div>

<style>
	.roulette {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
		width: 100%;
		height: 100%;
		min-height: 100vh;
	}
	.track {
		position: absolute;
	}
	.arrow {
		position: absolute;
		transform: translate(0px, -220px);
	}
	.track-wrapper {
		position: relative;
		display: flex;
		overflow: hidden;
		width: 1225px;
		height: 260px;
		mask-image: linear-gradient(
			to right,
			transparent,
			transparent 20px,
			black 50px,
			black 1175px,
			transparent 1205px,
			transparent
		);
	}
	.track-scroller {
		display: flex;
		gap: 0px;
	}
	.animate {
		animation: roll 5s cubic-bezier(0.1, 0.85, 0.8, 1) infinite;
	}
	@keyframes roll {
		from {
			transform: translateX(0);
		}
		to {
			transform: translateX(calc(3 * -1225px));
		}
	}
</style>
