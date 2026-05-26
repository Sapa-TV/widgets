<script lang="ts">
	import { asset, resolve } from "$app/paths";

	interface Page {
		name: string;
		href: ReturnType<typeof resolve>;
	}

	const pages: Page[] = [
		{ name: "Roulette king", href: resolve("/roulette-king") },
		{ name: "Roulette", href: resolve("/roulette") },
	];
</script>

<svelte:head>
	<title>Sapa Widgets</title>
	<link href="https://fonts.googleapis.com" rel="preconnect" />
	<link crossorigin="" href="https://fonts.gstatic.com" rel="preconnect" />
	<link
		href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&family=Manrope:wght@700;800;900&display=swap"
		rel="stylesheet"
	/>
	<link
		href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap"
		rel="stylesheet"
	/>
</svelte:head>

<div class="light" lang="ru">
	<div class="page">
		<nav class="navbar">
			<div class="navbar-inner">
				<div class="nav-links">
					{#each pages as link (link.href)}
						<a class="nav-link" href={link.href}>{link.name}</a>
					{/each}
				</div>
			</div>
		</nav>
		<main class="main">
			<div class="bg-blob"></div>
			<section class="section">
				<div class="avatar-wrapper">
					<div class="glow"></div>
					<div class="avatar-frame">
						<div class="avatar-stack">
							<img
								alt="Персонаж Sapa TV"
								class="avatar-img avatar-default"
								src={asset("/avatar.png")}
							/>
							<img
								alt="Персонаж Sapa TV"
								class="avatar-img avatar-hover"
								src={asset("/avatar_v2.jpg")}
							/>
						</div>
					</div>
				</div>
				<div class="content">
					<div class="content-header">
						<h1 class="title">Виджеты для Сапушки</h1>
						<p class="subtitle">это вам не надо</p>
					</div>
					<div class="links">
						<a
							class="link link-twitch"
							href="https://www.twitch.tv/sapushka_"
							target="_blank"
						>
							<svg class="icon" fill="currentColor" viewBox="0 0 24 24">
								<path
									d="M11.571 4.714h1.715v5.143H11.57zm4.715 0H18v5.143h-1.714zM6 0L1.714 4.286v15.428h5.143V24l4.286-4.286h3.428L22.286 12V0zm14.571 11.143l-3.428 3.428h-3.429l-3 3v-3H6.857V1.714h13.714z"
								/>
							</svg>
							Смотреть на Twitch
						</a>
						<a
							class="link link-vk"
							href="https://live.vkvideo.ru/sapushka_"
							target="_blank"
						>
							<svg class="icon" fill="currentColor" viewBox="0 0 24 24">
								<path
									d="M15.684 2H8.316C2.504 2 2 2.504 2 8.316v7.368C2 21.496 2.504 22 8.316 22h7.368C21.496 22 22 21.496 22 15.684V8.316C22 2.504 21.496 2 15.684 2zm3.268 12.292h-1.682c-.636 0-.832-.508-1.976-1.668-1.004-.988-1.444-1.124-1.692-1.124-.348 0-.448.1-.448.58v1.524c0 .416-.132.664-1.216.664-1.792 0-3.784-1.084-5.172-3.108C4.664 8.664 4.216 7.1 4.216 6.684c0-.248.1-.48.58-.48h1.682c.44 0 .604.184.772.632.848 2.46 2.26 4.616 2.844 4.616.216 0 .316-.1.316-.648V9.08c-.064-1.044-.612-1.132-.612-1.5 0-.184.152-.364.4-.364h2.648c.368 0 .496.2.496.616v2.512c0 .368.164.496.268.496.216 0 .396-.1.792-.496 1.248-1.396 2.14-3.552 2.14-3.552.12-.248.312-.48.748-.48h1.682c.512 0 .624.264.512.616-.216.984-2.312 3.932-2.312 3.932-.184.296-.248.428 0 .76.184.248.784.76 1.184 1.224.724.808 1.276 1.488 1.424 1.952.164.468-.084.712-.556.712z"
								/>
							</svg>
							VK Видео Live
						</a>
						<a
							class="link link-yt"
							href="https://www.youtube.com/@sapa_sapushka"
							target="_blank"
						>
							<svg class="icon" fill="currentColor" viewBox="0 0 24 24">
								<path
									d="M23.498 6.186a3.016 3.016 0 0 0-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 0 0 .502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 0 0 2.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 0 0 2.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"
								/>
							</svg>
							YouTube
						</a>
					</div>
				</div>
			</section>
		</main>
	</div>
</div>

<style>
	.page {
		background: var(--surface);
		color: var(--on-surface);
		::selection {
			background: var(--primary-container);
			color: var(--on-primary-container);
		}
		min-height: 100vh;
		display: flex;
		flex-direction: column;
		overflow-x: hidden;
	}

	.navbar {
		position: fixed;
		top: 0;
		width: 100%;
		background: rgba(239, 248, 255, 0.4);
		backdrop-filter: blur(20px);
		z-index: 50;
	}

	.navbar-inner {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1.5rem 2rem;
		width: 100%;
		max-width: 1440px;
		margin: 0 auto;
	}

	.nav-links {
		display: flex;
		gap: 1rem;
	}

	.nav-link {
		font-size: 1.5rem;
		font-weight: 900;
		color: #003346;
		letter-spacing: -0.05em;
		text-decoration: none;
	}

	.nav-link:hover {
		text-decoration: underline;
	}

	.main {
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		padding: 6rem 1.5rem;
		position: relative;
		padding-top: 5rem;
	}

	.bg-blob {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		width: 300px;
		height: 300px;
		background: linear-gradient(
			to top right,
			rgba(0, 207, 252, 0.2),
			rgba(207, 236, 255, 0.2)
		);
		border-radius: 9999px;
		filter: blur(120px);
		z-index: -10;
	}

	@media (min-width: 640px) {
		.bg-blob {
			width: 500px;
			height: 500px;
		}
	}

	@media (min-width: 768px) {
		.bg-blob {
			width: 800px;
			height: 800px;
		}
	}

	.section {
		max-width: 42rem;
		width: 100%;
		text-align: center;
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 2.5rem;
	}

	.avatar-wrapper {
		position: relative;
		display: inline-block;
	}

	.glow {
		position: absolute;
		inset: 0;
		background: rgba(0, 207, 252, 0.1);
		border-radius: 9999px;
		filter: blur(48px);
		transition: background 1s;
	}

	.avatar-wrapper:hover .glow {
		background: rgba(0, 207, 252, 0.2);
	}

	.avatar-frame {
		position: relative;
		background: rgba(255, 255, 255, 0.4);
		padding: 0.5rem;
		border-radius: 1rem;
		box-shadow:
			0 20px 25px -5px rgba(0, 0, 0, 0.1),
			0 8px 10px -6px rgba(0, 0, 0, 0.1);
		backdrop-filter: blur(4px);
		border: 1px solid rgba(255, 255, 255, 0.5);
	}

	.avatar-stack {
		position: relative;
		width: 14rem;
		aspect-ratio: 1;
	}

	@media (min-width: 640px) {
		.avatar-stack {
			width: 20rem;
		}
	}

	@media (min-width: 768px) {
		.avatar-stack {
			width: 24rem;
		}
	}

	.avatar-img {
		position: absolute;
		inset: 0;
		width: 100%;
		height: 100%;
		border-radius: 0.75rem;
		object-fit: cover;
		transition: opacity 0.5s;
	}

	.avatar-hover {
		opacity: 0;
	}

	.avatar-wrapper:hover .avatar-default {
		opacity: 0;
	}

	.avatar-wrapper:hover .avatar-hover {
		opacity: 1;
	}

	.content {
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}

	.content-header {
		display: flex;
		flex-direction: column;
		gap: 0.25rem;
	}

	.title {
		font-size: 1.5rem;
		font-weight: 900;
		letter-spacing: -0.05em;
		color: var(--on-background);
		line-height: 1;
	}

	@media (min-width: 640px) {
		.title {
			font-size: 1.875rem;
		}
	}

	@media (min-width: 768px) {
		.title {
			font-size: 2.25rem;
		}
	}

	.subtitle {
		font-size: 0.75rem;
		font-weight: 500;
		color: rgba(52, 97, 120, 0.5);
	}

	@media (min-width: 640px) {
		.subtitle {
			font-size: 0.875rem;
		}
	}

	.coming-soon {
		font-size: 1.125rem;
		font-weight: 500;
		color: rgba(52, 97, 120, 0.8);
		line-height: 1.625;
		max-width: 28rem;
		margin: 0 auto;
		opacity: 0;
	}

	@media (min-width: 768px) {
		.coming-soon {
			font-size: 1.25rem;
		}
	}

	.links {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 1rem;
		width: 100%;
		max-width: 20rem;
		margin: 0 auto;
	}

	.link {
		display: inline-flex;
		align-items: center;
		justify-content: center;
		gap: 0.75rem;
		color: white;
		padding: 0.75rem 1.5rem;
		border-radius: 9999px;
		font-weight: 700;
		font-size: 0.875rem;
		box-shadow:
			0 10px 15px -3px rgba(0, 0, 0, 0.1),
			0 4px 6px -4px rgba(0, 0, 0, 0.1);
		transition: all 0.15s;
		width: 100%;
		text-decoration: none;
	}

	@media (min-width: 640px) {
		.link {
			padding: 0.75rem 2rem;
			font-size: 1rem;
		}
	}

	.link:active {
		transform: scale(0.95);
	}

	.link-twitch {
		background: #9146ff;
	}

	.link-twitch:hover {
		background: #772ce8;
	}

	.link-vk {
		background: #0077ff;
	}

	.link-vk:hover {
		background: #0066dd;
	}

	.link-yt {
		background: #ff0000;
	}

	.link-yt:hover {
		background: #cc0000;
	}

	.icon {
		width: 1.5rem;
		height: 1.5rem;
	}
</style>
