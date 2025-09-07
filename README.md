# Ai-chat-
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Chat Sederhana</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #6e8efb, #a777e3);
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .chat-container {
            width: 360px;
            height: 600px;
            background-color: #fff;
            border-radius: 16px;
            box-shadow: 0 12px 30px rgba(0, 0, 0, 0.2);
            display: flex;
            flex-direction: column;
            overflow: hidden;
        }
        
        .chat-header {
            background-color: #6e8efb;
            color: white;
            padding: 20px;
            text-align: center;
            font-weight: bold;
            font-size: 1.2rem;
        }
        
        .chat-messages {
            flex: 1;
            padding: 20px;
            overflow-y: auto;
            display: flex;
            flex-direction: column;
            gap: 15px;
            background-color: #f9f9f9;
        }
        
        .message {
            max-width: 80%;
            padding: 12px 16px;
            border-radius: 18px;
            line-height: 1.4;
            animation: fadeIn 0.3s ease;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .user-message {
            align-self: flex-end;
            background-color: #6e8efb;
            color: white;
            border-bottom-right-radius: 5px;
        }
        
        .bot-message {
            align-self: flex-start;
            background-color: #e8e8e8;
            color: #333;
            border-bottom-left-radius: 5px;
        }
        
        .chat-input {
            display: flex;
            padding: 15px;
            background-color: #fff;
            border-top: 1px solid #eee;
        }
        
        .chat-input input {
            flex: 1;
            padding: 12px 16px;
            border: 1px solid #ddd;
            border-radius: 24px;
            outline: none;
            font-size: 1rem;
        }
        
        .chat-input button {
            margin-left: 10px;
            padding: 12px 20px;
            background-color: #6e8efb;
            color: white;
            border: none;
            border-radius: 24px;
            cursor: pointer;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        
        .chat-input button:hover {
            background-color: #5a7de3;
        }
        
        .typing-indicator {
            align-self: flex-start;
            background-color: #e8e8e8;
            color: #333;
            padding: 12px 16px;
            border-radius: 18px;
            display: none;
        }
        
        .typing-indicator span {
            height: 8px;
            width: 8px;
            background-color: #999;
            border-radius: 50%;
            display: inline-block;
            margin: 0 2px;
            animation: typing 1.3s infinite;
        }
        
        .typing-indicator span:nth-child(2) {
            animation-delay: 0.2s;
        }
        
        .typing-indicator span:nth-child(3) {
            animation-delay: 0.4s;
        }
        
        @keyframes typing {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }
    </style>
</head>
<body>
    <div class="chat-container">
        <div class="chat-header">
            AI Chat Sederhana
        </div>
        <div class="chat-messages" id="chatMessages">
            <div class="message bot-message">
                Halo! Saya adalah AI chat sederhana. Ada yang bisa saya bantu?
            </div>
        </div>
        <div class="chat-input">
            <input type="text" id="userInput" placeholder="Ketik pesan Anda...">
            <button id="sendButton">Kirim</button>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const chatMessages = document.getElementById('chatMessages');
            const userInput = document.getElementById('userInput');
            const sendButton = document.getElementById('sendButton');
            
            // Fungsi untuk menambahkan pesan pengguna
            function addUserMessage(message) {
                const messageElement = document.createElement('div');
                messageElement.classList.add('message', 'user-message');
                messageElement.textContent = message;
                chatMessages.appendChild(messageElement);
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
            
            // Fungsi untuk menambahkan pesan bot
            function addBotMessage(message) {
                const messageElement = document.createElement('div');
                messageElement.classList.add('message', 'bot-message');
                messageElement.textContent = message;
                chatMessages.appendChild(messageElement);
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
            
            // Fungsi untuk menampilkan indikator typing
            function showTypingIndicator() {
                const typingIndicator = document.createElement('div');
                typingIndicator.classList.add('typing-indicator');
                typingIndicator.id = 'typingIndicator';
                typingIndicator.innerHTML = '<span></span><span></span><span></span>';
                chatMessages.appendChild(typingIndicator);
                chatMessages.scrollTop = chatMessages.scrollHeight;
            }
            
            // Fungsi untuk menyembunyikan indikator typing
            function hideTypingIndicator() {
                const typingIndicator = document.getElementById('typingIndicator');
                if (typingIndicator) {
                    typingIndicator.remove();
                }
            }
            
            // Fungsi untuk memproses input pengguna dan menghasilkan respons
            function processUserInput(input) {
                input = input.toLowerCase().trim();
                
                // Aturan-aturan respons
                if (input.includes('halo') || input.includes('hai') || input.includes('hi')) {
                    return "Halo! Ada yang bisa saya bantu?";
                } else if (input.includes('nama') && input.includes('kamu')) {
                    return "Saya adalah AI Chat sederhana yang dibuat untuk membantu Anda.";
                } else if (input.includes('apa kabar') || input.includes('how are you')) {
                    return "Saya baik-baik saja, terima kasih! Bagaimana dengan Anda?";
                } else if (input.includes('terima kasih') || input.includes('thanks')) {
                    return "Sama-sama! Senang bisa membantu.";
                } else if (input.includes('help') || input.includes('bantuan')) {
                    return "Saya bisa menjawab pertanyaan sederhana. Coba tanyakan tentang salam, nama, atau waktu.";
                } else if (input.includes('jam') || input.includes('waktu')) {
                    return "Sekarang jam " + new Date().toLocaleTimeString('id-ID');
                } else if (input.includes('tanggal') || input.includes('hari')) {
                    return "Hari ini adalah " + new Date().toLocaleDateString('id-ID', { 
                        weekday: 'long', 
                        year: 'numeric', 
                        month: 'long', 
                        day: 'numeric' 
                    });
                } else if (input.includes('bye') || input.includes('selamat tinggal') || input.includes('dadah')) {
                    return "Selamat tinggal! Senang berbicara dengan Anda.";
                } else {
                    return "Maaf, saya tidak mengerti pertanyaan Anda. Coba tanyakan sesuatu yang lain.";
                }
            }
            
            // Fungsi untuk mengirim pesan
            function sendMessage() {
                const message = userInput.value.trim();
                if (message === '') return;
                
                // Tambahkan pesan pengguna
                addUserMessage(message);
                userInput.value = '';
                
                // Tampilkan indikator typing
                showTypingIndicator();
                
                // Proses pesan dan berikan respons setelah delay
                setTimeout(() => {
                    hideTypingIndicator();
                    const response = processUserInput(message);
                    addBotMessage(response);
                }, 1000);
            }
            
            // Event listener untuk tombol kirim
            sendButton.addEventListener('click', sendMessage);
            
            // Event listener untuk menekan enter pada input
            userInput.addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    sendMessage();
                }
            });
        });
    </script>
</body>
</html>
