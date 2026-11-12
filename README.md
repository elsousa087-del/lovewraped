# lovewraped
Faça uma retrospectiva e mostre todo seu amor>
```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Nossa Retrospectiva de Amor</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts: Montserrat, Plus Jakarta Sans & Lora (para a carta romântica) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Lora:ital,wght@0,500;0,600;1,400;1,600&family=Montserrat:wght@800;900&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">

    <style>
        :root {
            --primary: #FF2E93;
            --secondary: #8338EC;
            --accent: #FFBE0B;
            --bg-dark: #100618;
        }

        * {
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            user-select: none;
        }

        input, textarea, select {
            user-select: text;
        }

        body {
            font-family: 'Plus Jakarta Sans', system-ui, -apple-system, sans-serif;
            background-color: #050507;
            color: #ffffff;
            overflow: hidden;
            margin: 0;
            padding: 0;
            height: 100dvh;
            width: 100vw;
        }

        .font-display {
            font-family: 'Montserrat', system-ui, -apple-system, sans-serif;
            letter-spacing: -0.03em;
        }

        .font-letter {
            font-family: 'Lora', Georgia, serif;
        }

        /* Animações das Formas Geométricas Fluidas no Fundo */
        @keyframes floatSlow {
            0%, 100% { transform: translate(0, 0) rotate(0deg) scale(1); }
            33% { transform: translate(28px, -36px) rotate(10deg) scale(1.08); }
            66% { transform: translate(-22px, 24px) rotate(-8deg) scale(0.95); }
        }

        @keyframes spinSlow {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        @keyframes pulseGlow {
            0%, 100% { opacity: 0.6; transform: scale(1); }
            50% { opacity: 0.95; transform: scale(1.12); }
        }

        @keyframes heartbeat {
            0%, 100% { transform: scale(1); }
            15% { transform: scale(1.18); }
            30% { transform: scale(1); }
            45% { transform: scale(1.12); }
            60% { transform: scale(1); }
        }

        @keyframes slideUpFade {
            0% { opacity: 0; transform: translateY(28px) scale(0.96); }
            100% { opacity: 1; transform: translateY(0) scale(1); }
        }

        @keyframes popIn {
            0% { opacity: 0; transform: scale(0.78) rotate(-2deg); }
            70% { transform: scale(1.03) rotate(1deg); }
            100% { opacity: 1; transform: scale(1) rotate(0deg); }
        }

        @keyframes equalizer {
            0%, 100% { height: 22%; }
            50% { height: 100%; }
        }

        .animate-float {
            animation: floatSlow 11s ease-in-out infinite;
        }

        .animate-float-reverse {
            animation: floatSlow 14s ease-in-out infinite reverse;
        }

        .animate-spin-slow {
            animation: spinSlow 26s linear infinite;
        }

        .animate-pulse-glow {
            animation: pulseGlow 6s ease-in-out infinite;
        }

        .animate-heartbeat {
            animation: heartbeat 2s ease-in-out infinite;
        }

        .slide-enter {
            animation: slideUpFade 0.5s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }

        .slide-enter-delay-1 {
            opacity: 0;
            animation: slideUpFade 0.5s cubic-bezier(0.16, 1, 0.3, 1) 0.1s forwards;
        }

        .slide-enter-delay-2 {
            opacity: 0;
            animation: slideUpFade 0.5s cubic-bezier(0.16, 1, 0.3, 1) 0.2s forwards;
        }

        .slide-enter-delay-3 {
            opacity: 0;
            animation: popIn 0.6s cubic-bezier(0.16, 1, 0.3, 1) 0.3s forwards;
        }

        .slide-enter-delay-4 {
            opacity: 0;
            animation: slideUpFade 0.5s cubic-bezier(0.16, 1, 0.3, 1) 0.38s forwards;
        }

        .eq-bar {
            animation: equalizer 0.85s ease-in-out infinite;
        }

        /* Padrão de Grid Abstrato */
        .bg-grid-pattern {
            background-image: linear-gradient(to right, rgba(255,255,255,0.055) 1px, transparent 1px),
                              linear-gradient(to bottom, rgba(255,255,255,0.055) 1px, transparent 1px);
            background-size: 34px 34px;
        }

        /* Esconder scrollbar mantendo rolagem fluida */
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }

        /* Modo Print / Limpo */
        body.clean-mode .ui-chrome {
            opacity: 0 !important;
            pointer-events: none !important;
        }
    </style>
</head>
<body class="flex items-center justify-center bg-black">

    <!-- Container Principal (Formato Vertical Stories 9:16 em Desktop, Tela Cheia no Mobile) -->
    <main id="app-frame" class="relative w-full h-full sm:w-[430px] sm:h-[90dvh] sm:max-h-[880px] sm:rounded-[38px] overflow-hidden shadow-[0_0_90px_rgba(0,0,0,0.95)] sm:border sm:border-white/15 bg-[#100618] flex flex-col justify-between transition-colors duration-700">

        <!-- Elemento de Áudio Real para Trilha Sonora do Casal -->
        <audio id="couple-audio-player" loop preload="auto" class="hidden"></audio>

        <!-- Camada de Fundo Geométrico Abstrato Animado -->
        <div id="bg-shapes-layer" class="absolute inset-0 overflow-hidden pointer-events-none z-0 transition-all duration-700"></div>

        <!-- Overlay de Grid -->
        <div class="absolute inset-0 bg-grid-pattern opacity-45 pointer-events-none z-0"></div>

        <!-- Cabeçalho: Barras de Progresso + Controles Superiores -->
        <header class="ui-chrome relative z-30 pt-4 px-4 pb-2 transition-opacity duration-300">
            <!-- Barras de Progresso Segmentadas -->
            <div id="progress-bars-container" class="flex gap-1.5 w-full mb-3"></div>

            <!-- Barra de Identificação e Ações -->
            <div class="flex items-center justify-between">
                <div class="flex items-center gap-2 min-w-0">
                    <div id="brand-dot" class="w-3 h-3 rounded-full shrink-0 bg-[#FF2E93] shadow-[0_0_12px_#FF2E93]"></div>
                    <span class="text-[11px] font-extrabold tracking-widest uppercase text-white/90 truncate">NOSSO WRAPPED • <span id="header-since-year">DESDE 2023</span></span>
                </div>

                <div class="flex items-center gap-1.5 shrink-0">
                    <!-- Botão Reiniciar -->
                    <button id="btn-restart" type="button" title="Reiniciar Retrospectiva" class="p-2 rounded-full bg-black/35 hover:bg-black/60 backdrop-blur-md border border-white/10 text-white/90 transition active:scale-90 cursor-pointer">
                        <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 12a9 9 0 1 0 9-9 9.75 9.75 0 0 0-6.74 2.74L3 8"/><path d="M3 3v5h5"/></svg>
                    </button>
                    <!-- Botão Som / Trilha Romântica -->
                    <button id="btn-sound" type="button" title="Ativar/Desativar Trilha Sonora" class="p-2 rounded-full bg-black/35 hover:bg-black/60 backdrop-blur-md border border-white/10 text-white/90 transition active:scale-90 cursor-pointer">
                        <span id="icon-sound-wrap" class="flex items-center justify-center">
                            <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polygon points="11 5 6 9 2 9 2 15 6 15 11 19 11 5"/><line x1="23" y1="9" x2="17" y2="15"/><line x1="17" y1="9" x2="23" y2="15"/></svg>
                        </span>
                    </button>
                    <!-- Botão Pausar/Continuar -->
                    <button id="btn-pause" type="button" title="Pausar/Continuar" class="p-2 rounded-full bg-black/35 hover:bg-black/60 backdrop-blur-md border border-white/10 text-white/90 transition active:scale-90 cursor-pointer">
                        <span id="icon-pause-wrap" class="flex items-center justify-center">
                            <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><rect x="6" y="4" width="4" height="16"/><rect x="14" y="4" width="4" height="16"/></svg>
                        </span>
                    </button>
                    <!-- Botão Modo Print Limpo -->
                    <button id="btn-clean" type="button" title="Modo Print (Ocultar Controles)" class="p-2 rounded-full bg-black/35 hover:bg-black/60 backdrop-blur-md border border-white/10 text-white/90 transition active:scale-90 cursor-pointer">
                        <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M14.5 4h-5L7 7H4a2 2 0 0 0-2 2v9a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V9a2 2 0 0 0-2-2h-3l-2.5-3z"/><circle cx="12" cy="13" r="3"/></svg>
                    </button>
                </div>
            </div>
        </header>

        <!-- Zonas de Toque / Clique para Navegação (Esquerda = Voltar, Direita = Avançar) -->
        <div class="absolute inset-0 z-20 flex">
            <div id="tap-prev" class="w-1/3 h-full cursor-pointer" title="Slide Anterior"></div>
            <div id="tap-next" class="w-2/3 h-full cursor-pointer" title="Próximo Slide"></div>
        </div>

        <!-- Área Central do Conteúdo do Slide -->
        <section id="slide-content" class="relative z-10 flex-1 flex flex-col justify-center px-6 py-2 pointer-events-none overflow-hidden">
            <!-- Conteúdo do slide atual renderizado via JavaScript -->
        </section>

        <!-- Rodapé com Botão de Personalização e Compartilhar -->
        <footer class="ui-chrome relative z-30 p-5 pt-2 flex items-center justify-between gap-2.5 transition-opacity duration-300">
            <button id="btn-open-editor" type="button" class="flex-1 py-3.5 px-5 rounded-full bg-white text-black font-extrabold text-sm tracking-tight flex items-center justify-center gap-2 shadow-[0_8px_25px_rgba(0,0,0,0.45)] hover:scale-[1.02] active:scale-95 transition cursor-pointer">
                <svg class="w-4 h-4 text-pink-600" viewBox="0 0 24 24" fill="currentColor"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>
                <span>Editar História</span>
            </button>

            <button id="btn-share-toast" type="button" title="Copiar Declaração & Resumo" class="p-3.5 rounded-full bg-black/45 hover:bg-black/70 backdrop-blur-md border border-white/15 text-white transition active:scale-90 cursor-pointer">
                <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><circle cx="18" cy="5" r="3"/><circle cx="6" cy="12" r="3"/><circle cx="18" cy="19" r="3"/><line x1="8.59" y1="13.51" x2="15.42" y2="17.49"/><line x1="15.41" y1="6.51" x2="8.59" y2="10.49"/></svg>
            </button>
        </footer>

        <!-- Botão Flutuante para Sair do Modo Print (visível apenas no modo limpo) -->
        <button id="btn-exit-clean" type="button" class="hidden fixed bottom-6 left-1/2 -translate-x-1/2 z-50 px-5 py-2.5 rounded-full bg-black/85 text-white text-xs font-bold border border-white/25 backdrop-blur-md shadow-2xl cursor-pointer">
            Toque para mostrar controles
        </button>

        <!-- Toast / Notificação Flutuante -->
        <div id="toast-box" class="pointer-events-none fixed top-20 left-1/2 -translate-x-1/2 z-50 px-4 py-2.5 rounded-full bg-white text-black text-xs font-extrabold shadow-2xl opacity-0 -translate-y-3 transition-all duration-300 flex items-center gap-2 whitespace-nowrap">
            <svg class="w-4 h-4 text-pink-600" viewBox="0 0 24 24" fill="currentColor"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>
            <span id="toast-message">Resumo copiado!</span>
        </div>

        <!-- MODAL: Painel "Personalizar Nossa História" -->
        <div id="editor-modal" class="hidden absolute inset-0 z-40 bg-[#0B0910]/96 backdrop-blur-2xl flex flex-col justify-between p-5 sm:p-6 overflow-y-auto no-scrollbar">
            <div>
                <div class="flex items-center justify-between mb-4">
                    <div>
                        <span class="text-[11px] font-extrabold uppercase tracking-widest text-[#FF2E93]">Personalizar Nossa História</span>
                        <h2 class="font-display text-xl sm:text-2xl font-black text-white">Edite a Retrospectiva</h2>
                    </div>
                    <button id="btn-close-editor" type="button" class="p-2.5 rounded-full bg-white/10 hover:bg-white/20 text-white transition cursor-pointer">
                        <svg class="w-5 h-5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
                    </button>
                </div>

                <form id="love-form" class="space-y-4 text-left">
                    <!-- 1. Nomes do Casal e Data de Início -->
                    <div class="grid grid-cols-2 gap-2.5">
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1">Pessoa 1</label>
                            <input type="text" id="input-person1" maxlength="18" required placeholder="Ex: Lucas"
                                class="w-full px-3.5 py-2.5 rounded-2xl bg-white/10 border border-white/15 text-white text-sm font-semibold placeholder-white/40 focus:outline-none focus:border-white transition">
                        </div>
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1">Pessoa 2</label>
                            <input type="text" id="input-person2" maxlength="18" required placeholder="Ex: Mariana"
                                class="w-full px-3.5 py-2.5 rounded-2xl bg-white/10 border border-white/15 text-white text-sm font-semibold placeholder-white/40 focus:outline-none focus:border-white transition">
                        </div>
                    </div>

                    <div>
                        <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1">Data de Início do Relacionamento</label>
                        <input type="date" id="input-start-date" required
                            class="w-full px-3.5 py-2.5 rounded-2xl bg-white/10 border border-white/15 text-white text-sm font-semibold focus:outline-none focus:border-white transition">
                    </div>

                    <!-- 2. Gerenciador de Até 10 Fotos -->
                    <div class="p-3.5 rounded-2xl bg-white/5 border border-white/15 space-y-2.5">
                        <div class="flex items-center justify-between">
                            <span class="text-[11px] font-extrabold uppercase tracking-wider text-[#FF2E93] flex items-center gap-1.5">
                                <svg class="w-3.5 h-3.5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="3" width="18" height="18" rx="2" ry="2"/><circle cx="8.5" cy="8.5" r="1.5"/><polyline points="21 15 16 10 5 21"/></svg>
                                <span>Galeria de Fotos (<span id="photo-counter-badge">0/10</span>)</span>
                            </span>
                            <label for="input-photos-batch" id="btn-add-photos-label" class="px-3 py-1.5 rounded-xl bg-[#FF2E93] hover:brightness-110 text-white text-[11px] font-extrabold flex items-center gap-1 cursor-pointer transition active:scale-95">
                                <svg class="w-3.5 h-3.5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
                                <span>Adicionar Fotos</span>
                            </label>
                            <input type="file" id="input-photos-batch" accept="image/*" multiple class="hidden">
                        </div>

                        <p class="text-[10px] font-medium text-white/55 leading-tight">
                            Adicione até 10 fotos do casal e escolha no seletor de cada foto em qual slide ela deve aparecer.
                        </p>

                        <!-- Lista Dinâmica de Fotos Carregadas -->
                        <div id="photos-manager-list" class="space-y-2 max-h-56 overflow-y-auto pr-0.5">
                            <!-- Miniaturas e seletores de slide renderizados via JS -->
                        </div>
                    </div>

                    <!-- 3. Momento Inesquecível #1 -->
                    <div class="space-y-2">
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1">Momento Inesquecível #1 (Título)</label>
                            <input type="text" id="input-moment" maxlength="44" required placeholder="Ex: Nosso primeiro pôr do sol na praia"
                                class="w-full px-3.5 py-2.5 rounded-2xl bg-white/10 border border-white/15 text-white text-sm font-semibold placeholder-white/40 focus:outline-none focus:border-white transition">
                        </div>
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1">Descrição do Momento #1</label>
                            <input type="text" id="input-moment-desc" maxlength="90" placeholder="Ex: Conversamos por horas vendo o céu ficar laranja e soubemos que era pra sempre."
                                class="w-full px-3.5 py-2 rounded-2xl bg-white/10 border border-white/15 text-white text-xs font-semibold placeholder-white/40 focus:outline-none focus:border-white transition">
                        </div>
                    </div>

                    <!-- 4. Top 5 Coisas que mais fizeram juntos -->
                    <div>
                        <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1.5">Top 5 Coisas que Mais Fizemos Juntos</label>
                        <div class="space-y-1.5">
                            <input type="text" id="input-top1" maxlength="34" required placeholder="#1 Ex: Maratonar séries agarradinhos"
                                class="w-full px-3.5 py-2 rounded-xl bg-white/10 border border-white/15 text-white text-xs font-semibold placeholder-white/40 focus:outline-none focus:border-white">
                            <input type="text" id="input-top2" maxlength="34" required placeholder="#2 Ex: Pedir lanche de madrugada"
                                class="w-full px-3.5 py-2 rounded-xl bg-white/10 border border-white/15 text-white text-xs font-semibold placeholder-white/40 focus:outline-none focus:border-white">
                            <input type="text" id="input-top3" maxlength="34" required placeholder="#3 Ex: Rir de besteira até perder o ar"
                                class="w-full px-3.5 py-2 rounded-xl bg-white/10 border border-white/15 text-white text-xs font-semibold placeholder-white/40 focus:outline-none focus:border-white">
                            <input type="text" id="input-top4" maxlength="34" required placeholder="#4 Ex: Cantar no carro como num show"
                                class="w-full px-3.5 py-2 rounded-xl bg-white/10 border border-white/15 text-white text-xs font-semibold placeholder-white/40 focus:outline-none focus:border-white">
                            <input type="text" id="input-top5" maxlength="34" required placeholder="#5 Ex: Planejar nossas próximas viagens"
                                class="w-full px-3.5 py-2 rounded-xl bg-white/10 border border-white/15 text-white text-xs font-semibold placeholder-white/40 focus:outline-none focus:border-white">
                        </div>
                    </div>

                    <!-- 5. Música do Casal (Busca Online iTunes + Upload Local) -->
                    <div class="space-y-2.5">
                        <div>
                            <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1">Nossa Música (Título Exibido)</label>
                            <input type="text" id="input-song" maxlength="52" required placeholder="Ex: Don't Let Me Down - The Beatles"
                                class="w-full px-3.5 py-2.5 rounded-2xl bg-white/10 border border-white/15 text-white text-sm font-semibold placeholder-white/40 focus:outline-none focus:border-white transition">
                        </div>

                        <div class="p-3.5 rounded-2xl bg-white/5 border border-white/15 space-y-2.5">
                            <div class="flex items-center justify-between">
                                <span class="text-[11px] font-extrabold uppercase tracking-wider text-[#FFBE0B] flex items-center gap-1.5">
                                    <svg class="w-3.5 h-3.5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 18V5l12-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="18" cy="16" r="3"/></svg>
                                    <span>Trilha Sonora & Áudio</span>
                                </span>
                                <button type="button" id="btn-remove-audio" class="hidden text-[11px] font-bold text-rose-400 hover:underline cursor-pointer">
                                    Usar trilha nativa
                                </button>
                            </div>

                            <!-- Pesquisa Online (iTunes Search API) -->
                            <div class="flex gap-1.5">
                                <input type="text" id="input-music-search" placeholder="Pesquisar música ou artista..."
                                    class="flex-1 min-w-0 px-3 py-2 rounded-xl bg-black/40 border border-white/15 text-white text-xs font-semibold placeholder-white/45 focus:outline-none focus:border-[#FF2E93] transition">
                                <button type="button" id="btn-music-search" class="px-3.5 py-2 rounded-xl bg-[#FF2E93] hover:brightness-110 text-white text-xs font-extrabold flex items-center gap-1 shrink-0 transition active:scale-95 cursor-pointer">
                                    <svg class="w-3.5 h-3.5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"/><line x1="21" y1="21" x2="16.65" y2="16.65"/></svg>
                                    <span>Buscar</span>
                                </button>
                            </div>

                            <div id="music-search-status" class="hidden text-[11px] font-semibold text-white/70 text-center py-1.5"></div>
                            <div id="music-search-results" class="hidden max-h-48 overflow-y-auto space-y-1.5 pr-0.5"></div>

                            <div class="flex items-center gap-2 text-[10px] font-bold uppercase tracking-wider text-white/40">
                                <div class="flex-1 h-px bg-white/10"></div>
                                <span>ou envie do aparelho</span>
                                <div class="flex-1 h-px bg-white/10"></div>
                            </div>

                            <label for="input-audio" class="w-full px-3.5 py-2.5 rounded-xl bg-white/10 hover:bg-white/15 border border-dashed border-white/30 text-white text-xs font-bold flex items-center justify-center gap-2 cursor-pointer transition">
                                <svg class="w-4 h-4 shrink-0 text-[#FF2E93]" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"/><polyline points="17 8 12 3 7 8"/><line x1="12" y1="3" x2="12" y2="15"/></svg>
                                <span id="audio-label-text" class="truncate">Carregar MP3 / WAV / M4A / OGG</span>
                            </label>
                            <input type="file" id="input-audio" accept="audio/*" class="hidden">
                            <p id="audio-status-hint" class="text-[10px] font-medium text-white/55 leading-tight">
                                Pesquise qualquer música acima ou envie um arquivo. Sem áudio, uma melodia suave via Web Audio toca ao ativar o som.
                            </p>
                        </div>
                    </div>

                    <!-- 6. Declaração do Pôster Final (Slide 6) -->
                    <div>
                        <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1">Frase Curta do Pôster Final (Slide 6)</label>
                        <input type="text" id="input-quote" maxlength="75" required placeholder="Ex: Cada segundo ao seu lado é o meu lugar favorito."
                            class="w-full px-3.5 py-2.5 rounded-2xl bg-white/10 border border-white/15 text-white text-sm font-semibold placeholder-white/40 focus:outline-none focus:border-white transition">
                    </div>

                    <!-- 7. Carta Romântica Opcional (Slide 7) -->
                    <div class="p-3.5 rounded-2xl bg-white/5 border border-white/15 space-y-2.5">
                        <label class="flex items-center justify-between cursor-pointer">
                            <span class="text-[11px] font-extrabold uppercase tracking-wider text-amber-300 flex items-center gap-1.5">
                                <svg class="w-3.5 h-3.5" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
                                <span>Incluir Slide 7: Carta Romântica</span>
                            </span>
                            <input type="checkbox" id="input-enable-letter" checked class="w-4 h-4 accent-[#FF2E93] rounded cursor-pointer">
                        </label>

                        <div id="letter-editor-fields" class="space-y-2">
                            <input type="text" id="input-letter-title" maxlength="40" placeholder="Título da Carta (Ex: Para o amor da minha vida,)"
                                class="w-full px-3.5 py-2 rounded-xl bg-black/40 border border-white/15 text-white text-xs font-semibold placeholder-white/40 focus:outline-none focus:border-amber-300">
                            <textarea id="input-letter-body" rows="4" maxlength="900" placeholder="Escreva sua carta personalizada aqui... Quebras de linha serão mantidas!"
                                class="w-full px-3.5 py-2.5 rounded-xl bg-black/40 border border-white/15 text-white text-xs font-medium leading-relaxed placeholder-white/40 focus:outline-none focus:border-amber-300 resize-none"></textarea>
                        </div>
                    </div>

                    <!-- 8. Seletor de Temas de Cores -->
                    <div>
                        <label class="block text-[11px] font-bold uppercase tracking-wider text-white/70 mb-1.5">Paleta de Cores</label>
                        <div id="theme-selector" class="grid grid-cols-2 gap-2"></div>
                    </div>
                </form>
            </div>

            <!-- Botões de Ação do Modal -->
            <div class="pt-4 mt-4 border-t border-white/10 flex gap-2.5">
                <button type="button" id="btn-fill-example" class="px-3.5 py-3.5 rounded-2xl bg-white/10 hover:bg-white/20 text-white font-bold text-xs flex items-center justify-center gap-1.5 transition cursor-pointer shrink-0">
                    <svg class="w-4 h-4 text-amber-300" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="m12 3-1.912 5.813a2 2 0 0 1-1.275 1.275L3 12l5.813 1.912a2 2 0 0 1 1.275 1.275L12 21l1.912-5.813a2 2 0 0 1 1.275-1.275L21 12l-5.813-1.912a2 2 0 0 1-1.275-1.275L12 3Z"/></svg>
                    <span>Exemplo Romântico</span>
                </button>
                <button type="submit" form="love-form" class="flex-1 py-3.5 px-4 rounded-2xl bg-[#FF2E93] hover:brightness-110 text-white font-extrabold text-sm shadow-lg transition active:scale-95 cursor-pointer">
                    Salvar & Ver História
                </button>
            </div>
        </div>

    </main>

    <script>
        /**
         * NOSSA RETROSPECTIVA DE AMOR (ESTILO SPOTIFY WRAPPED)
         * Código 100% autocontido em arquivo único:
         * - Até 7 Slides interativos estilo Stories (com Slide 7 de Carta Romântica opcional)
         * - Gerenciador de até 10 fotos com escolha individual de qual slide exibir cada foto
         * - Player de áudio real + Busca Online via iTunes Search API + Fallback Web Audio API nativa
         */

        const ICONS = {
            volumeOn: '<svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polygon points="11 5 6 9 2 9 2 15 6 15 11 19 11 5"/><path d="M15.54 8.46a5 5 0 0 1 0 7.07"/><path d="M19.07 4.93a10 10 0 0 1 0 14.14"/></svg>',
            volumeOff: '<svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polygon points="11 5 6 9 2 9 2 15 6 15 11 19 11 5"/><line x1="23" y1="9" x2="17" y2="15"/><line x1="17" y1="9" x2="23" y2="15"/></svg>',
            pause: '<svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><rect x="6" y="4" width="4" height="16"/><rect x="14" y="4" width="4" height="16"/></svg>',
            play: '<svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polygon points="5 3 19 12 5 21 5 3"/></svg>'
        };

        // Destinos disponíveis para cada foto carregada
        const SLIDE_TARGETS = [
            { value: 'none', label: 'Não exibir (Oculta)' },
            { value: '0', label: 'Slide 1 - Capa' },
            { value: '2', label: 'Slide 3 - Momento #1' },
            { value: '3', label: 'Slide 4 - Top 5' },
            { value: '4', label: 'Slide 5 - Trilha Sonora' },
            { value: '5', label: 'Slide 6 - Pôster Final' },
            { value: '6', label: 'Slide 7 - Carta' }
        ];

        // Paletas de Temas Românticos Vibrantes
        const THEMES = [
            {
                id: 'paixao-neon',
                name: 'Paixão Neon',
                primary: '#FF2E93',
                secondary: '#8338EC',
                accent: '#FFBE0B',
                bg: '#100618',
                cardBg: 'rgba(255, 46, 147, 0.16)',
                textOnPrimary: '#FFFFFF'
            },
            {
                id: 'por-do-sol',
                name: 'Pôr do Sol',
                primary: '#FF6B4A',
                secondary: '#72092B',
                accent: '#FFD166',
                bg: '#16070B',
                cardBg: 'rgba(255, 107, 74, 0.16)',
                textOnPrimary: '#FFFFFF'
            },
            {
                id: 'noite-estrelada',
                name: 'Noite Estrelada',
                primary: '#00F5D4',
                secondary: '#3A0CA3',
                accent: '#F72585',
                bg: '#060B19',
                cardBg: 'rgba(0, 245, 212, 0.14)',
                textOnPrimary: '#050811'
            },
            {
                id: 'minimalista-pb',
                name: 'Minimalista P&B',
                primary: '#FFFFFF',
                secondary: '#52525B',
                accent: '#D4D4D8',
                bg: '#09090B',
                cardBg: 'rgba(255, 255, 255, 0.10)',
                textOnPrimary: '#09090B'
            }
        ];

        const ROMANTIC_EXAMPLES = [
            {
                person1: 'Lucas',
                person2: 'Mariana',
                startDate: '2023-06-12',
                moment: 'Nosso primeiro pôr do sol na praia',
                momentDesc: 'Ficamos horas olhando o mar e soubemos ali que nossa história seria inesquecível.',
                top5: [
                    'Maratonar séries agarradinhos',
                    'Pedir lanche de madrugada',
                    'Rir de besteira até perder o ar',
                    'Cantar no carro como num show',
                    'Planejar nossas próximas viagens'
                ],
                song: "Don't Let Me Down - The Beatles",
                quote: 'Cada segundo ao seu lado é o meu lugar favorito no mundo.',
                letterTitle: 'Para o amor da minha vida,',
                letterBody: 'Olhar para trás e ver tudo o que já vivemos me enche de orgulho e carinho.\n\nObrigado por ser meu porto seguro, meu melhor sorriso nos dias difíceis e a minha companhia favorita em qualquer lugar.\n\nQue essa retrospectiva seja apenas o começo de muitos outros anos juntos. Eu te amo infinito!',
                themeId: 'paixao-neon'
            },
            {
                person1: 'Gabriel',
                person2: 'Camila',
                startDate: '2022-09-18',
                moment: 'A viagem surpresa de aniversário',
                momentDesc: 'Mala pronta sem destino revelado e o melhor final de semana das nossas vidas.',
                top5: [
                    'Cozinhar juntos ouvindo música',
                    'Tomar café da manhã na cama',
                    'Fazer chamadas de vídeo de horas',
                    'Trocar memes o dia inteiro',
                    'Dançar na sala de casa'
                ],
                song: 'Partilhar - Rubel & ANAVITÓRIA',
                quote: 'Se eu pudesse escolher de novo, escolheria você mil vezes.',
                letterTitle: 'Meu amor,',
                letterBody: 'Desde que você entrou na minha vida, até os dias mais comuns ganharam cor e trilha sonora.\n\nAmo cada mania nossa, cada risada fora de hora e a paz que sinto quando estou com você.\n\nTe amo hoje, amanhã e sempre!',
                themeId: 'por-do-sol'
            },
            {
                person1: 'Matheus',
                person2: 'Beatriz',
                startDate: '2024-02-14',
                moment: 'O dia em que olhamos as estrelas no mirante',
                momentDesc: 'Frio lá fora, música baixa no carro e a certeza de que eu já tinha encontrado tudo.',
                top5: [
                    'Ir ao cinema de última hora',
                    'Experimentar cafeterias novas',
                    'Dormir de conchinha na chuva',
                    'Tirar fotos espontâneas juntos',
                    'Torcer juntos no sofá'
                ],
                song: 'Golden Hour - JVKE',
                quote: 'Nosso amor é a melhor história que eu já vivi.',
                letterTitle: 'Para sempre nós,',
                letterBody: 'Cada dia ao seu lado me faz ter ainda mais certeza de que somos feitos um para o outro.\n\nObrigado por dividir sonhos, planos e tantos momentos incríveis comigo. Vamos conquistar o mundo juntos!',
                themeId: 'noite-estrelada'
            }
        ];

        // Estado Central da Aplicação
        const state = {
            currentSlide: 0,
            isPaused: false,
            soundEnabled: false,
            slideDuration: 6500,
            progress: 0,
            lastFrameTime: null,
            counterAnimFrame: null,
            data: {
                person1: 'Lucas',
                person2: 'Mariana',
                startDate: '2023-06-12',
                // Array de até 10 fotos: { id, dataUrl, targetSlide }
                photos: [],
                moment: 'Nosso primeiro pôr do sol na praia',
                momentDesc: 'Ficamos horas olhando o mar e soubemos ali que nossa história seria inesquecível.',
                top5: [
                    'Maratonar séries agarradinhos',
                    'Pedir lanche de madrugada',
                    'Rir de besteira até perder o ar',
                    'Cantar no carro como num show',
                    'Planejar nossas próximas viagens'
                ],
                song: "Don't Let Me Down - The Beatles",
                quote: 'Cada segundo ao seu lado é o meu lugar favorito no mundo.',
                enableLetter: true,
                letterTitle: 'Para o amor da minha vida,',
                letterBody: 'Olhar para trás e ver tudo o que já vivemos me enche de orgulho e carinho.\n\nObrigado por ser meu porto seguro, meu melhor sorriso nos dias difíceis e a minha companhia favorita em qualquer lugar.\n\nQue essa retrospectiva seja apenas o começo de muitos outros anos juntos. Eu te amo infinito!',
                themeId: 'paixao-neon'
            },
            audioFileUrl: null,
            audioFileName: null,
            audioSourceType: 'synth', // 'synth' | 'itunes' | 'local'
            albumArtworkUrl: null,
            previewingUrl: null
        };

        const previewTesterAudio = new Audio();
        previewTesterAudio.volume = 0.85;

        function getTotalSlides() {
            return state.data.enableLetter ? 7 : 6;
        }

        function getPhotosForSlide(slideIndex) {
            return state.data.photos.filter(p => String(p.targetSlide) === String(slideIndex));
        }

        function escapeHtml(str) {
            const div = document.createElement('div');
            div.textContent = String(str || '');
            return div.innerHTML;
        }

        // Controle de Áudio Real (<audio>) + Fallback Melodia via Web Audio API Nativa
        const audioEl = document.getElementById('couple-audio-player');
        let fadeInterval = null;
        let webAudioCtx = null;
        let webAudioTimer = null;
        let chordStep = 0;

        const ROMANTIC_FREQS = [
            [261.63, 329.63, 392.00, 493.88],
            [220.00, 261.63, 329.63, 392.00],
            [174.61, 220.00, 261.63, 329.63],
            [196.00, 246.94, 293.66, 329.63]
        ];

        function playWebAudioChord(freqs) {
            try {
                if (!webAudioCtx) {
                    const AudioCtx = window.AudioContext || window.webkitAudioContext;
                    if (!AudioCtx) return;
                    webAudioCtx = new AudioCtx();
                }
                if (webAudioCtx.state === 'suspended') {
                    webAudioCtx.resume();
                }
                const now = webAudioCtx.currentTime;
                freqs.forEach((freq) => {
                    const osc = webAudioCtx.createOscillator();
                    const gain = webAudioCtx.createGain();
                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(freq, now);

                    gain.gain.setValueAtTime(0.0001, now);
                    gain.gain.exponentialRampToValueAtTime(0.03, now + 0.35);
                    gain.gain.exponentialRampToValueAtTime(0.0001, now + 1.8);

                    osc.connect(gain);
                    gain.connect(webAudioCtx.destination);

                    osc.start(now);
                    osc.stop(now + 1.85);
                });
            } catch (e) {
                console.warn('Web Audio API indisponível:', e);
            }
        }

        function playSoftChime(index) {
            if (!state.soundEnabled || state.audioFileUrl) return;
            const notes = [523.25, 587.33, 659.25, 783.99, 880.00, 1046.50, 1174.66];
            playWebAudioChord([notes[index % notes.length]]);
        }

        function startWebAudioFallback() {
            stopWebAudioFallback();
            playWebAudioChord(ROMANTIC_FREQS[chordStep % ROMANTIC_FREQS.length]);
            chordStep++;
            webAudioTimer = setInterval(() => {
                if (!state.soundEnabled || state.audioFileUrl) {
                    stopWebAudioFallback();
                    return;
                }
                playWebAudioChord(ROMANTIC_FREQS[chordStep % ROMANTIC_FREQS.length]);
                chordStep++;
            }, 1900);
        }

        function stopWebAudioFallback() {
            if (webAudioTimer) {
                clearInterval(webAudioTimer);
                webAudioTimer = null;
            }
        }

        function fadeAudioVolume(targetVol, duration = 600, onComplete = null) {
            if (fadeInterval) clearInterval(fadeInterval);
            const steps = 20;
            const stepTime = duration / steps;
            const startVol = audioEl.volume;
            const delta = (targetVol - startVol) / steps;
            let count = 0;

            fadeInterval = setInterval(() => {
                count++;
                const nextVol = Math.max(0, Math.min(1, startVol + delta * count));
                audioEl.volume = nextVol;
                if (count >= steps) {
                    clearInterval(fadeInterval);
                    fadeInterval = null;
                    audioEl.volume = targetVol;
                    if (onComplete) onComplete();
                }
            }, stepTime);
        }

        function formatAudioTime(seconds) {
            if (!isFinite(seconds) || seconds < 0) return '0:00';
            const mins = Math.floor(seconds / 60);
            const secs = Math.floor(seconds % 60);
            return `${mins}:${secs < 10 ? '0' : ''}${secs}`;
        }

        async function startRomanticSoundtrack() {
            if (state.audioFileUrl && audioEl.src) {
                stopWebAudioFallback();
                try {
                    audioEl.crossOrigin = 'anonymous';
                    audioEl.volume = 0;
                    await audioEl.play();
                    fadeAudioVolume(0.85, 700);
                } catch (err) {
                    console.warn('Reprodução aguardando interação do usuário:', err);
                }
                return;
            }
            startWebAudioFallback();
        }

        function stopRomanticSoundtrack() {
            stopWebAudioFallback();
            if (!audioEl.paused) {
                fadeAudioVolume(0, 450, () => {
                    audioEl.pause();
                });
            }
        }

        // Cálculo do tempo vivido juntos a partir da data de início
        function calculateLoveStats(startDateStr) {
            const now = new Date();
            const parsed = new Date(`${startDateStr}T00:00:00`);
            const start = isNaN(parsed.getTime()) ? new Date('2023-06-12T00:00:00') : parsed;

            const diffMs = Math.max(86400000, now.getTime() - start.getTime());
            const totalMinutes = Math.floor(diffMs / 60000);
            const totalHours = Math.floor(diffMs / 3600000);
            const totalDays = Math.floor(diffMs / 86400000);
            const totalMonths = Math.max(1, Math.floor(totalDays / 30.4375));
            const years = Math.floor(totalDays / 365.25);
            const remainingDays = Math.floor(totalDays % 365.25);

            const formattedDate = start.toLocaleDateString('pt-BR', {
                day: '2-digit',
                month: 'long',
                year: 'numeric'
            });

            return {
                startYear: start.getFullYear(),
                formattedDate,
                totalDays,
                totalHours,
                totalMinutes,
                totalMonths,
                years,
                remainingDays
            };
        }

        function getActiveTheme() {
            return THEMES.find(t => t.id === state.data.themeId) || THEMES[0];
        }

        function formatNumber(num) {
            return Number(num || 0).toLocaleString('pt-BR');
        }

        function animateCounter(elementId, targetValue, duration = 1200) {
            if (state.counterAnimFrame) cancelAnimationFrame(state.counterAnimFrame);
            const el = document.getElementById(elementId);
            if (!el) return;

            const startTime = performance.now();
            function update(now) {
                const elapsed = now - startTime;
                const progress = Math.min(elapsed / duration, 1);
                const eased = 1 - Math.pow(1 - progress, 4);
                const current = Math.floor(eased * targetValue);
                el.textContent = formatNumber(current);
                if (progress < 1) {
                    state.counterAnimFrame = requestAnimationFrame(update);
                } else {
                    el.textContent = formatNumber(targetValue);
                }
            }
            state.counterAnimFrame = requestAnimationFrame(update);
        }

        const dom = {
            appFrame: document.getElementById('app-frame'),
            bgShapes: document.getElementById('bg-shapes-layer'),
            progressContainer: document.getElementById('progress-bars-container'),
            slideContent: document.getElementById('slide-content'),
            brandDot: document.getElementById('brand-dot'),
            headerSinceYear: document.getElementById('header-since-year'),
            editorModal: document.getElementById('editor-modal'),
            themeSelector: document.getElementById('theme-selector'),
            toastBox: document.getElementById('toast-box'),
            toastMsg: document.getElementById('toast-message'),
            iconPauseWrap: document.getElementById('icon-pause-wrap'),
            iconSoundWrap: document.getElementById('icon-sound-wrap'),
            btnExitClean: document.getElementById('btn-exit-clean')
        };

        function renderProgressBars() {
            const total = getTotalSlides();
            dom.progressContainer.innerHTML = '';
            for (let i = 0; i < total; i++) {
                const track = document.createElement('div');
                track.className = 'h-1 flex-1 bg-white/25 rounded-full overflow-hidden';
                const fill = document.createElement('div');
                fill.id = `progress-fill-${i}`;
                fill.className = 'h-full bg-white rounded-full transition-none';
                fill.style.width = i < state.currentSlide ? '100%' : '0%';
                track.appendChild(fill);
                dom.progressContainer.appendChild(track);
            }
        }

        function updateBackgroundShapes() {
            const theme = getActiveTheme();
            const stats = calculateLoveStats(state.data.startDate);
            dom.appFrame.style.backgroundColor = theme.bg;
            dom.brandDot.style.backgroundColor = theme.primary;
            dom.brandDot.style.boxShadow = `0 0 14px ${theme.primary}`;
            dom.headerSinceYear.textContent = `DESDE ${stats.startYear}`;

            const idx = state.currentSlide;
            const shapesConfigs = [
                `
                <div class="animate-float absolute -top-16 -right-16 w-72 h-72 rounded-full blur-2xl opacity-60" style="background: ${theme.primary}"></div>
                <div class="animate-float-reverse absolute -bottom-20 -left-16 w-80 h-80 rounded-full blur-3xl opacity-55" style="background: ${theme.secondary}"></div>
                <div class="animate-spin-slow absolute top-1/4 -left-12 w-44 h-44 border-[14px] rounded-full opacity-25" style="border-color: ${theme.accent}"></div>
                `,
                `
                <div class="animate-pulse-glow absolute top-1/3 left-1/2 -translate-x-1/2 -translate-y-1/2 w-80 h-80 rounded-full blur-3xl opacity-50" style="background: ${theme.secondary}"></div>
                <div class="animate-float absolute bottom-12 right-6 w-48 h-48 rounded-full border-[18px] opacity-30" style="border-color: ${theme.primary}"></div>
                <div class="animate-float-reverse absolute top-16 left-8 w-24 h-24 rotate-45 rounded-2xl opacity-35" style="background: ${theme.accent}"></div>
                `,
                `
                <div class="animate-spin-slow absolute -top-20 left-1/2 -translate-x-1/2 w-96 h-96 rounded-[72px] opacity-30 blur-xl" style="background: linear-gradient(135deg, ${theme.primary}, ${theme.secondary})"></div>
                <div class="animate-float absolute bottom-20 -left-10 w-56 h-56 rounded-full opacity-45 blur-2xl" style="background: ${theme.accent}"></div>
                `,
                `
                <div class="animate-float absolute top-14 -right-12 w-64 h-64 rounded-full opacity-50 blur-2xl" style="background: ${theme.primary}"></div>
                <div class="animate-spin-slow absolute bottom-16 left-10 w-40 h-40 border-[12px] border-dashed rounded-full opacity-30" style="border-color: ${theme.accent}"></div>
                `,
                `
                <div class="animate-pulse-glow absolute inset-x-4 top-24 h-80 rounded-[48px] blur-3xl opacity-45" style="background: linear-gradient(180deg, ${theme.primary}, ${theme.secondary})"></div>
                <div class="animate-float-reverse absolute -bottom-10 right-6 w-52 h-52 rotate-12 rounded-full border-[10px] opacity-25" style="border-color: ${theme.accent}"></div>
                `,
                `
                <div class="animate-float absolute -top-12 -left-12 w-72 h-72 rounded-full blur-3xl opacity-55" style="background: ${theme.primary}"></div>
                <div class="animate-float-reverse absolute -bottom-12 -right-12 w-72 h-72 rounded-full blur-3xl opacity-55" style="background: ${theme.secondary}"></div>
                `,
                `
                <div class="animate-pulse-glow absolute top-10 right-4 w-64 h-64 rounded-full blur-3xl opacity-45" style="background: ${theme.accent}"></div>
                <div class="animate-float absolute bottom-10 left-4 w-72 h-72 rounded-full blur-3xl opacity-50" style="background: ${theme.primary}"></div>
                `
            ];

            dom.bgShapes.innerHTML = shapesConfigs[idx] || shapesConfigs[0];
        }

        // Helper para renderizar galeria de fotos atribuídas a um slide específico
        function renderSlidePhotoStrip(photos, theme, heightClass = 'h-36') {
            if (!photos || photos.length === 0) return '';
            if (photos.length === 1) {
                return `
                    <div class="slide-enter-delay-2 w-full ${heightClass} rounded-3xl overflow-hidden border-2 shadow-xl" style="border-color: ${theme.primary};">
                        <img src="${photos[0].dataUrl}" alt="Foto do casal" class="w-full h-full object-cover">
                    </div>
                `;
            }
            const cols = photos.length === 2 ? 'grid-cols-2' : 'grid-cols-3';
            return `
                <div class="slide-enter-delay-2 grid ${cols} gap-2 w-full">
                    ${photos.slice(0, 6).map(p => `
                        <div class="${heightClass} rounded-2xl overflow-hidden border border-white/25 shadow-lg">
                            <img src="${p.dataUrl}" alt="Foto do casal" class="w-full h-full object-cover">
                        </div>
                    `).join('')}
                </div>
            `;
        }

        // Renderiza o Slide Atual
        function renderCurrentSlide() {
            const theme = getActiveTheme();
            const { person1, person2, startDate, moment, momentDesc, top5, song, quote, letterTitle, letterBody } = state.data;
            const stats = calculateLoveStats(startDate);
            const coupleNames = `${escapeHtml(person1)} & ${escapeHtml(person2)}`;
            const slidePhotos = getPhotosForSlide(state.currentSlide);

            let html = '';

            switch (state.currentSlide) {
                case 0: // SLIDE 1: CAPA / BOAS-VINDAS
                    html = `
                        <div class="space-y-4">
                            <div class="slide-enter inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full text-xs font-extrabold uppercase tracking-wider shadow-lg"
                                 style="background: ${theme.primary}; color: ${theme.textOnPrimary};">
                                <span>♥</span>
                                <span>Nossa Retrospectiva</span>
                            </div>

                            ${renderSlidePhotoStrip(slidePhotos, theme, slidePhotos.length > 1 ? 'h-28' : 'h-44')}

                            <h1 class="slide-enter-delay-1 font-display ${slidePhotos.length ? 'text-3xl sm:text-4xl' : 'text-4xl sm:text-[44px]'} font-black leading-[1.03] tracking-tight text-white">
                                <span style="color: ${theme.primary};">${escapeHtml(person1)}</span> & <span style="color: ${theme.accent};">${escapeHtml(person2)}</span>.<br>
                                Nossa história em números.
                            </h1>

                            <p class="slide-enter-delay-2 text-sm sm:text-base text-white/85 font-medium leading-relaxed">
                                Tudo começou em <span class="font-extrabold text-white underline decoration-2" style="text-decoration-color:${theme.primary};">${stats.formattedDate}</span>. Veja tudo o que construímos juntos desde então.
                            </p>

                            <div class="slide-enter-delay-3 pt-2 flex items-center gap-3">
                                <div class="w-10 h-10 rounded-2xl flex items-center justify-center shadow-lg animate-heartbeat"
                                     style="background: ${theme.primary}; color: ${theme.textOnPrimary};">
                                    <svg class="w-5 h-5" viewBox="0 0 24 24" fill="currentColor"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>
                                </div>
                                <div>
                                    <div class="text-xs font-extrabold uppercase tracking-wider text-white">Capítulo Especial</div>
                                    <div class="text-xs font-semibold text-white/60">Toque na direita para avançar →</div>
                                </div>
                            </div>
                        </div>
                    `;
                    break;

                case 1: // SLIDE 2: O TEMPO JUNTOS
                    html = `
                        <div class="space-y-4">
                            <span class="slide-enter inline-block text-xs font-extrabold uppercase tracking-widest px-3 py-1 rounded-full bg-white/10 text-white/90">
                                O Tempo Juntos
                            </span>

                            <h2 class="slide-enter-delay-1 font-display text-3xl sm:text-4xl font-black leading-tight">
                                Cada instante valeu a pena.
                            </h2>

                            <div class="slide-enter-delay-2 p-5 sm:p-6 rounded-[32px] border border-white/20 backdrop-blur-xl shadow-2xl"
                                 style="background: ${theme.cardBg};">
                                <div id="animated-days-counter" class="font-display text-5xl sm:text-6xl font-black tracking-tighter leading-none"
                                     style="color: ${theme.primary};">
                                    0
                                </div>
                                <div class="text-lg font-extrabold uppercase tracking-wider text-white mt-1.5">
                                    dias de amor vivido
                                </div>
                                <div class="text-xs font-bold text-white/75 mt-1.5">
                                    ${stats.years > 0 ? `${stats.years} ${stats.years === 1 ? 'ano' : 'anos'}, ${stats.totalMonths} meses e ${stats.remainingDays} dias` : `${stats.totalMonths} ${stats.totalMonths === 1 ? 'mês' : 'meses'} de história`}
                                </div>
                            </div>

                            <div class="slide-enter-delay-3 grid grid-cols-2 gap-2.5">
                                <div class="p-3.5 rounded-2xl bg-white/10 backdrop-blur-md border border-white/10">
                                    <div class="text-[11px] font-bold uppercase text-white/60">Em Horas</div>
                                    <div class="font-display text-xl font-black mt-0.5" style="color: ${theme.accent};">${formatNumber(stats.totalHours)}h</div>
                                </div>
                                <div class="p-3.5 rounded-2xl bg-white/10 backdrop-blur-md border border-white/10">
                                    <div class="text-[11px] font-bold uppercase text-white/60">Em Minutos</div>
                                    <div class="font-display text-xl font-black mt-0.5 text-white">${formatNumber(stats.totalMinutes)}</div>
                                </div>
                            </div>
                        </div>
                    `;
                    break;

                case 2: // SLIDE 3: MOMENTO INESQUECÍVEL #1
                    html = `
                        <div class="space-y-4">
                            <span class="slide-enter inline-block text-xs font-extrabold uppercase tracking-widest px-3 py-1 rounded-full bg-white/10 text-white/90">
                                Destaque Absoluto
                            </span>

                            <h2 class="slide-enter-delay-1 font-display text-2xl sm:text-3xl font-black leading-tight">
                                Um momento ficou gravado na memória.
                            </h2>

                            ${renderSlidePhotoStrip(slidePhotos, theme, slidePhotos.length > 1 ? 'h-24' : 'h-36')}

                            <div class="slide-enter-delay-2 relative p-5 sm:p-6 rounded-[30px] overflow-hidden border border-white/25 shadow-2xl"
                                 style="background: linear-gradient(135deg, ${theme.primary}, ${theme.secondary});">

                                <div class="flex items-center justify-between mb-3">
                                    <span class="px-3 py-1 rounded-full text-[11px] font-extrabold uppercase tracking-wider bg-black/25 backdrop-blur-md"
                                          style="color: ${theme.textOnPrimary};">
                                        Top Hit • Momento #1
                                    </span>
                                    <div class="w-8 h-8 rounded-full bg-black/20 flex items-center justify-center animate-heartbeat"
                                         style="color: ${theme.textOnPrimary};">
                                        <svg class="w-4 h-4" viewBox="0 0 24 24" fill="currentColor"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>
                                    </div>
                                </div>

                                <div class="font-display text-xl sm:text-2xl font-black leading-snug break-words"
                                     style="color: ${theme.textOnPrimary};">
                                    “${escapeHtml(moment)}”
                                </div>

                                ${momentDesc ? `
                                    <p class="mt-2 text-xs sm:text-sm font-semibold opacity-90 leading-relaxed" style="color: ${theme.textOnPrimary};">
                                        ${escapeHtml(momentDesc)}
                                    </p>
                                ` : ''}

                                <div class="mt-3 pt-2.5 border-t border-black/15 flex items-center justify-between text-[11px] font-extrabold opacity-85"
                                     style="color: ${theme.textOnPrimary};">
                                    <span>Replay infinito no coração</span>
                                    <span>#1 do Casal</span>
                                </div>
                            </div>
                        </div>
                    `;
                    break;

                case 3: // SLIDE 4: TOP 5 COISAS QUE MAIS FIZEMOS JUNTOS
                    const validTop5 = top5.slice(0, 5);
                    html = `
                        <div class="space-y-3">
                            <div class="slide-enter">
                                <span class="inline-block text-[11px] font-extrabold uppercase tracking-widest px-3 py-1 rounded-full bg-white/10 text-white/90 mb-1.5">
                                    Nossas Manias & Rolês
                                </span>
                                <h2 class="font-display text-2xl sm:text-3xl font-black leading-tight">
                                    Top 5 coisas que mais fizemos juntos
                                </h2>
                            </div>

                            ${renderSlidePhotoStrip(slidePhotos, theme, 'h-20')}

                            <div class="space-y-1.5 pt-0.5">
                                ${validTop5.map((item, idx) => `
                                    <div class="slide-enter-delay-${Math.min(idx, 4)} flex items-center gap-3 p-2.5 sm:p-3 rounded-2xl bg-black/45 border border-white/15 backdrop-blur-xl shadow-lg">
                                        <div class="w-7 h-7 rounded-xl font-display font-black text-sm flex items-center justify-center shrink-0"
                                             style="background: ${idx === 0 ? theme.primary : 'rgba(255,255,255,0.12)'}; color: ${idx === 0 ? theme.textOnPrimary : '#FFFFFF'};">
                                            ${idx + 1}
                                        </div>
                                        <div class="text-xs sm:text-sm font-bold text-white leading-snug line-clamp-2">
                                            ${escapeHtml(item)}
                                        </div>
                                    </div>
                                `).join('')}
                            </div>
                        </div>
                    `;
                    break;

                case 4: // SLIDE 5: TRILHA SONORA & SINTONIA DO CASAL
                    const hasRealAudio = Boolean(state.audioFileUrl);
                    const initialPct = (hasRealAudio && audioEl.duration) ? Math.min(100, (audioEl.currentTime / audioEl.duration) * 100) : 65;
                    const initialCurrTime = hasRealAudio ? formatAudioTime(audioEl.currentTime) : '1:42';
                    const initialDurTime = (hasRealAudio && audioEl.duration) ? formatAudioTime(audioEl.duration) : '3:35';
                    const sourceBadge = state.audioSourceType === 'itunes'
                        ? 'Prévia Oficial • Apple Music'
                        : (state.audioSourceType === 'local' ? 'Arquivo Oficial Carregado' : 'Nossa Música #1');

                    const coverSrc = state.albumArtworkUrl || (slidePhotos[0] ? slidePhotos[0].dataUrl : null);
                    const albumCoverHtml = coverSrc
                        ? `<img src="${escapeHtml(coverSrc)}" alt="Capa" class="w-14 h-14 rounded-2xl shrink-0 object-cover shadow-lg border border-white/25">`
                        : `<div class="w-14 h-14 rounded-2xl shrink-0 flex items-center justify-center shadow-lg"
                                style="background: linear-gradient(135deg, ${theme.primary}, ${theme.secondary}); color: ${theme.textOnPrimary};">
                               <svg class="w-7 h-7" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><path d="M9 18V5l12-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="18" cy="16" r="3"/></svg>
                           </div>`;

                    html = `
                        <div class="space-y-4">
                            <span class="slide-enter inline-block text-xs font-extrabold uppercase tracking-widest px-3 py-1 rounded-full"
                                  style="background:${theme.accent}; color:#050505;">
                                Química & Sintonia
                            </span>

                            <div class="slide-enter-delay-1 flex items-end justify-between p-4 rounded-3xl bg-white/10 border border-white/15 backdrop-blur-md">
                                <div>
                                    <div class="text-xs font-bold uppercase tracking-wider text-white/70">Índice de Conexão</div>
                                    <div class="font-display text-4xl sm:text-5xl font-black leading-none mt-1" style="color: ${theme.primary};">
                                        99,9%
                                    </div>
                                </div>
                                <div class="text-right">
                                    <span class="text-xs font-extrabold px-2.5 py-1 rounded-full bg-white/15 text-white">Almas Gêmeas</span>
                                </div>
                            </div>

                            ${slidePhotos.length > 0 && state.albumArtworkUrl ? renderSlidePhotoStrip(slidePhotos, theme, 'h-24') : ''}

                            <div class="slide-enter-delay-2 p-5 rounded-[30px] bg-black/60 border border-white/15 backdrop-blur-xl shadow-2xl space-y-3.5">
                                <div class="flex items-center justify-between">
                                    <span class="text-[11px] font-extrabold uppercase tracking-widest text-white/60">
                                        ${sourceBadge}
                                    </span>
                                    <div class="flex items-end gap-1 h-5">
                                        <span class="eq-bar w-1 rounded-full" style="background:${theme.primary}; animation-delay:0.0s"></span>
                                        <span class="eq-bar w-1 rounded-full" style="background:${theme.accent}; animation-delay:0.25s"></span>
                                        <span class="eq-bar w-1 rounded-full" style="background:${theme.primary}; animation-delay:0.1s"></span>
                                        <span class="eq-bar w-1 rounded-full" style="background:${theme.accent}; animation-delay:0.35s"></span>
                                    </div>
                                </div>

                                <div class="flex items-center gap-3.5">
                                    ${albumCoverHtml}
                                    <div class="min-w-0">
                                        <div class="font-display text-lg sm:text-xl font-black text-white leading-tight break-words">
                                            ${escapeHtml(song)}
                                        </div>
                                        <div class="text-xs font-bold mt-1" style="color: ${theme.primary};">
                                            Trilha oficial de ${coupleNames}
                                        </div>
                                    </div>
                                </div>

                                <div class="pt-1 space-y-1.5">
                                    <div class="w-full h-1.5 rounded-full bg-white/20 overflow-hidden">
                                        <div id="slide-audio-progress" class="h-full rounded-full transition-all duration-150" style="width: ${initialPct}%; background: ${theme.primary};"></div>
                                    </div>
                                    <div class="flex items-center justify-between text-[10px] font-bold text-white/55">
                                        <span id="slide-audio-current">${initialCurrTime}</span>
                                        <span>${state.soundEnabled ? '🔊 Som Ativo' : '🔇 Toque no som no topo'}</span>
                                        <span id="slide-audio-duration">${initialDurTime}</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    `;
                    break;

                case 5: // SLIDE 6: PÔSTER FINAL COMPARTILHÁVEL
                    const posterPhoto = slidePhotos[0] || state.data.photos[0] || null;
                    const avatarHtml = posterPhoto
                        ? `<img src="${posterPhoto.dataUrl}" alt="Foto do casal" class="w-20 h-20 rounded-full object-cover border-[3px] shadow-xl shrink-0" style="border-color: ${theme.primary};">`
                        : `<div class="w-20 h-20 rounded-full flex items-center justify-center border-[3px] shadow-xl shrink-0" style="border-color: ${theme.primary}; background: linear-gradient(135deg, ${theme.primary}, ${theme.secondary}); color: ${theme.textOnPrimary};">
                               <svg class="w-9 h-9 animate-heartbeat" viewBox="0 0 24 24" fill="currentColor"><path d="M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z"/></svg>
                           </div>`;

                    html = `
                        <div class="slide-enter w-full">
                            <div class="p-5 rounded-[32px] border border-white/25 backdrop-blur-2xl shadow-[0_20px_60px_rgba(0,0,0,0.75)] relative overflow-hidden"
                                 style="background: linear-gradient(160deg, rgba(22,18,28,0.94) 0%, rgba(10,10,14,0.98) 100%);">

                                <div class="absolute top-0 inset-x-0 h-2" style="background: linear-gradient(90deg, ${theme.primary}, ${theme.accent}, ${theme.secondary});"></div>

                                <div class="flex items-center gap-3.5 pt-1 mb-3.5">
                                    ${avatarHtml}
                                    <div class="min-w-0">
                                        <div class="text-[10px] font-extrabold uppercase tracking-widest" style="color: ${theme.primary};">
                                            Nossa Retrospectiva
                                        </div>
                                        <div class="font-display text-xl font-black text-white leading-tight truncate">
                                            ${coupleNames}
                                        </div>
                                        <div class="text-[11px] font-semibold text-white/65 mt-0.5">
                                            Desde ${stats.formattedDate}
                                        </div>
                                    </div>
                                </div>

                                <div class="space-y-2.5 my-3">
                                    <div class="grid grid-cols-2 gap-2">
                                        <div class="p-3 rounded-2xl bg-white/5 border border-white/10">
                                            <div class="text-[10px] font-extrabold uppercase tracking-wider text-white/55">Tempo Juntos</div>
                                            <div class="font-display text-lg font-black mt-0.5" style="color: ${theme.primary};">${formatNumber(stats.totalDays)} dias</div>
                                        </div>
                                        <div class="p-3 rounded-2xl bg-white/5 border border-white/10">
                                            <div class="text-[10px] font-extrabold uppercase tracking-wider text-white/55">Sintonia</div>
                                            <div class="font-display text-lg font-black mt-0.5" style="color: ${theme.accent};">99,9% ♥</div>
                                        </div>
                                    </div>

                                    <div class="p-3 rounded-2xl bg-white/5 border border-white/10">
                                        <div class="text-[10px] font-extrabold uppercase tracking-wider text-white/55">Momento Inesquecível #1</div>
                                        <div class="text-xs sm:text-sm font-extrabold text-white mt-0.5 line-clamp-2">${escapeHtml(moment)}</div>
                                    </div>

                                    <div class="p-3 rounded-2xl bg-white/5 border border-white/10">
                                        <div class="text-[10px] font-extrabold uppercase tracking-wider text-white/55">Nossa Música</div>
                                        <div class="text-xs sm:text-sm font-extrabold text-white mt-0.5 truncate">🎵 ${escapeHtml(song)}</div>
                                    </div>
                                </div>

                                <p class="text-xs italic font-semibold text-white/85 text-center px-2 py-2 rounded-xl bg-white/5">
                                    “${escapeHtml(quote)}”
                                </p>

                                <div class="mt-3 pt-2 border-t border-white/10 flex items-center justify-between text-[10px] font-extrabold uppercase tracking-wider text-white/50">
                                    <span>Wrapped do Amor</span>
                                    <span style="color: ${theme.primary};">♥ Para Sempre</span>
                                </div>
                            </div>
                        </div>
                    `;
                    break;

                case 6: // SLIDE 7: CARTA ROMÂNTICA OPCIONAL
                    const formattedLetterBody = escapeHtml(letterBody).replace(/\n/g, '<br>');
                    html = `
                        <div class="slide-enter w-full">
                            <div class="p-5 sm:p-6 rounded-[30px] shadow-[0_20px_60px_rgba(0,0,0,0.8)] border border-amber-200/40 relative overflow-hidden"
                                 style="background: linear-gradient(165deg, #FFFDF7 0%, #F7EFE2 100%); color: #1F1916;">

                                <!-- Selo Postal Romântico -->
                                <div class="flex items-center justify-between pb-3 mb-3 border-b border-stone-300/80">
                                    <div class="flex items-center gap-2">
                                        <span class="w-7 h-7 rounded-full flex items-center justify-center text-white text-xs shadow" style="background: ${theme.primary};">♥</span>
                                        <div>
                                            <div class="text-[9px] font-extrabold uppercase tracking-widest text-stone-500">Carta Especial</div>
                                            <div class="text-xs font-extrabold text-stone-800">${coupleNames}</div>
                                        </div>
                                    </div>
                                    <span class="px-2.5 py-1 rounded-lg border border-dashed border-stone-400 text-[9px] font-extrabold uppercase tracking-wider text-stone-600">
                                        ${stats.formattedDate}
                                    </span>
                                </div>

                                ${slidePhotos.length > 0 ? `
                                    <div class="mb-3 rounded-2xl overflow-hidden border border-stone-300 shadow-sm h-28">
                                        <img src="${slidePhotos[0].dataUrl}" alt="Foto da carta" class="w-full h-full object-cover">
                                    </div>
                                ` : ''}

                                <h3 class="font-letter italic font-semibold text-lg sm:text-xl text-stone-900 mb-2.5">
                                    ${escapeHtml(letterTitle || 'Para você,')}
                                </h3>

                                <div class="font-letter text-xs sm:text-[13.5px] leading-relaxed text-stone-800 max-h-56 overflow-y-auto no-scrollbar pr-1">
                                    ${formattedLetterBody}
                                </div>

                                <div class="mt-4 pt-2.5 border-t border-stone-300/80 flex items-center justify-between text-[11px] font-bold text-stone-600">
                                    <span class="font-letter italic">Com todo o meu amor,</span>
                                    <span style="color: ${theme.primary};" class="font-extrabold">♥ ${escapeHtml(person1)}</span>
                                </div>
                            </div>
                        </div>
                    `;
                    break;
            }

            dom.slideContent.innerHTML = html;
            updateBackgroundShapes();

            if (state.currentSlide === 1) {
                animateCounter('animated-days-counter', stats.totalDays, 1200);
            }
        }

        function goToSlide(index) {
            const total = getTotalSlides();
            if (index < 0) index = 0;
            if (index >= total) {
                index = 0;
            }
            state.currentSlide = index;
            state.progress = 0;

            for (let i = 0; i < total; i++) {
                const fill = document.getElementById(`progress-fill-${i}`);
                if (fill) {
                    fill.style.width = i < state.currentSlide ? '100%' : '0%';
                }
            }

            renderCurrentSlide();
            playSoftChime(state.currentSlide);
        }

        function nextSlide() {
            goToSlide(state.currentSlide + 1);
        }

        function prevSlide() {
            if (state.progress > 22) {
                state.progress = 0;
                renderCurrentSlide();
            } else {
                goToSlide(state.currentSlide - 1);
            }
        }

        function progressLoop(timestamp) {
            if (!state.lastFrameTime) state.lastFrameTime = timestamp;
            const delta = timestamp - state.lastFrameTime;
            state.lastFrameTime = timestamp;

            if (!state.isPaused && dom.editorModal.classList.contains('hidden')) {
                state.progress += (delta / state.slideDuration) * 100;
                const currentFill = document.getElementById(`progress-fill-${state.currentSlide}`);
                if (currentFill) {
                    currentFill.style.width = `${Math.min(state.progress, 100)}%`;
                }

                if (state.progress >= 100) {
                    nextSlide();
                }
            }

            requestAnimationFrame(progressLoop);
        }

        // Renderiza o Gerenciador de até 10 Fotos no Modal
        function renderPhotosManager() {
            const listEl = document.getElementById('photos-manager-list');
            const badgeEl = document.getElementById('photo-counter-badge');
            const addLabel = document.getElementById('btn-add-photos-label');

            badgeEl.textContent = `${state.data.photos.length}/10`;
            if (state.data.photos.length >= 10) {
                addLabel.classList.add('opacity-45', 'pointer-events-none');
            } else {
                addLabel.classList.remove('opacity-45', 'pointer-events-none');
            }

            if (state.data.photos.length === 0) {
                listEl.innerHTML = `
                    <div class="py-3 px-3 rounded-xl bg-black/35 border border-dashed border-white/15 text-center text-[11px] text-white/50 font-semibold">
                        Nenhuma foto adicionada ainda. Toque em "+ Adicionar Fotos" acima.
                    </div>
                `;
                return;
            }

            listEl.innerHTML = state.data.photos.map((photo, idx) => `
                <div class="p-2 rounded-xl bg-black/45 border border-white/10 flex items-center gap-2.5">
                    <img src="${photo.dataUrl}" alt="Foto ${idx + 1}" class="w-11 h-11 rounded-lg object-cover shrink-0 border border-white/20">
                    <div class="flex-1 min-w-0">
                        <div class="text-[10px] font-extrabold uppercase tracking-wider text-white/60 mb-1">Foto #${idx + 1} • Exibir em:</div>
                        <select data-photo-id="${photo.id}" class="photo-target-select w-full px-2.5 py-1.5 rounded-lg bg-white/10 border border-white/15 text-white text-xs font-bold focus:outline-none focus:border-[#FF2E93]">
                            ${SLIDE_TARGETS.map(opt => `
                                <option value="${opt.value}" class="bg-[#14111D] text-white" ${String(photo.targetSlide) === opt.value ? 'selected' : ''}>
                                    ${opt.label}
                                </option>
                            `).join('')}
                        </select>
                    </div>
                    <button type="button" data-remove-photo-id="${photo.id}" title="Remover foto" class="p-2 rounded-lg bg-rose-500/15 hover:bg-rose-500/30 text-rose-400 transition shrink-0 cursor-pointer">
                        <svg class="w-4 h-4" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2" stroke-linecap="round" stroke-linejoin="round"><polyline points="3 6 5 6 21 6"/><path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"/></svg>
                    </button>
                </div>
            `).join('');

            listEl.querySelectorAll('.photo-target-select').forEach(sel => {
                sel.addEventListener('change', (e) => {
                    const photoObj = state.data.photos.find(p => p.id === sel.dataset.photoId);
                    if (photoObj) {
                        photoObj.targetSlide = e.target.value;
                    }
                });
            });

            listEl.querySelectorAll('[data-remove-photo-id]').forEach(btn => {
                btn.addEventListener('click', () => {
                    const idToRemove = btn.dataset.removePhotoId;
                    state.data.photos = state.data.photos.filter(p => p.id !== idToRemove);
                    renderPhotosManager();
                });
            });
        }

        function renderThemeSelector() {
            dom.themeSelector.innerHTML = THEMES.map(theme => {
                const isSelected = theme.id === state.data.themeId;
                return `
                    <button type="button" data-theme-id="${theme.id}"
                        class="theme-option p-2.5 rounded-2xl border text-left flex items-center gap-2 transition cursor-pointer ${isSelected ? 'border-white bg-white/15 scale-[1.02]' : 'border-white/10 bg-white/5 hover:bg-white/10'}">
                        <span class="w-4 h-4 rounded-full shrink-0 shadow-md border border-white/20" style="background: linear-gradient(135deg, ${theme.primary}, ${theme.secondary});"></span>
                        <span class="text-xs font-extrabold text-white truncate">${theme.name}</span>
                    </button>
                `;
            }).join('');

            document.querySelectorAll('.theme-option').forEach(btn => {
                btn.addEventListener('click', () => {
                    state.data.themeId = btn.dataset.themeId;
                    renderThemeSelector();
                });
            });
        }

        function syncModalAudioPreview() {
            const label = document.getElementById('audio-label-text');
            const removeBtn = document.getElementById('btn-remove-audio');
            const hint = document.getElementById('audio-status-hint');
            if (state.audioSourceType === 'itunes' && state.audioFileName) {
                label.textContent = 'Trocar por arquivo MP3 / WAV / M4A / OGG';
                removeBtn.classList.remove('hidden');
                hint.textContent = `Trilha online ativa: ${state.audioFileName} (prévia de 30s em loop).`;
                hint.classList.add('text-emerald-400');
            } else if (state.audioSourceType === 'local' && state.audioFileName) {
                label.textContent = state.audioFileName;
                removeBtn.classList.remove('hidden');
                hint.textContent = 'Arquivo local carregado! Ative o ícone de volume no topo para ouvir.';
                hint.classList.add('text-emerald-400');
            } else {
                label.textContent = 'Carregar MP3 / WAV / M4A / OGG';
                removeBtn.classList.add('hidden');
                hint.textContent = 'Pesquise qualquer música acima ou envie um arquivo. Sem áudio, uma melodia suave via Web Audio toca ao ativar o som.';
                hint.classList.remove('text-emerald-400');
            }
        }

        function stopPreviewTester() {
            previewTesterAudio.pause();
            previewTesterAudio.currentTime = 0;
            state.previewingUrl = null;
            document.querySelectorAll('.btn-preview-track').forEach(btn => {
                btn.innerHTML = `${ICONS.play}<span>Ouvir prévia</span>`;
                btn.classList.remove('bg-[#FF2E93]', 'text-white');
                btn.classList.add('bg-white/10', 'text-white/90');
            });
        }

        async function searchItunesMusic(query) {
            const statusEl = document.getElementById('music-search-status');
            const resultsEl = document.getElementById('music-search-results');
            const trimmed = (query || '').trim();

            if (!trimmed) {
                showToast('Digite o nome de uma música ou artista!');
                return;
            }

            stopPreviewTester();
            statusEl.textContent = 'Buscando faixas...';
            statusEl.classList.remove('hidden');
            resultsEl.classList.add('hidden');
            resultsEl.innerHTML = '';

            try {
                const url = `https://itunes.apple.com/search?term=${encodeURIComponent(trimmed)}&media=music&entity=song&limit=6`;
                const response = await fetch(url);
                if (!response.ok) throw new Error('Falha na resposta da iTunes API');
                const data = await response.json();
                const tracks = (data.results || []).filter(item => item.previewUrl);

                if (tracks.length === 0) {
                    statusEl.textContent = 'Nenhuma música encontrada. Tente outro termo.';
                    return;
                }

                statusEl.classList.add('hidden');
                resultsEl.classList.remove('hidden');

                resultsEl.innerHTML = tracks.map((track) => {
                    const art60 = track.artworkUrl60 || track.artworkUrl100 || '';
                    const artLarge = (track.artworkUrl100 || art60).replace('100x100bb', '300x300bb');
                    const title = track.trackName || 'Faixa sem título';
                    const artist = track.artistName || 'Artista';
                    const previewUrl = track.previewUrl;

                    return `
                        <div class="p-2.5 rounded-2xl bg-black/50 border border-white/10 flex items-center gap-2.5">
                            <img src="${escapeHtml(art60)}" alt="Capa" class="w-11 h-11 rounded-xl object-cover shrink-0 bg-white/10">
                            <div class="min-w-0 flex-1">
                                <div class="text-xs font-extrabold text-white truncate">${escapeHtml(title)}</div>
                                <div class="text-[11px] font-semibold text-white/60 truncate">${escapeHtml(artist)}</div>
                                <div class="flex items-center gap-1.5 mt-1.5">
                                    <button type="button" data-preview-url="${escapeHtml(previewUrl)}"
                                        class="btn-preview-track px-2.5 py-1 rounded-lg bg-white/10 hover:bg-white/20 text-white/90 text-[10px] font-bold flex items-center gap-1 transition cursor-pointer">
                                        ${ICONS.play}<span>Ouvir prévia</span>
                                    </button>
                                    <button type="button"
                                        data-track-title="${escapeHtml(title)}"
                                        data-track-artist="${escapeHtml(artist)}"
                                        data-preview-url="${escapeHtml(previewUrl)}"
                                        data-artwork-url="${escapeHtml(artLarge)}"
                                        class="btn-select-track px-2.5 py-1 rounded-lg bg-emerald-500 hover:bg-emerald-400 text-black text-[10px] font-extrabold transition cursor-pointer">
                                        Selecionar
                                    </button>
                                </div>
                            </div>
                        </div>
                    `;
                }).join('');

                resultsEl.querySelectorAll('.btn-preview-track').forEach(btn => {
                    btn.addEventListener('click', async () => {
                        const urlToPlay = btn.dataset.previewUrl;
                        if (state.previewingUrl === urlToPlay && !previewTesterAudio.paused) {
                            stopPreviewTester();
                            return;
                        }
                        stopPreviewTester();
                        if (!audioEl.paused) audioEl.pause();
                        stopWebAudioFallback();

                        state.previewingUrl = urlToPlay;
                        previewTesterAudio.src = urlToPlay;
                        btn.innerHTML = `${ICONS.pause}<span>Pausar</span>`;
                        btn.classList.remove('bg-white/10', 'text-white/90');
                        btn.classList.add('bg-[#FF2E93]', 'text-white');

                        try {
                            await previewTesterAudio.play();
                        } catch (err) {
                            showToast('Não foi possível reproduzir esta prévia.');
                            stopPreviewTester();
                        }
                    });
                });

                resultsEl.querySelectorAll('.btn-select-track').forEach(btn => {
                    btn.addEventListener('click', async () => {
                        stopPreviewTester();

                        const fullSongLabel = `${btn.dataset.trackTitle} - ${btn.dataset.trackArtist}`;
                        const previewUrl = btn.dataset.previewUrl;
                        const artworkUrl = btn.dataset.artworkUrl;

                        if (state.audioSourceType === 'local' && state.audioFileUrl) {
                            URL.revokeObjectURL(state.audioFileUrl);
                        }

                        state.data.song = fullSongLabel;
                        document.getElementById('input-song').value = fullSongLabel;

                        state.audioFileUrl = previewUrl;
                        state.audioFileName = fullSongLabel;
                        state.audioSourceType = 'itunes';
                        state.albumArtworkUrl = artworkUrl;

                        audioEl.src = previewUrl;
                        syncModalAudioPreview();
                        renderCurrentSlide();

                        state.soundEnabled = true;
                        updateSoundIcon();
                        await startRomanticSoundtrack();
                        showToast(`Selecionada: ${fullSongLabel}`);
                    });
                });

            } catch (error) {
                console.error('Erro na busca de músicas:', error);
                statusEl.textContent = 'Erro ao buscar músicas. Verifique sua conexão e tente novamente.';
            }
        }

        function updatePauseIcon() {
            dom.iconPauseWrap.innerHTML = state.isPaused ? ICONS.play : ICONS.pause;
        }

        function updateSoundIcon() {
            dom.iconSoundWrap.innerHTML = state.soundEnabled ? ICONS.volumeOn : ICONS.volumeOff;
        }

        function showToast(msg) {
            dom.toastMsg.textContent = msg;
            dom.toastBox.classList.remove('opacity-0', '-translate-y-3');
            dom.toastBox.classList.add('opacity-100', 'translate-y-0');
            setTimeout(() => {
                dom.toastBox.classList.remove('opacity-100', 'translate-y-0');
                dom.toastBox.classList.add('opacity-0', '-translate-y-3');
            }, 2600);
        }

        function syncLetterFieldsVisibility() {
            const enabled = document.getElementById('input-enable-letter').checked;
            const fields = document.getElementById('letter-editor-fields');
            if (enabled) {
                fields.classList.remove('opacity-40', 'pointer-events-none');
            } else {
                fields.classList.add('opacity-40', 'pointer-events-none');
            }
        }

        function openEditor() {
            state.isPaused = true;
            updatePauseIcon();
            document.getElementById('input-person1').value = state.data.person1;
            document.getElementById('input-person2').value = state.data.person2;
            document.getElementById('input-start-date').value = state.data.startDate;
            document.getElementById('input-moment').value = state.data.moment;
            document.getElementById('input-moment-desc').value = state.data.momentDesc;
            document.getElementById('input-top1').value = state.data.top5[0] || '';
            document.getElementById('input-top2').value = state.data.top5[1] || '';
            document.getElementById('input-top3').value = state.data.top5[2] || '';
            document.getElementById('input-top4').value = state.data.top5[3] || '';
            document.getElementById('input-top5').value = state.data.top5[4] || '';
            document.getElementById('input-song').value = state.data.song;
            document.getElementById('input-quote').value = state.data.quote;
            document.getElementById('input-enable-letter').checked = state.data.enableLetter;
            document.getElementById('input-letter-title').value = state.data.letterTitle;
            document.getElementById('input-letter-body').value = state.data.letterBody;

            syncLetterFieldsVisibility();
            renderPhotosManager();
            syncModalAudioPreview();
            renderThemeSelector();
            dom.editorModal.classList.remove('hidden');
        }

        function closeEditor() {
            stopPreviewTester();
            dom.editorModal.classList.add('hidden');
            state.isPaused = false;
            updatePauseIcon();
        }

        function bindEvents() {
            document.getElementById('tap-next').addEventListener('click', nextSlide);
            document.getElementById('tap-prev').addEventListener('click', prevSlide);

            const holdStart = () => { if (!dom.editorModal.classList.contains('hidden')) return; state.isPaused = true; };
            const holdEnd = () => { if (!dom.editorModal.classList.contains('hidden')) return; state.isPaused = false; };
            document.getElementById('tap-next').addEventListener('pointerdown', holdStart);
            document.getElementById('tap-next').addEventListener('pointerup', holdEnd);
            document.getElementById('tap-prev').addEventListener('pointerdown', holdStart);
            document.getElementById('tap-prev').addEventListener('pointerup', holdEnd);

            document.addEventListener('keydown', (e) => {
                if (!dom.editorModal.classList.contains('hidden')) return;
                if (e.key === 'ArrowRight') nextSlide();
                if (e.key === 'ArrowLeft') prevSlide();
                if (e.key === ' ') {
                    e.preventDefault();
                    state.isPaused = !state.isPaused;
                    updatePauseIcon();
                }
            });

            document.getElementById('btn-restart').addEventListener('click', () => {
                goToSlide(0);
                showToast('Retrospectiva reiniciada!');
            });

            document.getElementById('btn-pause').addEventListener('click', () => {
                state.isPaused = !state.isPaused;
                updatePauseIcon();
            });

            document.getElementById('btn-sound').addEventListener('click', async () => {
                if (!state.soundEnabled) {
                    state.soundEnabled = true;
                    updateSoundIcon();
                    await startRomanticSoundtrack();
                    showToast(state.audioFileName ? `Tocando: ${state.audioFileName}` : 'Trilha sonora romântica ativada!');
                } else {
                    state.soundEnabled = false;
                    updateSoundIcon();
                    stopRomanticSoundtrack();
                    showToast('Trilha sonora desativada');
                }
                if (state.currentSlide === 4) renderCurrentSlide();
            });

            audioEl.addEventListener('timeupdate', () => {
                if (state.currentSlide !== 4 || !audioEl.duration) return;
                const bar = document.getElementById('slide-audio-progress');
                const curr = document.getElementById('slide-audio-current');
                const dur = document.getElementById('slide-audio-duration');
                if (bar) bar.style.width = `${(audioEl.currentTime / audioEl.duration) * 100}%`;
                if (curr) curr.textContent = formatAudioTime(audioEl.currentTime);
                if (dur) dur.textContent = formatAudioTime(audioEl.duration);
            });

            // Upload de até 10 fotos em lote ou individual
            document.getElementById('input-photos-batch').addEventListener('change', (e) => {
                const files = Array.from(e.target.files || []);
                if (files.length === 0) return;

                const availableSlots = 10 - state.data.photos.length;
                if (availableSlots <= 0) {
                    showToast('Limite máximo de 10 fotos atingido!');
                    return;
                }

                const defaultTargets = ['5', '0', '2', '3', '4', '6', '0', '2', '3', '5'];
                const filesToProcess = files.slice(0, availableSlots);

                filesToProcess.forEach((file, idx) => {
                    const reader = new FileReader();
                    reader.onload = (ev) => {
                        if (state.data.photos.length >= 10) return;
                        const currentCount = state.data.photos.length;
                        state.data.photos.push({
                            id: `photo_${Date.now()}_${Math.random().toString(36).slice(2, 7)}`,
                            dataUrl: ev.target.result,
                            targetSlide: defaultTargets[currentCount % defaultTargets.length]
                        });
                        renderPhotosManager();
                    };
                    reader.readAsDataURL(file);
                });

                if (files.length > availableSlots) {
                    showToast(`Adicionadas ${availableSlots} fotos (limite de 10).`);
                } else {
                    showToast(`${filesToProcess.length} ${filesToProcess.length === 1 ? 'foto adicionada' : 'fotos adicionadas'}!`);
                }
                e.target.value = '';
            });

            // Upload de Arquivo de Áudio Real
            document.getElementById('input-audio').addEventListener('change', async (e) => {
                const file = e.target.files && e.target.files[0];
                if (!file) return;

                stopPreviewTester();
                if (state.audioSourceType === 'local' && state.audioFileUrl) {
                    URL.revokeObjectURL(state.audioFileUrl);
                }

                state.audioFileUrl = URL.createObjectURL(file);
                state.audioFileName = file.name;
                state.audioSourceType = 'local';
                state.albumArtworkUrl = null;
                audioEl.src = state.audioFileUrl;

                const cleanTitle = file.name.replace(/\.[^/.]+$/, '').replace(/[_-]+/g, ' ');
                const songInput = document.getElementById('input-song');
                if (songInput && (!songInput.value.trim() || songInput.value.includes("Don't Let Me Down"))) {
                    songInput.value = cleanTitle;
                }

                syncModalAudioPreview();
                renderCurrentSlide();
                showToast('Música carregada com sucesso!');

                state.soundEnabled = true;
                updateSoundIcon();
                await startRomanticSoundtrack();
            });

            document.getElementById('btn-music-search').addEventListener('click', () => {
                const query = document.getElementById('input-music-search').value;
                searchItunesMusic(query);
            });

            document.getElementById('input-music-search').addEventListener('keydown', (e) => {
                if (e.key === 'Enter') {
                    e.preventDefault();
                    searchItunesMusic(e.target.value);
                }
            });

            previewTesterAudio.addEventListener('ended', stopPreviewTester);

            document.getElementById('btn-remove-audio').addEventListener('click', () => {
                stopPreviewTester();
                if (state.audioSourceType === 'local' && state.audioFileUrl) {
                    URL.revokeObjectURL(state.audioFileUrl);
                }
                state.audioFileUrl = null;
                state.audioFileName = null;
                state.audioSourceType = 'synth';
                state.albumArtworkUrl = null;
                audioEl.pause();
                audioEl.removeAttribute('src');
                document.getElementById('input-audio').value = '';
                syncModalAudioPreview();
                renderCurrentSlide();
                if (state.soundEnabled) {
                    startRomanticSoundtrack();
                }
                showToast('Trilha sintetizada nativa restaurada.');
            });

            document.getElementById('input-enable-letter').addEventListener('change', syncLetterFieldsVisibility);

            // Modo Print Limpo
            document.getElementById('btn-clean').addEventListener('click', () => {
                document.body.classList.add('clean-mode');
                dom.btnExitClean.classList.remove('hidden');
                state.isPaused = true;
                updatePauseIcon();
            });

            dom.btnExitClean.addEventListener('click', () => {
                document.body.classList.remove('clean-mode');
                dom.btnExitClean.classList.add('hidden');
                state.isPaused = false;
                updatePauseIcon();
            });

            document.getElementById('btn-open-editor').addEventListener('click', openEditor);
            document.getElementById('btn-close-editor').addEventListener('click', closeEditor);

            // Botão "Exemplo Romântico"
            document.getElementById('btn-fill-example').addEventListener('click', () => {
                const ex = ROMANTIC_EXAMPLES[Math.floor(Math.random() * ROMANTIC_EXAMPLES.length)];
                document.getElementById('input-person1').value = ex.person1;
                document.getElementById('input-person2').value = ex.person2;
                document.getElementById('input-start-date').value = ex.startDate;
                document.getElementById('input-moment').value = ex.moment;
                document.getElementById('input-moment-desc').value = ex.momentDesc;
                document.getElementById('input-top1').value = ex.top5[0];
                document.getElementById('input-top2').value = ex.top5[1];
                document.getElementById('input-top3').value = ex.top5[2];
                document.getElementById('input-top4').value = ex.top5[3];
                document.getElementById('input-top5').value = ex.top5[4];
                document.getElementById('input-song').value = ex.song;
                document.getElementById('input-quote').value = ex.quote;
                document.getElementById('input-enable-letter').checked = true;
                document.getElementById('input-letter-title').value = ex.letterTitle;
                document.getElementById('input-letter-body').value = ex.letterBody;
                state.data.themeId = ex.themeId;
                syncLetterFieldsVisibility();
                renderThemeSelector();
                showToast('Exemplo romântico preenchido!');
            });

            // Salvar História Customizada
            document.getElementById('love-form').addEventListener('submit', (e) => {
                e.preventDefault();
                state.data.person1 = document.getElementById('input-person1').value.trim() || 'Amor 1';
                state.data.person2 = document.getElementById('input-person2').value.trim() || 'Amor 2';
                state.data.startDate = document.getElementById('input-start-date').value || '2023-06-12';
                state.data.moment = document.getElementById('input-moment').value.trim() || 'Nosso momento especial';
                state.data.momentDesc = document.getElementById('input-moment-desc').value.trim();
                state.data.top5 = [
                    document.getElementById('input-top1').value.trim() || 'Maratonar séries juntos',
                    document.getElementById('input-top2').value.trim() || 'Comer lanche de madrugada',
                    document.getElementById('input-top3').value.trim() || 'Rir juntos sem parar',
                    document.getElementById('input-top4').value.trim() || 'Cantar nossas músicas',
                    document.getElementById('input-top5').value.trim() || 'Sonhar com o futuro'
                ];
                state.data.song = document.getElementById('input-song').value.trim() || "Don't Let Me Down - The Beatles";
                state.data.quote = document.getElementById('input-quote').value.trim() || 'Te amo hoje e sempre.';
                state.data.enableLetter = document.getElementById('input-enable-letter').checked;
                state.data.letterTitle = document.getElementById('input-letter-title').value.trim() || 'Para você,';
                state.data.letterBody = document.getElementById('input-letter-body').value.trim() || 'Te amo infinito!';

                closeEditor();
                renderProgressBars();
                goToSlide(0);
                showToast('Nossa história foi atualizada!');
            });

            // Copiar Resumo & Declaração
            document.getElementById('btn-share-toast').addEventListener('click', () => {
                const { person1, person2, startDate, moment, song, quote } = state.data;
                const stats = calculateLoveStats(startDate);
                const shareText = `♥ Nossa Retrospectiva de Amor (${person1} & ${person2})\n📅 Juntos desde: ${stats.formattedDate}\n⏳ ${formatNumber(stats.totalDays)} dias (${formatNumber(stats.totalHours)} horas) de amor!\n✨ Momento #1: ${moment}\n🎵 Nossa Música: ${song}\n💌 “${quote}”`;

                const tempInput = document.createElement('textarea');
                tempInput.value = shareText;
                document.body.appendChild(tempInput);
                tempInput.select();
                try {
                    document.execCommand('copy');
                    showToast('Declaração copiada para compartilhar!');
                } catch (err) {
                    showToast('Use o botão de câmera no topo para tirar print!');
                }
                document.body.removeChild(tempInput);
            });
        }

        window.addEventListener('DOMContentLoaded', () => {
            renderProgressBars();
            renderCurrentSlide();
            bindEvents();
            requestAnimationFrame(progressLoop);
        });
    </script>
</body>
</html>
```
