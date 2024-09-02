<style>
	.cards-container {
		display: grid;
		justify-items: center;
		width: 100vw;
		gap: 1.8rem;
	}

	.bg-image {
		position: absolute;
		bottom: -63rem;
		left: -20rem;
		width: 1070px;
		z-index: -1;
	}

	@media (max-width: 840px) {
   	 	.bg-image {
   	 	  display: none;
   	 	}
  	}

	@media (max-width: 650px) {
   	 	.aratu-logo {
   	 	  width: 70%;
   	 	}
  	}

	.intro-container {
		display: flex;
		flex-wrap: wrap;
		width: 100%;
		/* height: 650px; */
		justify-content: center;
    	align-items: center;
		padding: 14rem 0 15rem 0;
		gap: 2rem;
	}

	.main-container {
		display: grid;
		align-items: center;
		justify-items: center;
	}

	.intro-text-container {
		width: 50%;
	}

	section{
		width: auto;
	}

	.inline-container {
		display: flex;
		align-items: center;
	}

	.ctf-container {
		padding: 2rem;
	}
</style>

<script>
    import CardPalestra from '../components/CardPalestra/index.svelte'
    import HighlightedText from '../components/HighlightedText/index.svelte'
    import Selector from '../components/Seletor/index.svelte'
    import semanaaratubg from '../assets/aratu-bg.png'
    import semanaaratulogo from '../assets/semana-aratu-logo.png'

    let selectedDate = '24.09.2024';
    let events = [
        { date: '24.09.2024', time: '19:00', topic: 'My Best Random Projects', speaker: 'Ciro Santili', description: 'Introduction to the OurBigBook Project plus a few quick "infosec" projects I\'ve done.' },
		{ date: '24.09.2024', time: '20:00', topic: 'Skills de kernelmode para debug de aplicações usermode', speaker: 'Gildásio Junior', description: 'A ideia é mostrar alguns conhecimentos de kernel linux, como montar ambiente, debugging de kernel, código, separação entre kernelmode e usermode, etc. Como um estudo de caso, mostrar um exemplo de uso desses conhecimentos até mesmo para debug de aplicações usermode, por exemplo: quando escrevemos um código, está errado mas não conseguimos identificar o erro pela documentação, o que fazer? Cair pra dentro do código do kernel :)' },
        { date: '24.09.2024', time: '21:00', topic: 'ScaryRF - Radiofrequências com Hardware Barato', speaker: 'Fernando "scaryhollow" Hansen', description: 'O Scary-RF Tool é um projeto raiz de Arduino, usando um ESP32, um módulo CC1101 e alguns componentes para criar uma ferramenta versátil de comunicação por rádio (RF). Com ela, você pode capturar e reproduzir sinais RF (o famoso Replay Attack) nas frequências de 315MHz ou 433.92MHz, enviar um código aleatório em 315-433Mhz e analisar qual frequência está recebendo 300-928Mhz.' },

		{ date: '25.09.2024', time: '19:00', topic: 'Lockpicking: Descomplicando a Arte de Abrir Fechaduras', speaker: 'Flávio Costa', description: '' },
		{ date: '25.09.2024', time: '20:00', topic: 'DevSecOps na Prática: Construindo uma esteira com ferramentas Open Source', speaker: 'Helena "molocohorror" Carreço', description: 'Nesta palestra exploraremos o universo das automações em cybersec, demonstrando de forma prática como integrar etapas de validação de segurança na pipeline, usando exclusivamente ferramentas Open Source. Partiremos do conceito de DevSecOps, passando pela implementação das ferramentas e chegando à entrega dos resultados numa ferramenta de gestão de vulnerabilidades.' },
		{ date: '25.09.2024', time: '21:00', topic: 'Coding for hacking', speaker: 'José Vitor', description: 'A palestra se resume no foco da criação de exploits, ferramentas entre outras automações para nosso dia a dia como profissional de segurança da informação. Buscando principalmente salientar a importância do profissional de segurança também saber programar. Coisas como, code review para exploração de um sistema. Elaboração de ferramentas de próprio punho. Criação dos próprios exploits. A ideia seria, explicar a conceito, apresentar casos de uso no âmbito real e por fim realizar um script para explorar uma vulnerabilidade em um ambiente controlado.' },

		{ date: '26.09.2024', time: '19:00', topic: 'Exploring WinSxS Vulnerabilities: Unveiling the Depths of DLL Side-Loading Attacks for Red Team Scenarios and Malware Tactics', speaker: 'Thiago Peixoto', description: 'DLL Side-Loading attacks, leveraging vulnerabilities within the Windows Side-by-Side Assembly (WinSxS) directory, present potent threats in both red team engagements and malware campaigns. This presentation explores the intricacies of WinSxS weaknesses, shedding light on how attackers exploit them to sideload malicious DLLs.6' },
		{ date: '26.09.2024', time: '20:00', topic: 'Secure Defaults - Scalling AppSec throught thousand developers', speaker: 'Ben-Hur Santos Ott', description: 'Escalar desenvolvimento seguro e soluções de segurança em times de desenvolvimento é um desafio considerável. As equipes de appsec costumam ser pequenas e a quantidade de trabalho no backlog parece ser infinita. Neste momento que implementar Secure Defaults pode ser uma excelente opção. Nesta talk vamos conhecer: O que é Secure Default; Casos reais de implementação; Quais os níveis de implementação e maturidade de cada controle; Como escalar a implementação dentro da empresa; Como integrar a prática em outras ações de segurança já estabelecidas, como Threat Modeling e Pentests.' },
		{ date: '26.09.2024', time: '21:00', topic: 'Além da Reverse Shell: Explorando a Complexidade das Infraestruturas de C&C', speaker: 'Francisco Marinho', description: 'Nesta palestra, vamos além do conceito de reverse shell comum, adentrando nas complexas infraestruturas de servidores de comando e controle (C&C). Exploraremos como atores de ameaças avançadas operam, oferecendo insights valiosos para equipes de defesa (blue teams) entenderem melhor esses ataques. Também abordaremos como equipes de ataque (red teams) podem começar a usar servidores de C&C em suas operações e engajamentos de forma eficaz.' },
	];

    function handleDateSelected(event) {
        selectedDate = event.detail.date;
    }

    $: filteredEvents = events.filter(event => event.date === selectedDate);
