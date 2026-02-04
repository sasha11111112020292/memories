<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Safe Space — Your Personal Sanctuary</title>
    <link href="https://fonts.googleapis.com/css2?family=Spectral:ital,wght@0,300;0,400;1,300&family=Work+Sans:wght@300;400;500&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Work Sans', sans-serif;
            background: linear-gradient(135deg, #fdf6e3 0%, #f5e6d3 50%, #ffd7ba 100%);
            color: #3d3d3d;
            min-height: 100vh;
            padding: 40px 20px;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            margin-bottom: 60px;
        }

        h1 {
            font-family: 'Spectral', serif;
            font-size: 48px;
            font-weight: 300;
            color: #8b6f47;
            margin-bottom: 12px;
            letter-spacing: 1px;
        }

        .tagline {
            font-size: 15px;
            color: #a08968;
            font-weight: 300;
            font-style: italic;
        }

        .welcome-message {
            background: rgba(255, 255, 255, 0.6);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(139, 111, 71, 0.15);
            border-radius: 20px;
            padding: 30px;
            margin-bottom: 50px;
            text-align: center;
            box-shadow: 0 8px 32px rgba(139, 111, 71, 0.08);
        }

        .welcome-text {
            font-family: 'Spectral', serif;
            font-size: 18px;
            line-height: 1.8;
            color: #6b5d4f;
            font-style: italic;
        }

        .rooms-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .room {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(10px);
            border: 2px solid rgba(139, 111, 71, 0.15);
            border-radius: 24px;
            padding: 28px;
            transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .room::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 6px;
            background: var(--room-color);
            opacity: 0.6;
            transition: all 0.3s ease;
        }

        .room:hover {
            transform: translateY(-8px);
            box-shadow: 0 16px 48px rgba(139, 111, 71, 0.15);
            border-color: rgba(139, 111, 71, 0.25);
        }

        .room:hover::before {
            height: 100%;
            opacity: 0.08;
        }

        .room-header {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 16px;
        }

        .room-icon {
            font-size: 28px;
            filter: drop-shadow(0 2px 8px rgba(0, 0, 0, 0.1));
        }

        .room-title {
            font-family: 'Spectral', serif;
            font-size: 22px;
            font-weight: 400;
            color: #5d4e3a;
            flex: 1;
        }

        .room-count {
            background: rgba(139, 111, 71, 0.1);
            padding: 4px 12px;
            border-radius: 12px;
            font-size: 13px;
            color: #8b6f47;
            font-weight: 500;
        }

        .room-description {
            font-size: 14px;
            color: #7d6f5d;
            line-height: 1.6;
            margin-bottom: 20px;
            font-style: italic;
        }

        .entries-preview {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-bottom: 16px;
        }

        .entry-snippet {
            background: rgba(255, 255, 255, 0.5);
            padding: 12px 14px;
            border-radius: 10px;
            font-size: 13px;
            color: #5d5d5d;
            border-left: 3px solid var(--room-color);
            line-height: 1.5;
            transition: all 0.2s ease;
        }

        .entry-snippet:hover {
            background: rgba(255, 255, 255, 0.8);
            transform: translateX(4px);
        }

        .add-entry-btn {
            width: 100%;
            padding: 12px;
            background: transparent;
            border: 2px dashed rgba(139, 111, 71, 0.25);
            border-radius: 12px;
            color: #a08968;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Work Sans', sans-serif;
            font-weight: 400;
        }

        .add-entry-btn:hover {
            background: rgba(139, 111, 71, 0.08);
            border-color: rgba(139, 111, 71, 0.4);
            color: #8b6f47;
        }

        .modal {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(61, 46, 35, 0.7);
            backdrop-filter: blur(12px);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 20px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .modal.active {
            display: flex;
            opacity: 1;
        }

        .modal-content {
            background: linear-gradient(135deg, #fff9f0 0%, #ffecd1 100%);
            border: 3px solid rgba(139, 111, 71, 0.2);
            border-radius: 28px;
            padding: 40px;
            max-width: 600px;
            width: 100%;
            box-shadow: 0 24px 64px rgba(61, 46, 35, 0.3);
            max-height: 90vh;
            overflow-y: auto;
        }

        .modal-header {
            display: flex;
            align-items: center;
            gap: 12px;
            margin-bottom: 30px;
        }

        .modal-icon {
            font-size: 36px;
        }

        .modal-title {
            font-family: 'Spectral', serif;
            font-size: 28px;
            font-weight: 400;
            color: #5d4e3a;
            flex: 1;
        }

        .form-group {
            margin-bottom: 24px;
        }

        .form-label {
            display: block;
            font-size: 13px;
            color: #8b6f47;
            margin-bottom: 10px;
            font-weight: 500;
            letter-spacing: 0.5px;
        }

        .form-textarea {
            width: 100%;
            background: rgba(255, 255, 255, 0.8);
            border: 2px solid rgba(139, 111, 71, 0.2);
            border-radius: 16px;
            padding: 18px;
            color: #3d3d3d;
            font-size: 15px;
            font-family: 'Spectral', serif;
            line-height: 1.8;
            min-height: 200px;
            resize: vertical;
            transition: all 0.3s ease;
            outline: none;
        }

        .form-textarea:focus {
            border-color: rgba(139, 111, 71, 0.4);
            background: rgba(255, 255, 255, 0.95);
            box-shadow: 0 4px 16px rgba(139, 111, 71, 0.1);
        }

        .form-textarea::placeholder {
            color: #b8a890;
            font-style: italic;
        }

        .form-actions {
            display: flex;
            gap: 12px;
            margin-top: 30px;
        }

        .btn {
            flex: 1;
            padding: 16px 24px;
            border: none;
            border-radius: 14px;
            font-size: 15px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Work Sans', sans-serif;
        }

        .btn-primary {
            background: linear-gradient(135deg, #d4a574 0%, #c99a6e 100%);
            color: #fff;
            box-shadow: 0 4px 16px rgba(212, 165, 116, 0.3);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(212, 165, 116, 0.4);
        }

        .btn-secondary {
            background: rgba(139, 111, 71, 0.1);
            color: #8b6f47;
            border: 2px solid rgba(139, 111, 71, 0.2);
        }

        .btn-secondary:hover {
            background: rgba(139, 111, 71, 0.15);
            border-color: rgba(139, 111, 71, 0.3);
        }

        .bottom-actions {
            display: flex;
            gap: 16px;
            justify-content: center;
            padding: 30px 20px;
        }

        .action-btn {
            padding: 12px 24px;
            background: rgba(255, 255, 255, 0.7);
            border: 2px solid rgba(139, 111, 71, 0.15);
            border-radius: 16px;
            color: #8b6f47;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Work Sans', sans-serif;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .action-btn:hover {
            background: rgba(255, 255, 255, 0.9);
            border-color: rgba(139, 111, 71, 0.3);
            transform: translateY(-2px);
            box-shadow: 0 8px 24px rgba(139, 111, 71, 0.15);
        }

        .stats {
            text-align: center;
            margin-top: 40px;
            padding: 30px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 20px;
            border: 2px solid rgba(139, 111, 71, 0.1);
        }

        .stats-content {
            font-family: 'Spectral', serif;
            font-size: 16px;
            color: #6b5d4f;
            line-height: 1.8;
        }

        .stats-number {
            font-size: 32px;
            font-weight: 400;
            color: #8b6f47;
            margin: 0 6px;
        }

        .empty-state {
            text-align: center;
            padding: 30px;
            color: #b8a890;
            font-style: italic;
            font-size: 14px;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(10px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .room {
            animation: fadeIn 0.6s ease backwards;
        }

        .room:nth-child(1) { animation-delay: 0.1s; }
        .room:nth-child(2) { animation-delay: 0.2s; }
        .room:nth-child(3) { animation-delay: 0.3s; }
        .room:nth-child(4) { animation-delay: 0.4s; }
        .room:nth-child(5) { animation-delay: 0.5s; }
        .room:nth-child(6) { animation-delay: 0.6s; }
        .room:nth-child(7) { animation-delay: 0.7s; }
        .room:nth-child(8) { animation-delay: 0.8s; }

        ::selection {
            background: rgba(212, 165, 116, 0.3);
            color: #3d3d3d;
        }

        ::-webkit-scrollbar {
            width: 10px;
        }

        ::-webkit-scrollbar-track {
            background: rgba(139, 111, 71, 0.05);
        }

        ::-webkit-scrollbar-thumb {
            background: rgba(139, 111, 71, 0.2);
            border-radius: 5px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: rgba(139, 111, 71, 0.3);
        }

        @media (max-width: 768px) {
            .rooms-grid {
                grid-template-columns: 1fr;
            }

            h1 {
                font-size: 36px;
            }

            .modal-content {
                padding: 30px 24px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Safe Space</h1>
            <p class="tagline">A gentle place for all the pieces of you</p>
        </header>

        <div class="welcome-message">
            <p class="welcome-text">
                This is your sanctuary. Every thought, feeling, and moment matters here. 
                There's no judgment, no rush—just space to be exactly who you are.
            </p>
        </div>

        <div class="rooms-grid" id="roomsGrid"></div>

        <div class="stats" id="stats">
            <div class="stats-content">
                You've preserved <span class="stats-number" id="totalEntries">0</span> moments in your sanctuary.
                <br>
                You've visited <span class="stats-number" id="activeRooms">0</span> different rooms.
            </div>
        </div>

        <div class="bottom-actions">
            <button class="action-btn" onclick="exportData()">
                <span>💾</span>
                <span>Save Backup</span>
            </button>
            <button class="action-btn" onclick="document.getElementById('importFile').click()">
                <span>📂</span>
                <span>Load Backup</span>
            </button>
            <input type="file" id="importFile" accept=".json" style="display: none;" onchange="importData(event)">
        </div>
    </div>

    <div class="modal" id="modal">
        <div class="modal-content">
            <div class="modal-header">
                <span class="modal-icon" id="modalIcon">💭</span>
                <h2 class="modal-title" id="modalTitle">New Entry</h2>
            </div>

            <div class="form-group">
                <label class="form-label" id="promptLabel">What's on your heart?</label>
                <textarea 
                    class="form-textarea" 
                    id="entryText" 
                    placeholder="Let it out... this space holds you."
                ></textarea>
            </div>

            <div class="form-actions">
                <button class="btn btn-secondary" onclick="closeModal()">Maybe Later</button>
                <button class="btn btn-primary" onclick="saveEntry()">Keep This Safe</button>
            </div>
        </div>
    </div>

    <script>
        const ROOMS = [
            {
                id: 'compliments',
                icon: '🌟',
                title: 'Kind Words',
                description: 'Compliments and affirming words that made you feel seen',
                color: '#f4c430',
                prompt: 'What kind words touched your heart today?'
            },
            {
                id: 'brave',
                icon: '🦋',
                title: 'Brave Moments',
                description: 'Times you did something scary, even when you were afraid',
                color: '#9b59b6',
                prompt: 'What brave thing did you do, even though it was hard?'
            },
            {
                id: 'special',
                icon: '✨',
                title: 'Special Moments',
                description: 'Memories that sparkle, moments you want to remember forever',
                color: '#ff9a9e',
                prompt: 'What made this moment special to you?'
            },
            {
                id: 'voices',
                icon: '💬',
                title: 'Two Voices',
                description: 'The conversation between your inner critic and inner friend',
                color: '#6a89cc',
                prompt: 'What is your critic saying? Now, what would your loving friend say back?'
            },
            {
                id: 'letters',
                icon: '💌',
                title: 'Unsent Letters',
                description: 'Words you need to say but haven\'t sent—to anyone, even yourself',
                color: '#f8b500',
                prompt: 'Who is this letter to, and what do you need to say?'
            },
            {
                id: 'grateful',
                icon: '🌸',
                title: 'Gratitude',
                description: 'Small and large things that filled you with appreciation',
                color: '#ff6b9d',
                prompt: 'What are you grateful for right now?'
            },
            {
                id: 'laughter',
                icon: '😊',
                title: 'Joy Captured',
                description: 'Things that made you laugh, smile, or feel light',
                color: '#ffa502',
                prompt: 'What brought joy to your day?'
            },
            {
                id: 'hard',
                icon: '🌧️',
                title: 'Hard Days',
                description: 'A space to hold the difficult feelings without fixing them',
                color: '#778ca3',
                prompt: 'What feels heavy right now? You don\'t have to fix it, just name it.'
            }
        ];

        let entries = {};
        let currentRoom = null;

        // Initialize
        document.addEventListener('DOMContentLoaded', () => {
            loadData();
            renderRooms();
            updateStats();
        });

        function renderRooms() {
            const grid = document.getElementById('roomsGrid');
            grid.innerHTML = '';

            ROOMS.forEach(room => {
                const roomEntries = entries[room.id] || [];
                const roomEl = document.createElement('div');
                roomEl.className = 'room';
                roomEl.style.setProperty('--room-color', room.color);

                const previewEntries = roomEntries.slice(-3).reverse();
                const entriesHTML = previewEntries.length > 0
                    ? previewEntries.map(entry => {
                        const preview = entry.text.length > 80 
                            ? entry.text.substring(0, 80) + '...'
                            : entry.text;
                        return `<div class="entry-snippet">${preview}</div>`;
                    }).join('')
                    : '<div class="empty-state">No entries yet—this room is waiting for you</div>';

                roomEl.innerHTML = `
                    <div class="room-header">
                        <span class="room-icon">${room.icon}</span>
                        <h3 class="room-title">${room.title}</h3>
                        <span class="room-count">${roomEntries.length}</span>
                    </div>
                    <p class="room-description">${room.description}</p>
                    <div class="entries-preview">
                        ${entriesHTML}
                    </div>
                    <button class="add-entry-btn" onclick="openModal('${room.id}')">
                        + Add to this space
                    </button>
                `;

                grid.appendChild(roomEl);
            });
        }

        function openModal(roomId) {
            currentRoom = ROOMS.find(r => r.id === roomId);
            if (!currentRoom) return;

            document.getElementById('modalIcon').textContent = currentRoom.icon;
            document.getElementById('modalTitle').textContent = currentRoom.title;
            document.getElementById('promptLabel').textContent = currentRoom.prompt;
            document.getElementById('entryText').value = '';
            document.getElementById('entryText').placeholder = 'Let it out... this space holds you.';

            const modal = document.getElementById('modal');
            modal.classList.add('active');
            setTimeout(() => {
                document.getElementById('entryText').focus();
            }, 100);
        }

        function closeModal() {
            document.getElementById('modal').classList.remove('active');
            currentRoom = null;
        }

        function saveEntry() {
            const text = document.getElementById('entryText').value.trim();
            if (!text || !currentRoom) return;

            if (!entries[currentRoom.id]) {
                entries[currentRoom.id] = [];
            }

            entries[currentRoom.id].push({
                text: text,
                date: new Date().toISOString(),
                id: Date.now()
            });

            saveData();
            renderRooms();
            updateStats();
            closeModal();
        }

        function updateStats() {
            const totalEntries = Object.values(entries).reduce((sum, arr) => sum + arr.length, 0);
            const activeRooms = Object.keys(entries).filter(key => entries[key].length > 0).length;

            document.getElementById('totalEntries').textContent = totalEntries;
            document.getElementById('activeRooms').textContent = activeRooms;
        }

        function saveData() {
            localStorage.setItem('safeSpaceEntries', JSON.stringify(entries));
        }

        function loadData() {
            const saved = localStorage.getItem('safeSpaceEntries');
            if (saved) {
                entries = JSON.parse(saved);
            }
        }

        function exportData() {
            const data = {
                entries,
                exported: new Date().toISOString(),
                version: '1.0'
            };

            const blob = new Blob([JSON.stringify(data, null, 2)], { type: 'application/json' });
            const url = URL.createObjectURL(blob);
            const a = document.createElement('a');
            a.href = url;
            a.download = `safe-space-backup-${new Date().toISOString().split('T')[0]}.json`;
            a.click();
            URL.revokeObjectURL(url);
        }

        function importData(e) {
            const file = e.target.files[0];
            if (!file) return;

            const reader = new FileReader();
            reader.onload = (event) => {
                try {
                    const data = JSON.parse(event.target.result);
                    if (data.entries) {
                        entries = data.entries;
                        saveData();
                        renderRooms();
                        updateStats();
                    }
                } catch (error) {
                    alert('Could not load backup. Please check the file.');
                }
            };
            reader.readAsText(file);
        }

        // Click outside modal to close
        document.getElementById('modal').addEventListener('click', (e) => {
            if (e.target.id === 'modal') {
                closeModal();
            }
        });

        // Keyboard shortcuts
        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') closeModal();
        });
    </script>
</body>
</html>
