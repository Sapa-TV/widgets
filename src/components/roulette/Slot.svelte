<script lang="ts" module>
	import { asset } from "$app/paths";

	export const VARIANT_IMG_LINKS = {
		common: asset("/roulette/common.png"),
		uncommon: asset("/roulette/uncommon.png"),
		rare: asset("/roulette/rare.png"),
		legendary: asset("/roulette/legendary.png"),
		mythic: asset("/roulette/mythic.png"),
	};
</script>

<script lang="ts">
	interface Props {
		variant: keyof typeof VARIANT_IMG_LINKS;
	}

	let { variant }: Props = $props();
</script>

<div>
	<img src={VARIANT_IMG_LINKS[variant]} alt={variant} />
</div>

<style>
	div {
		flex-shrink: 0;
	}
	img {
		object-fit: none;
	}
</style>