</script>

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
					Receba as boas vindas a mais uma edição da Semana Aratu!
					A IV edição do evento acontecerá nos dias <HighlightedText value="24, 25, 26, 27, 28 e 29"/> de setembro de 2024.
				</p>
	
				<p class="poppins">
					A Semana Aratu é um evento feito da comunidade para a comunidade, com a função de difundir conhecimentos a todas as pssoas interessadas. O evento contará com três dias de palestras e um CTF (Capture The Flag).
				</p>
	
				<p class="poppins">
					As palestras do evento serão transmitidas ao vivo na <a href="https://twitch.tv/boitatech"><HighlightedText value="twitch.tv/boitatech"/></a> e no <a href="https://youtube.com/boitatech"><HighlightedText value="youtube.com/boitatech"/> </a> nos dias e horários informados abaixo.
				</p>
	
				<div class="inline-container"><HighlightedText value="Palestras" class="large"/> <p class="poppins">: De 24 até 26/09, das 18h30 até às 22h</p></div>
				<div class="inline-container"><HighlightedText value="CTF" class="large"/> <p class="poppins">: Início dia 27/09 às 00h e término dia 29/09 às 23h59</p></div>
				
			</div>
		<img src={semanaaratulogo} class="aratu-logo" draggable="false" alt="logo semana aratu" />
		</div>
    
        <div class="cards-container">
            <Selector on:dateSelected={handleDateSelected} />
            {#each filteredEvents as event}
                <CardPalestra {event} />
			{/each}
        </div>
		
		<div class="intro-container">
			<div class="ctf-container">
				<h1 class="extra-large">Sobre o CTF</h1>
				<h1>Participe do CTF da Semana Aratu! 🔥🐍</h1>
				<p class="medium">
	
				Início: 27/09 às 00:00
				<br>
				Encerramento: 29/09 às 23:59
				</p>
	
				<p class="medium">
				Os prêmios serão:
				<br>
				1º Lugar - $300 HTB on Annual Plans Discount Code, 4 meses Mullvad, voucher CRTO, ingresso da <a href="https://www.h2hc.com.br/" target="_blank">H2HC</a>
				<br>
				2º Lugar - 50$ on Annual Plans Discount Code, 4 meses Mullvad, Binary Ninja, ingresso da <a href="https://www.h2hc.com.br/" target="_blank">H2HC</a>
				<br>
				3º Lugar - 4 meses Mullvad, ingresso da <a href="https://www.h2hc.com.br/" target="_blank">H2HC</a>
	
				</p>
			</div>
		</div>
    
        <img src={semanaaratubg} alt="logo semana aratu" class="bg-image" />
    </div>
</section>

