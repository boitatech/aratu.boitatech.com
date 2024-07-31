<script>
	import CardPalestra from '../components/CardPalestra/index.svelte'
	import HighlightedText from '../components/HighlightedText/index.svelte'
	import Selector from '../components/Seletor/index.svelte'
	import semanaaratubg from '../assets/aratu-bg.png'
	import semanaaratulogo from '../assets/semana-aratu-logo.png'
</script>

<style>
	.cards-container {
		display: grid;
		justify-items: center;
		width: 100vw;
		gap: 1.8rem;
	}

	.bg-image {
		position: absolute;
		bottom: -45rem;
		left: -20rem;
		width: 1070px;
		z-index: -1;
	}

	.intro-container {
		display: flex;
		width: 1230px;
		height: 650px;
		justify-content: center;
    	align-items: center;
		margin-top: 2rem;
		margin-bottom: 2rem;
		gap: 2rem;
	}

	.main-container {
		display: grid;
		align-items: center;
		justify-items: center;
	}

	.intro-text-container {
		width: 650px;
	}

	section{
		width: 100vw;
	}

	.inline-container {
		display: flex;
		align-items: center;
	}
</style>

<svelte:head>
	<title>IV Semana Aratu</title>
	<meta name="description" content="Semana Aratu" />
</svelte:head>

<section>
	<div class="main-container">
		<div class="intro-container">
			<div class="intro-text-container">
				<h1 class="extra-large">Participe da Semana Aratu!</h1>
				<p class="poppins">
					Bem-vindo a mais uma edição da Semana Aratu.
					A IV edição do evento irá acontecer nos dias <HighlightedText value="24, 25, 26 e 27"/> de setembro de 2024.
				</p>
	
				<p class="poppins">
					A Semana Aratu é um evento feito da comunidade para a comunidade com a função de difundir conhecimentos a todos os interessados, o evento contará com quatro dias de palestras e um Capture The Flag.
				</p>
	
				<p class="poppins">
					As palestras do evento serao transmitidas ao vivo na <a href="twitch.tv/boitatech"><HighlightedText value="twitch.tv/boitatech"/></a> ou no <a href="youtube.com/boitatech"><HighlightedText value="youtube.com/boitatech"/> </a> nos dias e horarios informados abaixo.
				</p>
	
				<div class="inline-container"><HighlightedText value="Palestras" class="large"/> <p class="poppins">: Das 20h ate 22h</p></div>
				<div class="inline-container"><HighlightedText value="CTF" class="large"/> <p class="poppins">: Inicio dia 27 as 19:30 ate 29 as 21:00</p></div>
				
			</div>
		<img src={semanaaratulogo} draggable="false" alt="logo semana aratu" />
		</div>
	
		<div class="cards-container">
			<Selector />
			<CardPalestra/>
			<CardPalestra/>
		</div>
	
		<img src={semanaaratubg} alt="logo semana aratu" class="bg-image" />
	</div>
</section>
