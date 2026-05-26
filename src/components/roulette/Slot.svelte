<script lang="ts" module>
	export const VARIANT_IMG_LINKS = {
		common: "/roulette/common.png",
		uncommon: "/roulette/uncommon.png",
		rare: "/roulette/rare.png",
		legendary: "/roulette/legendary.png",
		mythic: "/roulette/mythic.png",
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
</style>
