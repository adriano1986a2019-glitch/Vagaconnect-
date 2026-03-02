<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vagaconnect | Entrevistas por Vídeo</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <script src="https://meet.jit.si/external_api.js"></script>
    <style>
        .gradient-text { background: linear-gradient(135deg, #6366f1 0%, #ec4899 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
    </style>
</head>
<body class="bg-gray-50">
    <nav class="p-6 bg-white shadow-sm flex justify-between items-center">
        <div class="flex items-center space-x-2">
            <div class="w-10 h-10 bg-indigo-600 rounded-lg flex items-center justify-center text-white font-bold text-xl shadow-lg">VC</div>
            <span class="text-2xl font-bold text-gray-900">Vaga<span class="gradient-text">connect</span></span>
        </div>
        <button class="bg-indigo-600 text-white px-6 py-2 rounded-full font-medium hover:bg-indigo-700 transition">Anunciar Vaga</button>
    </nav>

    <header class="py-20 text-center px-4">
        <h1 class="text-5xl lg:text-6xl font-extrabold text-gray-900 mb-6">Recrutamento Inteligente por <span class="gradient-text">Vídeo</span></h1>
        <p class="text-xl text-gray-600 max-w-2xl mx-auto">Conectando empresas e talentos com agilidade em Itapevi e região.</p>
    </header>

    <main class="max-w-4xl mx-auto p-4">
        <div class="bg-white p-8 rounded-3xl shadow-xl border border-gray-100 mb-10">
            <h2 class="text-2xl font-bold mb-6 text-gray-800">Vagas Ativas com Entrevista Online</h2>
            
            <div class="flex flex-col md:flex-row justify-between items-center p-6 bg-indigo-50 rounded-2xl border border-indigo-100">
                <div class="mb-4 md:mb-0">
                    <h3 class="text-xl font-bold text-indigo-900">Auxiliar Administrativo</h3>
                    <p class="text-gray-600 font-medium">Empresa Parceira - Itapevi, SP</p>
                    <span class="inline-block mt-2 text-xs bg-green-200 text-green-800 px-2 py-1 rounded-full font-bold">VAGA PREMIUM</span>
                </div>
                <button onclick="startVideo('Entrevista-Vagaconnect-Admin')" class="bg-indigo-600 text-white px-8 py-4 rounded-xl font-bold flex items-center gap-2 hover:bg-indigo-700 transition shadow-lg">
                    <i class="fas fa-video"></i> Iniciar Entrevista Agora
                </button>
            </div>

            <div id="jitsi-container" class="mt-8 rounded-2xl overflow-hidden border-4 border-indigo-200 hidden" style="height: 550px;"></div>
            
            <button id="btn-close" onclick="location.reload()" class="hidden w-full mt-4 py-3 bg-red-500 text-white rounded-xl font-bold shadow-md hover:bg-red-600 transition">
                Encerrar Chamada de Vídeo
            </button>
        </div>
    </main>

    <script>
        function startVideo(roomName) {
            const container = document.getElementById('jitsi-container');
            const closeBtn = document.getElementById('btn-close');
            
            container.classList.remove('hidden');
            closeBtn.classList.remove('hidden');
            
            const domain = 'meet.jit.si';
            const options = {
                roomName: roomName + '-' + Math.floor(Math.random() * 10000),
                width: '100%',
                height: '100%',
                parentNode: container,
                lang: 'pt-br'
            };
            const api = new JitsiMeetExternalAPI(domain, options);
            
            container.scrollIntoView({ behavior: 'smooth' });
        }
    </script>
</body>
</html>
