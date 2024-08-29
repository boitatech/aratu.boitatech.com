<script>
    import boitatechlogo from '../../assets/boitatech-logo.png'
    import discordicon from '../../assets/Discord.svg'
</script>

<style>
    @import './index.css';
</style>
    
    <nav>
        <img src={boitatechlogo} class="nav-logo" alt="boitatech-logo" draggable="false" />
        <ul class="options-nav">
            <li><a href="https://www.boitatech.com" class="small">nosso site</a></li>
            <li><a href="aratu.boitatech.com" class="red small">semana aratu</a></li>
        </ul>

        <div class="add-buttons-container">
            <!-- <button class="lang-button small">
                PT/BR
            </button> -->
    
            <button class="discord-button">
                <a class="button-link" href="discord.gg/boitatech">
                    <img src={discordicon} alt="discord-logo">
                    <p class="button-text">
                        discord
                    </p>
                </a>
            </button>
        </div>
    </nav>
