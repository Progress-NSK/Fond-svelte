<main class="page">
	<section class="hero">
		<p class="badge">Svelte Starter</p>
		<h1>Репозиторий готов к разработке</h1>
		<p>
			Базовый проект настроен: можно запускать локальную разработку,
			собирать production-бандл и деплоить статику из <code>public</code>.
		</p>
	</section>

	<section>
		<h2>Быстрый старт</h2>
		<ol>
			<li><code>npm install</code></li>
			<li><code>npm run dev</code></li>
			<li><code>npm run build</code></li>
		</ol>
	</section>

	<section>
		<h2>Что сделать следующим шагом</h2>
		<ul>
			<li>Разбить UI на компоненты в <code>src/components</code>.</li>
			<li>Подключить роутинг (например, svelte-spa-router).</li>
			<li>Добавить линтер и форматтер в CI.</li>
		</ul>
	</section>
</main>

<style>
	:global(body) {
		margin: 0;
		font-family: Inter, -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
		background: #0f172a;
		color: #e2e8f0;
	}

	.page {
		max-width: 760px;
		margin: 0 auto;
		padding: 40px 20px 56px;
		display: grid;
		gap: 20px;
	}

	section {
		background: #111b33;
		border: 1px solid #334155;
		border-radius: 16px;
		padding: 20px;
	}

	.hero {
		background: linear-gradient(135deg, #1d4ed8, #7c3aed);
		border: none;
	}

	h1,
	h2 {
		margin: 0 0 12px;
	}

	p {
		margin: 0;
		line-height: 1.5;
	}

	.badge {
		display: inline-block;
		padding: 6px 10px;
		border-radius: 999px;
		font-size: 12px;
		font-weight: 600;
		letter-spacing: 0.02em;
		text-transform: uppercase;
		background: rgba(255, 255, 255, 0.18);
		margin-bottom: 12px;
	}

	code {
		background: #0b1224;
		border: 1px solid #334155;
		border-radius: 6px;
		padding: 2px 6px;
	}

	ol,
	ul {
		margin: 0;
		padding-left: 20px;
		display: grid;
		gap: 8px;
	}
</style>
