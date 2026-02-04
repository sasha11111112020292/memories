<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Safe Space — Your Personal Sanctuary</title>
    <link href="https://fonts.googleapis.com/css2?family=Crimson+Pro:wght@300;400;500&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-primary: #fafaf9;
            --bg-secondary: #f5f5f4;
            --text-primary: #1c1917;
            --text-secondary: #57534e;
            --text-tertiary: #a8a29e;
            --border-light: #e7e5e4;
            --border-medium: #d6d3d1;
            --accent-primary: #78716c;
            --accent-secondary: #a8a29e;
            --shadow-sm: 0 1px 2px 0 rgb(0 0 0 / 0.05);
            --shadow-md: 0 4px 6px -1px rgb(0 0 0 / 0.1);
            --shadow-lg: 0 10px 15px -3px rgb(0 0 0 / 0.1);
            --shadow-xl: 0 20px 25px -5px rgb(0 0 0 / 0.1);
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
            background: linear-gradient(-45deg, #fafaf9, #f5f5f4, #fef5f0, #f9f5f9, #f5f5f4, #fafaf9);
            background-size: 400% 400%;
            animation: gradientShift 20s ease infinite;
            color: var(--text-primary);
            min-height: 100vh;
            padding: 60px 24px;
            line-height: 1.6;
            position: relative;
            transition: background 0.5s ease;
        }

        body.room-active {
            background: linear-gradient(-45deg, 
                var(--active-room-color-light), 
                var(--active-room-color-lighter), 
                #fafaf9, 
                var(--active-room-color-lighter)
            );
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: 
                radial-gradient(circle at 20% 50%, rgba(212, 165, 116, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 80% 80%, rgba(155, 135, 181, 0.03) 0%, transparent 50%),
                radial-gradient(circle at 40% 90%, rgba(230, 159, 172, 0.03) 0%, transparent 50%);
            pointer-events: none;
            z-index: 0;
        }

        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .container {
            position: relative;
            z-index: 1;
            max-width: 1400px;
            margin: 0 auto;
        }

        header {
            text-align: center;
            margin-bottom: 80px;
            position: relative;
        }

        h1 {
            font-family: 'Crimson Pro', serif;
            font-size: 56px;
            font-weight: 300;
            color: var(--text-primary);
            margin-bottom: 16px;
            letter-spacing: -0.5px;
            position: relative;
            display: inline-block;
            overflow: hidden;
            border-right: 2px solid var(--text-primary);
            white-space: nowrap;
            animation: typing 2s steps(10, end) forwards, blink 0.75s step-end infinite;
        }

        @keyframes typing {
            from { width: 0; }
            to { width: 100%; border-right: none; }
        }

        @keyframes blink {
            from, to { border-color: transparent; }
            50% { border-color: var(--text-primary); }
        }

        h1::before {
            content: '';
            position: absolute;
            top: -25px;
            right: -45px;
            width: 35px;
            height: 30px;
            background: radial-gradient(ellipse at 30% 40%, #e69fac 0%, #d88b95 40%, transparent 70%),
                        radial-gradient(ellipse at 70% 40%, #e69fac 0%, #d88b95 40%, transparent 70%);
            opacity: 0;
            transform: rotate(15deg) scale(0);
            filter: blur(0.5px);
            animation: fadeInKiss 1s ease 2s forwards;
        }

        h1::after {
            content: '';
            position: absolute;
            top: -20px;
            right: -40px;
            width: 28px;
            height: 22px;
            background: radial-gradient(ellipse at 35% 45%, rgba(230, 159, 172, 0.6) 0%, rgba(216, 139, 149, 0.4) 40%, transparent 65%),
                        radial-gradient(ellipse at 65% 45%, rgba(230, 159, 172, 0.6) 0%, rgba(216, 139, 149, 0.4) 40%, transparent 65%);
            opacity: 0;
            transform: rotate(15deg) scale(0);
            filter: blur(0.8px);
            animation: fadeInKiss 1s ease 2.1s forwards;
        }

        @keyframes fadeInKiss {
            0% { opacity: 0; transform: rotate(15deg) scale(0); }
            50% { opacity: 0.5; transform: rotate(15deg) scale(1.1); }
            100% { opacity: 0.35; transform: rotate(15deg) scale(1); }
        }

        .signature {
            position: fixed;
            bottom: 20px;
            right: 30px;
            font-family: 'Crimson Pro', serif;
            font-size: 24px;
            color: rgba(212, 165, 116, 0.4);
            z-index: 100;
            pointer-events: none;
            font-style: italic;
            letter-spacing: 1px;
            animation: fadeIn 1s ease 3s both;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .tagline {
            font-size: 16px;
            color: var(--text-secondary);
            font-weight: 400;
            letter-spacing: 0.3px;
        }

        .daily-quote {
            margin-top: 32px;
            padding: 24px 40px;
            background: linear-gradient(135deg, rgba(212, 165, 116, 0.08) 0%, rgba(155, 135, 181, 0.08) 100%);
            border: 1px solid rgba(212, 165, 116, 0.2);
            border-radius: 12px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
            position: relative;
            overflow: hidden;
            animation: fadeIn 0.8s ease 2.5s both;
        }

        .daily-quote::before {
            content: '✨';
            position: absolute;
            top: 12px;
            left: 12px;
            font-size: 20px;
            opacity: 0.6;
            animation: gentleFloat 4s ease-in-out infinite;
        }

        .daily-quote::after {
            content: '✨';
            position: absolute;
            bottom: 12px;
            right: 12px;
            font-size: 20px;
            opacity: 0.6;
            animation: gentleFloat 4s ease-in-out infinite 2s;
        }

        @keyframes gentleFloat {
            0%, 100% {
                transform: translateY(0px);
                opacity: 0.6;
            }
            50% {
                transform: translateY(-3px);
                opacity: 0.8;
            }
        }

        .quote-text {
            font-family: 'Crimson Pro', serif;
            font-size: 17px;
            font-style: italic;
            color: var(--text-primary);
            line-height: 1.6;
            text-align: center;
            margin-bottom: 8px;
        }

        .quote-author {
            font-size: 13px;
            color: var(--text-secondary);
            text-align: center;
            font-weight: 500;
            letter-spacing: 0.5px;
        }

        .welcome-message {
            background: linear-gradient(135deg, #ffffff 0%, #fafaf9 100%);
            border: 1px solid var(--border-light);
            border-radius: 16px;
            padding: 48px;
            margin-bottom: 60px;
            margin-top: 60px;
            text-align: center;
            box-shadow: var(--shadow-sm);
            position: relative;
            overflow: hidden;
        }

        .welcome-message::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -5%;
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, rgba(212, 165, 116, 0.08) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
            animation: colorPulse 8s ease-in-out infinite;
        }

        .welcome-message::after {
            content: '';
            position: absolute;
            bottom: -50%;
            left: -5%;
            width: 250px;
            height: 250px;
            background: radial-gradient(circle, rgba(155, 135, 181, 0.06) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
            animation: colorPulse 8s ease-in-out infinite 2s;
        }

        @keyframes colorPulse {
            0%, 100% {
                opacity: 1;
                transform: scale(1);
            }
            50% {
                opacity: 0.6;
                transform: scale(1.1);
            }
        }

        .welcome-text {
            font-family: 'Crimson Pro', serif;
            font-size: 20px;
            line-height: 1.7;
            color: var(--text-secondary);
            max-width: 700px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .welcome-text::first-letter {
            font-size: 32px;
            font-weight: 400;
            color: var(--text-primary);
            float: left;
            line-height: 1;
            margin-right: 8px;
            margin-top: 4px;
        }

        .sparkle {
            position: fixed;
            pointer-events: none;
            width: 4px;
            height: 4px;
            background: radial-gradient(circle, rgba(212, 165, 116, 0.8) 0%, transparent 70%);
            border-radius: 50%;
            animation: sparkleFloat 2s ease-out forwards;
            z-index: 9999;
        }

        .sparkle::before {
            content: '';
            position: absolute;
            top: -1px;
            left: -1px;
            width: 2px;
            height: 6px;
            background: linear-gradient(to bottom, rgba(255, 255, 255, 0.9), transparent);
            transform: rotate(0deg);
        }

        .sparkle::after {
            content: '';
            position: absolute;
            top: -1px;
            left: -1px;
            width: 6px;
            height: 2px;
            background: linear-gradient(to right, rgba(255, 255, 255, 0.9), transparent);
        }

        @keyframes sparkleFloat {
            0% {
                opacity: 1;
                transform: translateY(0) scale(1) rotate(0deg);
            }
            100% {
                opacity: 0;
                transform: translateY(-40px) scale(0.3) rotate(180deg);
            }
        }

        .floating-kiss {
            position: fixed;
            bottom: -50px;
            animation: floatUp 20s linear infinite;
            pointer-events: none;
            opacity: 0.15;
            z-index: 1;
            width: 30px;
            height: 30px;
        }

        .floating-kiss::before {
            content: '';
            position: absolute;
            width: 15px;
            height: 20px;
            background: radial-gradient(ellipse at 30% 40%, #e69fac 0%, #d88b95 40%, transparent 70%),
                        radial-gradient(ellipse at 70% 40%, #e69fac 0%, #d88b95 40%, transparent 70%);
            transform: rotate(15deg);
            filter: blur(0.5px);
        }

        .floating-kiss::after {
            content: '';
            position: absolute;
            width: 12px;
            height: 16px;
            left: 2px;
            background: radial-gradient(ellipse at 35% 45%, rgba(230, 159, 172, 0.6) 0%, rgba(216, 139, 149, 0.4) 40%, transparent 65%),
                        radial-gradient(ellipse at 65% 45%, rgba(230, 159, 172, 0.6) 0%, rgba(216, 139, 149, 0.4) 40%, transparent 65%);
            transform: rotate(15deg);
            filter: blur(0.8px);
        }

        @keyframes floatUp {
            0% {
                bottom: -50px;
                transform: translateX(0) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.15;
            }
            90% {
                opacity: 0.15;
            }
            100% {
                bottom: 110vh;
                transform: translateX(30px) rotate(360deg);
                opacity: 0;
            }
        }

        .rooms-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(360px, 1fr));
            gap: 24px;
            margin-bottom: 60px;
        }

        .room {
            background: white;
            border: 1px solid var(--border-light);
            border-radius: 12px;
            padding: 32px;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
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
            height: 3px;
            background: linear-gradient(90deg, var(--room-color), transparent);
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .room::after {
            content: '';
            position: absolute;
            top: 0;
            right: 0;
            width: 100px;
            height: 100px;
            background: radial-gradient(circle at top right, var(--room-color) 0%, transparent 70%);
            opacity: 0.03;
            pointer-events: none;
        }

        .room:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 24px -8px rgba(0, 0, 0, 0.12), 0 0 0 1px var(--border-medium);
            border-color: var(--border-medium);
        }

        .room:hover::before {
            opacity: 1;
        }

        .room:hover::after {
            opacity: 0.08;
        }

        .room:active {
            transform: translateY(-2px) scale(0.98);
        }

        .room-header {
            display: flex;
            align-items: flex-start;
            gap: 16px;
            margin-bottom: 20px;
        }

        .room-icon {
            width: 48px;
            height: 48px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, var(--bg-secondary) 0%, white 100%);
            border-radius: 10px;
            flex-shrink: 0;
            border: 1px solid var(--border-light);
            box-shadow: var(--shadow-sm);
        }

        .room-icon svg {
            width: 24px;
            height: 24px;
            stroke: var(--text-primary);
            fill: none;
            stroke-width: 1.5;
        }

        .room-header-content {
            flex: 1;
        }

        .room-title {
            font-size: 20px;
            font-weight: 500;
            color: var(--text-primary);
            margin-bottom: 4px;
            letter-spacing: -0.3px;
        }

        .room-count {
            display: inline-block;
            background: var(--bg-secondary);
            padding: 4px 10px;
            border-radius: 6px;
            font-size: 12px;
            color: var(--text-secondary);
            font-weight: 500;
            margin-top: 8px;
        }

        .room-description {
            font-size: 14px;
            color: var(--text-tertiary);
            line-height: 1.6;
            margin-bottom: 24px;
        }

        .entries-preview {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-bottom: 20px;
            min-height: 120px;
        }

        .entry-snippet {
            background: var(--bg-secondary);
            padding: 14px 16px;
            border-radius: 8px;
            font-size: 13px;
            color: var(--text-secondary);
            line-height: 1.6;
            border-left: 3px solid var(--room-color);
            transition: all 0.2s ease;
            position: relative;
            cursor: pointer;
        }

        .entry-snippet::before {
            content: '"';
            position: absolute;
            top: 8px;
            left: 10px;
            font-size: 24px;
            color: var(--room-color);
            opacity: 0.15;
            font-family: 'Crimson Pro', serif;
            line-height: 1;
        }

        .entry-snippet:hover {
            background: var(--bg-primary);
            transform: translateX(2px);
            box-shadow: var(--shadow-sm);
        }

        .entry-media-indicator {
            display: inline-flex;
            align-items: center;
            gap: 4px;
            margin-left: 8px;
            font-size: 11px;
            color: var(--text-tertiary);
        }

        .entry-media-indicator svg {
            width: 14px;
            height: 14px;
            stroke: var(--text-tertiary);
        }

        .add-entry-btn {
            width: 100%;
            padding: 14px;
            background: transparent;
            border: 1.5px dashed var(--border-medium);
            border-radius: 8px;
            color: var(--text-tertiary);
            font-size: 14px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Inter', sans-serif;
            font-weight: 500;
        }

        .add-entry-btn:hover {
            background: var(--bg-secondary);
            border-color: var(--accent-primary);
            color: var(--text-secondary);
        }

        .modal {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(28, 25, 23, 0.4);
            backdrop-filter: blur(8px);
            display: none;
            align-items: center;
            justify-content: center;
            z-index: 1000;
            padding: 24px;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .modal.active {
            display: flex;
            opacity: 1;
        }

        .modal-content {
            background: white;
            border: 1px solid var(--border-light);
            border-radius: 16px;
            padding: 48px;
            max-width: 700px;
            width: 100%;
            box-shadow: 0 24px 48px rgba(0, 0, 0, 0.12), 0 0 0 1px rgba(0, 0, 0, 0.05);
            max-height: 90vh;
            overflow-y: auto;
            position: relative;
            animation: slideUp 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .modal-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, #d4a574, #9b87b5, #e69fac, #7b9eb0);
            border-radius: 16px 16px 0 0;
        }

        .modal-header {
            display: flex;
            align-items: center;
            gap: 16px;
            margin-bottom: 32px;
            padding-bottom: 24px;
            border-bottom: 1px solid var(--border-light);
        }

        .modal-icon {
            width: 48px;
            height: 48px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, var(--bg-secondary) 0%, white 100%);
            border-radius: 10px;
            border: 1px solid var(--border-light);
            box-shadow: var(--shadow-sm);
        }

        .modal-icon svg {
            width: 24px;
            height: 24px;
            stroke: var(--text-primary);
        }

        .modal-title {
            font-size: 28px;
            font-weight: 500;
            color: var(--text-primary);
            flex: 1;
            letter-spacing: -0.5px;
        }

        .form-group {
            margin-bottom: 28px;
        }

        .form-label {
            display: block;
            font-size: 14px;
            color: var(--text-secondary);
            margin-bottom: 12px;
            font-weight: 500;
        }

        .form-textarea {
            width: 100%;
            background: var(--bg-secondary);
            border: 1px solid var(--border-light);
            border-radius: 10px;
            padding: 16px;
            color: var(--text-primary);
            font-size: 15px;
            font-family: 'Crimson Pro', serif;
            line-height: 1.7;
            min-height: 180px;
            resize: vertical;
            transition: all 0.3s ease;
            outline: none;
        }

        .form-textarea:focus {
            border-color: var(--accent-primary);
            background: white;
            box-shadow: var(--shadow-md);
        }

        .form-textarea::placeholder {
            color: var(--text-tertiary);
        }

        .media-upload-section {
            margin-top: 24px;
            padding-top: 24px;
            border-top: 1px solid var(--border-light);
        }

        .media-upload-label {
            display: block;
            font-size: 13px;
            color: var(--text-secondary);
            margin-bottom: 12px;
            font-weight: 500;
        }

        .media-buttons {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
        }

        .media-btn {
            display: flex;
            align-items: center;
            gap: 8px;
            padding: 10px 16px;
            background: var(--bg-secondary);
            border: 1px solid var(--border-light);
            border-radius: 8px;
            color: var(--text-secondary);
            font-size: 13px;
            cursor: pointer;
            transition: all 0.2s ease;
            font-family: 'Inter', sans-serif;
            font-weight: 500;
        }

        .media-btn:hover {
            background: var(--bg-primary);
            border-color: var(--border-medium);
        }

        .media-btn svg {
            width: 18px;
            height: 18px;
            stroke: var(--text-secondary);
        }

        .media-preview-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(120px, 1fr));
            gap: 12px;
            margin-top: 16px;
        }

        .media-preview-item {
            position: relative;
            aspect-ratio: 1;
            border-radius: 8px;
            overflow: hidden;
            background: var(--bg-secondary);
            border: 1px solid var(--border-light);
            box-shadow: var(--shadow-sm);
            transition: all 0.2s ease;
            cursor: pointer;
        }

        .media-preview-item:hover {
            box-shadow: var(--shadow-md);
            transform: scale(1.02);
        }

        .media-preview-item img,
        .media-preview-item video {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .media-preview-item audio {
            width: 100%;
            height: 100%;
        }

        .media-remove-btn {
            position: absolute;
            top: 6px;
            right: 6px;
            width: 24px;
            height: 24px;
            background: rgba(28, 25, 23, 0.8);
            border: none;
            border-radius: 50%;
            color: white;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.2s ease;
        }

        .media-remove-btn:hover {
            background: rgba(28, 25, 23, 0.95);
        }

        .audio-preview {
            display: flex;
            align-items: center;
            justify-content: center;
            padding: 12px;
        }

        .form-actions {
            display: flex;
            gap: 12px;
            margin-top: 32px;
        }

        .btn {
            flex: 1;
            padding: 14px 24px;
            border: none;
            border-radius: 10px;
            font-size: 15px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Inter', sans-serif;
        }

        .btn-primary {
            background: var(--text-primary);
            color: white;
        }

        .btn-primary:hover {
            background: var(--text-secondary);
            transform: translateY(-1px);
            box-shadow: var(--shadow-md);
        }

        .btn-secondary {
            background: var(--bg-secondary);
            color: var(--text-secondary);
            border: 1px solid var(--border-light);
        }

        .btn-secondary:hover {
            background: var(--bg-primary);
            border-color: var(--border-medium);
        }

        .btn-edit {
            padding: 8px 16px;
            font-size: 14px;
            display: inline-flex;
            align-items: center;
            gap: 6px;
        }

        .btn-edit svg {
            width: 16px;
            height: 16px;
        }

        .btn-delete {
            background: #fee;
            color: #c33;
            border: 1px solid #fcc;
        }

        .btn-delete:hover {
            background: #fdd;
            border-color: #fbb;
        }

        .bottom-actions {
            display: flex;
            gap: 16px;
            justify-content: center;
            padding: 40px 20px;
            flex-wrap: wrap;
        }

        .action-btn {
            padding: 12px 24px;
            background: white;
            border: 1px solid var(--border-light);
            border-radius: 10px;
            color: var(--text-secondary);
            font-size: 14px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Inter', sans-serif;
            display: flex;
            align-items: center;
            gap: 10px;
            font-weight: 500;
            position: relative;
            overflow: hidden;
        }

        .action-btn::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: radial-gradient(circle, rgba(212, 165, 116, 0.2), transparent);
            transform: translate(-50%, -50%);
            transition: width 0.6s, height 0.6s;
        }

        .action-btn:hover::before {
            width: 300px;
            height: 300px;
        }

        .action-btn:hover {
            background: var(--bg-secondary);
            border-color: var(--border-medium);
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        .action-btn.magical {
            background: linear-gradient(135deg, #d4a574 0%, #c9a66b 50%, #d4a574 100%);
            background-size: 200% 200%;
            animation: shimmer 3s ease infinite;
            color: white;
            border: none;
            font-weight: 600;
            letter-spacing: 0.3px;
        }

        .action-btn.magical:hover {
            transform: translateY(-2px) scale(1.05);
            box-shadow: 0 8px 24px rgba(212, 165, 116, 0.4);
        }

        @keyframes shimmer {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        .surprise-btn {
            background: linear-gradient(135deg, #e69fac 0%, #d88b95 50%, #e69fac 100%);
            background-size: 200% 200%;
            animation: shimmer 3s ease infinite;
            animation-delay: 1s;
        }

        .action-btn svg {
            width: 18px;
            height: 18px;
            stroke: var(--text-secondary);
        }

        .stats {
            text-align: center;
            margin-top: 60px;
            padding: 40px;
            background: linear-gradient(135deg, white 0%, var(--bg-secondary) 100%);
            border-radius: 12px;
            border: 1px solid var(--border-light);
            position: relative;
            overflow: hidden;
        }

        .stats::before {
            content: '';
            position: absolute;
            top: -50px;
            left: 50%;
            transform: translateX(-50%);
            width: 150px;
            height: 150px;
            background: radial-gradient(circle, rgba(212, 165, 116, 0.1) 0%, transparent 70%);
            border-radius: 50%;
            pointer-events: none;
        }

        .stats-content {
            font-family: 'Crimson Pro', serif;
            font-size: 18px;
            color: var(--text-secondary);
            line-height: 1.8;
            position: relative;
            z-index: 1;
        }

        .stats-number {
            font-size: 36px;
            font-weight: 400;
            color: var(--text-primary);
            margin: 0 8px;
        }

        .empty-state {
            text-align: center;
            padding: 32px;
            color: var(--text-tertiary);
            font-size: 14px;
        }

        .memory-modal-content {
            background: linear-gradient(135deg, #fefefe 0%, #fafaf9 100%);
            padding: 48px;
            text-align: center;
            position: relative;
        }

        .memory-modal-content::before {
            content: '✨';
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 32px;
            opacity: 0.3;
            animation: sparkleRotate 4s linear infinite;
        }

        .memory-modal-content::after {
            content: '✨';
            position: absolute;
            bottom: 20px;
            right: 20px;
            font-size: 32px;
            opacity: 0.3;
            animation: sparkleRotate 4s linear infinite reverse;
        }

        @keyframes sparkleRotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .memory-room-badge {
            display: inline-block;
            padding: 8px 16px;
            background: linear-gradient(135deg, rgba(212, 165, 116, 0.15), rgba(155, 135, 181, 0.15));
            border-radius: 20px;
            font-size: 13px;
            font-weight: 500;
            color: var(--text-secondary);
            margin-bottom: 24px;
            letter-spacing: 0.5px;
        }

        .memory-text {
            font-family: 'Crimson Pro', serif;
            font-size: 20px;
            line-height: 1.8;
            color: var(--text-primary);
            margin-bottom: 28px;
            font-style: italic;
        }

        .memory-media-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
            gap: 16px;
            margin-bottom: 24px;
        }

        .memory-media-item {
            border-radius: 12px;
            overflow: hidden;
            background: var(--bg-secondary);
            border: 1px solid var(--border-light);
            cursor: pointer;
            transition: transform 0.2s ease;
        }

        .memory-media-item:hover {
            transform: scale(1.02);
        }

        .memory-media-item img,
        .memory-media-item video {
            width: 100%;
            height: 180px;
            object-fit: cover;
        }

        .memory-date {
            font-size: 14px;
            color: var(--text-tertiary);
            margin-bottom: 24px;
        }

        /* Lightbox styles */
        .lightbox {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.95);
            z-index: 2000;
            align-items: center;
            justify-content: center;
            padding: 40px;
            animation: fadeInLightbox 0.3s ease;
        }

        .lightbox.active {
            display: flex;
        }

        @keyframes fadeInLightbox {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .lightbox-content {
            max-width: 90vw;
            max-height: 90vh;
            position: relative;
            animation: scaleIn 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        @keyframes scaleIn {
            from {
                opacity: 0;
                transform: scale(0.9);
            }
            to {
                opacity: 1;
                transform: scale(1);
            }
        }

        .lightbox-content img,
        .lightbox-content video {
            max-width: 100%;
            max-height: 90vh;
            object-fit: contain;
            border-radius: 8px;
        }

        .lightbox-close {
            position: absolute;
            top: -50px;
            right: 0;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            font-size: 24px;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .lightbox-close:hover {
            background: rgba(255, 255, 255, 0.3);
            transform: scale(1.1);
        }

        .lightbox-nav {
            position: absolute;
            top: 50%;
            transform: translateY(-50%);
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.2);
            color: white;
            border: none;
            font-size: 24px;
            cursor: pointer;
            transition: all 0.2s ease;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .lightbox-nav:hover {
            background: rgba(255, 255, 255, 0.3);
        }

        .lightbox-prev {
            left: 20px;
        }

        .lightbox-next {
            right: 20px;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 36px;
            }

            .rooms-grid {
                grid-template-columns: 1fr;
            }

            .modal-content {
                padding: 24px;
            }

            .welcome-message {
                padding: 32px 24px;
            }

            .signature {
                font-size: 18px;
                right: 20px;
            }

            .lightbox-content {
                padding: 20px;
            }

            .lightbox-nav {
                width: 40px;
                height: 40px;
                font-size: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="signature">𝒪𝐵</div>
    
    <div class="container">
        <header>
            <h1>Safe Space</h1>
            <p class="tagline">Your personal sanctuary for thoughts, feelings, and moments that matter</p>
            
            <div class="daily-quote" id="dailyQuote">
                <div class="quote-text" id="quoteText">"Loading wisdom..."</div>
                <div class="quote-author" id="quoteAuthor">— Unknown</div>
            </div>
        </header>

        <div class="welcome-message">
            <p class="welcome-text" id="welcomeText">This is your private corner of the universe. Everything you share here stays here—safe, encrypted, and just for you. Let this be the place where you can finally exhale.</p>
        </div>

        <div class="rooms-grid" id="roomsGrid"></div>

        <div class="bottom-actions">
            <button class="action-btn magical" onclick="showRandomMemory()">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"></path>
                </svg>
                Surprise Memory
            </button>
            <button class="action-btn surprise-btn" onclick="surpriseMe()">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M12 2a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"></path>
                </svg>
                Surprise Me!
            </button>
            <button class="action-btn" onclick="exportData()">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                    <polyline points="7 10 12 15 17 10"></polyline>
                    <line x1="12" y1="15" x2="12" y2="3"></line>
                </svg>
                Export Backup
            </button>
            <label class="action-btn" style="margin: 0; cursor: pointer;">
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                    <path d="M21 15v4a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2v-4"></path>
                    <polyline points="17 8 12 3 7 8"></polyline>
                    <line x1="12" y1="3" x2="12" y2="15"></line>
                </svg>
                Import Backup
                <input type="file" accept=".json" onchange="importData(event)" style="display: none;">
            </label>
        </div>

        <div class="stats">
            <div class="stats-content" id="statsContent">
                Nothing here yet... but this space is waiting for your first memory.
            </div>
        </div>
    </div>

    <!-- Modal -->
    <div class="modal" id="modal">
        <div class="modal-content"></div>
    </div>

    <!-- Lightbox -->
    <div class="lightbox" id="lightbox">
        <div class="lightbox-content" id="lightboxContent">
            <button class="lightbox-close" onclick="closeLightbox()">×</button>
            <button class="lightbox-nav lightbox-prev" onclick="navigateLightbox(-1)" style="display: none;">‹</button>
            <button class="lightbox-nav lightbox-next" onclick="navigateLightbox(1)" style="display: none;">›</button>
        </div>
    </div>

    <script>
        const INSPIRATIONAL_QUOTES = [
            { text: "Darling, you are absolutely fabulous, and don't let anyone tell you otherwise!", author: "Your Inner Rarity" },
            { text: "Every moment of authenticity is a small revolution.", author: "Unknown" },
            { text: "You are allowed to be both a masterpiece and a work in progress simultaneously.", author: "Sophia Bush" },
            { text: "The most courageous act is still to think for yourself. Aloud.", author: "Coco Chanel" },
            { text: "Elegance is not about being noticed, it's about being remembered.", author: "Giorgio Armani" },
            { text: "Your emotions make you human. Even the unpleasant ones have a purpose.", author: "Sabaa Tahir" },
            { text: "Be yourself; everyone else is already taken.", author: "Oscar Wilde" },
            { text: "You are enough, just as you are. Each emotion you feel, every thought you have, is valid.", author: "Unknown" },
            { text: "Vulnerability is the birthplace of love, belonging, joy, courage, and creativity.", author: "Brené Brown" },
            { text: "The privilege of a lifetime is to become who you truly are.", author: "Carl Jung" },
            { text: "What lies behind us and what lies before us are tiny matters compared to what lies within us.", author: "Ralph Waldo Emerson" },
            { text: "You yourself, as much as anybody in the entire universe, deserve your love and affection.", author: "Buddha" },
            { text: "Imperfection is beauty, madness is genius, and it's better to be absolutely ridiculous than absolutely boring.", author: "Marilyn Monroe" },
            { text: "To be beautiful means to be yourself. You don't need to be accepted by others. You need to accept yourself.", author: "Thich Nhat Hanh" },
            { text: "The most common way people give up their power is by thinking they don't have any.", author: "Alice Walker" }
        ];

        const ROOMS = [
            {
                id: 'freeform',
                icon: 'thought',
                title: 'What\'s On My Mind?',
                description: 'Stream of consciousness. No filters, just thoughts.',
                color: '#a8a29e'
            },
            {
                id: 'openwhen',
                icon: 'envelope',
                title: 'Open When...',
                description: 'Letters to yourself for when you need them—sealed with love until the right moment',
                color: '#e69fac'
            },
            {
                id: 'proud',
                icon: 'trophy',
                title: 'Proud Moments',
                description: 'Times you surprised yourself, when you were stronger than you knew',
                color: '#d4a574'
            },
            {
                id: 'compliments',
                icon: 'star',
                title: 'Kind Words',
                description: 'Compliments and affirming words that made you feel seen',
                color: '#d4a574'
            },
            {
                id: 'brave',
                icon: 'heart',
                title: 'Brave Moments',
                description: 'Times you did something scary, even when you were afraid',
                color: '#9b87b5'
            },
            {
                id: 'special',
                icon: 'sparkles',
                title: 'Special Moments',
                description: 'Memories that sparkle, moments you want to remember forever',
                color: '#e69fac'
            },
            {
                id: 'voices',
                icon: 'messages',
                title: 'Two Voices',
                description: 'The conversation between your inner critic and inner friend',
                color: '#7b9eb0'
            },
            {
                id: 'letters',
                icon: 'mail',
                title: 'Unsent Letters',
                description: 'Words you need to say but haven\'t sent—to anyone, even yourself',
                color: '#c9a66b'
            },
            {
                id: 'grateful',
                icon: 'flower',
                title: 'Gratitude',
                description: 'Small and large things that filled you with appreciation',
                color: '#d88b95'
            },
            {
                id: 'laughter',
                icon: 'smile',
                title: 'Joy Captured',
                description: 'Things that made you laugh, smile, or feel light',
                color: '#e5a868'
            },
            {
                id: 'scream',
                icon: 'lightning',
                title: 'Scream Room',
                description: 'Let it all out—rage, pain, unfairness. No judgment, just release.',
                color: '#c74440'
            },
            {
                id: 'identity',
                icon: 'rainbow',
                title: 'Being Me',
                description: 'Your journey of self-discovery and authenticity',
                color: '#9b87b5'
            },
            {
                id: 'creative',
                icon: 'palette',
                title: 'Creative Outlet',
                description: 'Art, writing, music—anything you create',
                color: '#e69fac'
            }
        ];

        const ICONS = {
            star: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="12 2 15.09 8.26 22 9.27 17 14.14 18.18 21.02 12 17.77 5.82 21.02 7 14.14 2 9.27 8.91 8.26 12 2"></polygon></svg>',
            heart: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>',
            sparkles: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 3l1.5 4.5L18 9l-4.5 1.5L12 15l-1.5-4.5L6 9l4.5-1.5L12 3zM19 12l1 3 3 1-3 1-1 3-1-3-3-1 3-1 1-3z"></path></svg>',
            messages: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path></svg>',
            mail: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"></path><polyline points="22,6 12,13 2,6"></polyline></svg>',
            flower: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="3"></circle><path d="M12 2a3 3 0 0 0 0 6 3 3 0 0 0 0-6zM12 16a3 3 0 0 0 0 6 3 3 0 0 0 0-6zM22 12a3 3 0 0 0-6 0 3 3 0 0 0 6 0zM8 12a3 3 0 0 0-6 0 3 3 0 0 0 6 0z"></path></svg>',
            smile: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="10"></circle><path d="M8 14s1.5 2 4 2 4-2 4-2"></path><line x1="9" y1="9" x2="9.01" y2="9"></line><line x1="15" y1="9" x2="15.01" y2="9"></line></svg>',
            cloud: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 10h-1.26A8 8 0 1 0 9 20h9a5 5 0 0 0 0-10z"></path></svg>',
            rainbow: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 17H2M22 14c0-5.5-4.5-10-10-10S2 8.5 2 14M19 14c0-3.9-3.1-7-7-7s-7 3.1-7 7M16 14c0-2.2-1.8-4-4-4s-4 1.8-4 4"></path></svg>',
            thought: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"></path><circle cx="9" cy="10" r="1"></circle><circle cx="12" cy="10" r="1"></circle><circle cx="15" cy="10" r="1"></circle></svg>',
            palette: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10c.93 0 1.68-.75 1.68-1.68 0-.42-.16-.81-.42-1.12-.25-.3-.41-.71-.41-1.15 0-.93.75-1.68 1.68-1.68h1.95c3.03 0 5.5-2.47 5.5-5.5C22 6.48 17.52 2 12 2z"></path><circle cx="6.5" cy="11.5" r="1.5"></circle><circle cx="9.5" cy="7.5" r="1.5"></circle><circle cx="14.5" cy="7.5" r="1.5"></circle><circle cx="17.5" cy="11.5" r="1.5"></circle></svg>',
            envelope: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z"></path></svg>',
            trophy: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M6 9H4.5a2.5 2.5 0 010-5H6M18 9h1.5a2.5 2.5 0 000-5H18"></path><path d="M18 20a8 8 0 01-6-2.667A8 8 0 016 20M6 4h12v6a6 6 0 01-12 0V4zM8 20v-2M16 20v-2"></path></svg>',
            lightning: '<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polygon points="13 2 3 14 12 14 11 22 21 10 12 10 13 2"></polygon></svg>'
        };

        let entries = {};
        let currentRoom = null;
        let currentMedia = [];
        let currentEditingEntry = null;
        let lightboxMedia = [];
        let currentLightboxIndex = 0;

        document.addEventListener('DOMContentLoaded', () => {
            loadData();
            renderRooms();
            updateStats();
            displayDailyQuote();
            createFloatingKisses();
        });

        function displayDailyQuote() {
            const quote = INSPIRATIONAL_QUOTES[Math.floor(Math.random() * INSPIRATIONAL_QUOTES.length)];
            document.getElementById('quoteText').textContent = `"${quote.text}"`;
            document.getElementById('quoteAuthor').textContent = `— ${quote.author}`;
        }

        function createSparkle(x, y, color = null) {
            const sparkle = document.createElement('div');
            sparkle.className = 'sparkle';
            if (color) {
                sparkle.style.background = `radial-gradient(circle, ${color} 0%, transparent 70%)`;
            }
            sparkle.style.left = x + 'px';
            sparkle.style.top = y + 'px';
            document.body.appendChild(sparkle);
            
            setTimeout(() => sparkle.remove(), 2000);
        }

        function createFloatingKisses() {
            setInterval(() => {
                if (Math.random() > 0.85) {
                    const kiss = document.createElement('div');
                    kiss.className = 'floating-kiss';
                    kiss.style.left = Math.random() * 100 + '%';
                    kiss.style.animationDuration = (15 + Math.random() * 10) + 's';
                    document.body.appendChild(kiss);
                    
                    setTimeout(() => kiss.remove(), 25000);
                }
            }, 8000);
        }

        function applyRoomTheme(room) {
            if (!room) {
                document.body.classList.remove('room-active');
                document.body.style.removeProperty('--active-room-color-light');
                document.body.style.removeProperty('--active-room-color-lighter');
                return;
            }

            const color = room.color;
            document.body.classList.add('room-active');
            
            const hex = color.replace('#', '');
            const r = parseInt(hex.substr(0, 2), 16);
            const g = parseInt(hex.substr(2, 2), 16);
            const b = parseInt(hex.substr(4, 2), 16);
            
            document.body.style.setProperty('--active-room-color-light', `rgba(${r}, ${g}, ${b}, 0.08)`);
            document.body.style.setProperty('--active-room-color-lighter', `rgba(${r}, ${g}, ${b}, 0.04)`);
            
            for (let i = 0; i < 15; i++) {
                setTimeout(() => {
                    const x = Math.random() * window.innerWidth;
                    const y = Math.random() * window.innerHeight;
                    createSparkle(x, y, `rgba(${r}, ${g}, ${b}, 0.8)`);
                }, i * 50);
            }
        }

        function renderRooms() {
            const grid = document.getElementById('roomsGrid');
            grid.innerHTML = ROOMS.map(room => {
                const roomEntries = entries[room.id] || [];
                const previewEntries = roomEntries.slice(-3);
                
                let previewHTML = '';
                if (previewEntries.length > 0) {
                    previewHTML = '<div class="entries-preview">' + previewEntries.map((entry, index) => {
                        const truncated = entry.text.length > 80 ? entry.text.substring(0, 80) + '...' : entry.text;
                        const mediaIndicator = entry.media && entry.media.length > 0 ? 
                            `<span class="entry-media-indicator">
                                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <rect x="3" y="3" width="18" height="18" rx="2" ry="2"></rect>
                                    <circle cx="8.5" cy="8.5" r="1.5"></circle>
                                    <polyline points="21 15 16 10 5 21"></polyline>
                                </svg>
                                ${entry.media.length}
                            </span>` : '';
                        return `<div class="entry-snippet" onclick="event.stopPropagation(); openRoom('${room.id}')">${truncated}${mediaIndicator}</div>`;
                    }).join('') + '</div>';
                } else {
                    previewHTML = '<div class="empty-state">No entries yet. Click to start.</div>';
                }
                
                return `
                    <div class="room" style="--room-color: ${room.color};" onclick="openRoom('${room.id}')">
                        <div class="room-header">
                            <div class="room-icon">${ICONS[room.icon]}</div>
                            <div class="room-header-content">
                                <div class="room-title">${room.title}</div>
                                <div class="room-count">${roomEntries.length} ${roomEntries.length === 1 ? 'entry' : 'entries'}</div>
                            </div>
                        </div>
                        <div class="room-description">${room.description}</div>
                        ${previewHTML}
                        <button class="add-entry-btn" onclick="event.stopPropagation(); openRoom('${room.id}', true)">+ Add Entry</button>
                    </div>
                `;
            }).join('');
        }

        function openRoom(roomId, forceNew = false) {
            const room = ROOMS.find(r => r.id === roomId);
            if (!room) return;

            currentRoom = room;
            currentEditingEntry = null;
            applyRoomTheme(room);

            const roomEntries = entries[roomId] || [];

            if (forceNew || roomEntries.length === 0) {
                showEntryForm(room);
            } else {
                showRoomEntries(room, roomEntries);
            }
        }

        function showRoomEntries(room, roomEntries) {
            const modal = document.getElementById('modal');
            const entriesHTML = roomEntries.map((entry, index) => {
                const date = new Date(entry.date).toLocaleDateString('en-US', {
                    weekday: 'long',
                    year: 'numeric',
                    month: 'long',
                    day: 'numeric',
                    hour: '2-digit',
                    minute: '2-digit'
                });

                let mediaHTML = '';
                if (entry.media && entry.media.length > 0) {
                    mediaHTML = `
                        <div style="display: grid; grid-template-columns: repeat(auto-fill, minmax(100px, 1fr)); gap: 8px; margin: 12px 0;">
                            ${entry.media.map((media, mediaIndex) => {
                                if (media.type === 'photo') {
                                    return `<img src="${media.data}" style="width: 100%; height: 100px; object-fit: cover; border-radius: 8px; cursor: pointer;" onclick="openLightbox(${index}, ${mediaIndex})">`;
                                } else if (media.type === 'video') {
                                    return `<video src="${media.data}" style="width: 100%; height: 100px; object-fit: cover; border-radius: 8px; cursor: pointer;" onclick="openLightbox(${index}, ${mediaIndex})"></video>`;
                                } else if (media.type === 'audio') {
                                    return `<audio src="${media.data}" controls style="width: 100%;"></audio>`;
                                }
                                return '';
                            }).join('')}
                        </div>
                    `;
                }

                return `
                    <div style="padding: 20px; background: var(--bg-secondary); border-radius: 12px; margin-bottom: 16px; border-left: 3px solid ${room.color};">
                        <div style="font-size: 14px; color: var(--text-tertiary); margin-bottom: 12px;">${date}</div>
                        ${entry.text ? `<div style="margin-bottom: 12px; white-space: pre-wrap; line-height: 1.6;">${entry.text}</div>` : ''}
                        ${mediaHTML}
                        <div style="display: flex; gap: 8px; margin-top: 12px;">
                            <button class="btn btn-secondary btn-edit" onclick="editEntry('${room.id}', ${index})">
                                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                                    <path d="M11 4H4a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-7"></path>
                                    <path d="M18.5 2.5a2.121 2.121 0 0 1 3 3L12 15l-4 1 1-4 9.5-9.5z"></path>
                                </svg>
                                Edit
                            </button>
                            <button class="btn btn-secondary btn-delete btn-edit" onclick="deleteEntry('${room.id}', ${index})">Delete</button>
                        </div>
                    </div>
                `;
            }).join('');

            modal.innerHTML = `
                <div class="modal-content">
                    <div class="modal-header">
                        <div class="modal-icon">${ICONS[room.icon]}</div>
                        <h2 class="modal-title">${room.title}</h2>
                    </div>
                    <div style="max-height: 60vh; overflow-y: auto; margin-bottom: 24px;">
                        ${entriesHTML}
                    </div>
                    <div class="form-actions">
                        <button class="btn btn-secondary" onclick="closeModal()">Close</button>
                        <button class="btn btn-primary" onclick="showEntryForm(ROOMS.find(r => r.id === '${room.id}'))">New Entry</button>
                    </div>
                </div>
            `;
            modal.classList.add('active');
        }

        function showEntryForm(room) {
            currentRoom = room;
            const modal = document.getElementById('modal');
            
            modal.innerHTML = `
                <div class="modal-content">
                    <div class="modal-header">
                        <div class="modal-icon">${ICONS[room.icon]}</div>
                        <h2 class="modal-title">${currentEditingEntry ? 'Edit Entry' : room.title}</h2>
                    </div>

                    <div class="form-group">
                        <label class="form-label">${room.description}</label>
                        <textarea 
                            class="form-textarea" 
                            id="entryText" 
                            placeholder="Let it out... this space holds you."
                        >${currentEditingEntry ? currentEditingEntry.text : ''}</textarea>
                    </div>

                    <div class="media-upload-section">
                        <label class="media-upload-label">Add media (optional)</label>
                        <div class="media-buttons">
                            <button class="media-btn" onclick="document.getElementById('photoInput').click()">
                                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <rect x="3" y="3" width="18" height="18" rx="2" ry="2"></rect>
                                    <circle cx="8.5" cy="8.5" r="1.5"></circle>
                                    <polyline points="21 15 16 10 5 21"></polyline>
                                </svg>
                                Photo
                            </button>
                            <button class="media-btn" onclick="document.getElementById('videoInput').click()">
                                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <polygon points="23 7 16 12 23 17 23 7"></polygon>
                                    <rect x="1" y="5" width="15" height="14" rx="2" ry="2"></rect>
                                </svg>
                                Video
                            </button>
                            <button class="media-btn" onclick="document.getElementById('audioInput').click()">
                                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                                    <path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"></path>
                                    <path d="M19 10v2a7 7 0 0 1-14 0v-2"></path>
                                    <line x1="12" y1="19" x2="12" y2="23"></line>
                                    <line x1="8" y1="23" x2="16" y2="23"></line>
                                </svg>
                                Audio
                            </button>
                        </div>
                        <input type="file" id="photoInput" accept="image/*" style="display: none;" onchange="handleMediaUpload(event, 'photo')" multiple>
                        <input type="file" id="videoInput" accept="video/*" style="display: none;" onchange="handleMediaUpload(event, 'video')" multiple>
                        <input type="file" id="audioInput" accept="audio/*" style="display: none;" onchange="handleMediaUpload(event, 'audio')" multiple>
                        
                        <div class="media-preview-grid" id="mediaPreview"></div>
                    </div>

                    <div class="form-actions">
                        <button class="btn btn-secondary" onclick="closeModal()">Maybe Later</button>
                        <button class="btn btn-primary" onclick="saveEntry()">${currentEditingEntry ? 'Update' : 'Keep This Safe'}</button>
                    </div>
                </div>
            `;
            
            if (currentEditingEntry && currentEditingEntry.media) {
                currentMedia = [...currentEditingEntry.media];
                renderMediaPreview();
            }
            
            modal.classList.add('active');
        }

        function editEntry(roomId, entryIndex) {
            const room = ROOMS.find(r => r.id === roomId);
            const entry = entries[roomId][entryIndex];
            
            if (!entry || !room) return;
            
            currentRoom = room;
            currentEditingEntry = {
                ...entry,
                index: entryIndex,
                roomId: roomId
            };
            
            showEntryForm(room);
        }

        function deleteEntry(roomId, entryIndex) {
            if (confirm('Are you sure you want to delete this entry? This cannot be undone.')) {
                // Delete the entry
                entries[roomId].splice(entryIndex, 1);
                
                // Save to localStorage
                saveData();
                
                // Update the home page
                renderRooms();
                updateStats();
                
                // Find the room and refresh the modal
                const room = ROOMS.find(r => r.id === roomId);
                const roomEntries = entries[roomId] || [];
                
                // If no more entries, close modal. Otherwise refresh it.
                if (roomEntries.length === 0) {
                    closeModal();
                } else {
                    // Force refresh the modal with updated entries
                    currentRoom = room;
                    showRoomEntries(room, roomEntries);
                }
            }
        }

        function viewEntry(roomId, entryIndex) {
            const room = ROOMS.find(r => r.id === roomId);
            const entry = entries[roomId][entryIndex];
            
            if (!entry || !room) return;
            
            showMemoryModal({ ...entry, roomId, roomTitle: room.title });
        }

        function closeModal() {
            document.getElementById('modal').classList.remove('active');
            applyRoomTheme(null);
            currentRoom = null;
            currentMedia = [];
            currentEditingEntry = null;
        }

        function handleMediaUpload(event, type) {
            const files = Array.from(event.target.files);
            
            files.forEach(file => {
                const reader = new FileReader();
                reader.onload = (e) => {
                    currentMedia.push({
                        type: type,
                        data: e.target.result,
                        name: file.name
                    });
                    renderMediaPreview();
                };
                reader.readAsDataURL(file);
            });
        }

        function renderMediaPreview() {
            const preview = document.getElementById('mediaPreview');
            preview.innerHTML = currentMedia.map((media, index) => {
                let content = '';
                if (media.type === 'photo') {
                    content = `<img src="${media.data}" alt="Preview">`;
                } else if (media.type === 'video') {
                    content = `<video src="${media.data}" controls></video>`;
                } else if (media.type === 'audio') {
                    content = `<div class="audio-preview"><audio src="${media.data}" controls></audio></div>`;
                }
                
                return `
                    <div class="media-preview-item">
                        ${content}
                        <button class="media-remove-btn" onclick="removeMedia(${index})">×</button>
                    </div>
                `;
            }).join('');
        }

        function removeMedia(index) {
            currentMedia.splice(index, 1);
            renderMediaPreview();
        }

        function saveEntry() {
            const text = document.getElementById('entryText').value.trim();
            if (!text && currentMedia.length === 0) return;
            if (!currentRoom) return;

            if (!entries[currentRoom.id]) {
                entries[currentRoom.id] = [];
            }

            if (currentEditingEntry) {
                entries[currentEditingEntry.roomId][currentEditingEntry.index] = {
                    text: text,
                    media: [...currentMedia],
                    date: currentEditingEntry.date,
                    id: currentEditingEntry.id,
                    editedAt: new Date().toISOString()
                };
            } else {
                entries[currentRoom.id].push({
                    text: text,
                    media: [...currentMedia],
                    date: new Date().toISOString(),
                    id: Date.now()
                });
            }

            saveData();
            renderRooms();
            updateStats();
            closeModal();
        }

        function updateStats() {
            const totalEntries = Object.values(entries).reduce((sum, arr) => sum + arr.length, 0);
            const totalRooms = Object.keys(entries).filter(key => entries[key].length > 0).length;

            const statsEl = document.getElementById('statsContent');
            if (totalEntries === 0) {
                statsEl.innerHTML = 'Nothing here yet... but this space is waiting for your first memory.';
            } else if (totalEntries === 1) {
                statsEl.innerHTML = '🌱 You\'ve planted your first seed. One beautiful moment preserved.';
            } else if (totalEntries < 5) {
                statsEl.innerHTML = `✨ ${totalEntries} moments captured—your garden is beginning to grow.`;
            } else if (totalEntries < 10) {
                statsEl.innerHTML = `🌸 ${totalEntries} memories blooming across ${totalRooms} ${totalRooms === 1 ? 'space' : 'spaces'}. Look at you creating beauty.`;
            } else if (totalEntries < 25) {
                statsEl.innerHTML = `🌿 ${totalEntries} precious moments held safe across ${totalRooms} spaces. This is becoming something special.`;
            } else if (totalEntries < 50) {
                statsEl.innerHTML = `🌺 ${totalEntries} memories preserved—each one a testament to your journey through ${totalRooms} different spaces.`;
            } else {
                statsEl.innerHTML = `🌳 ${totalEntries} moments of your life, treasured across ${totalRooms} sacred spaces. What a beautiful collection of your story.`;
            }
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
                version: '3.0',
                mediaCount: Object.values(entries).reduce((sum, arr) => 
                    sum + arr.reduce((mediaSum, entry) => mediaSum + (entry.media?.length || 0), 0), 0)
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
                        if (confirm('This will replace all your current data. Continue?')) {
                            entries = data.entries;
                            saveData();
                            renderRooms();
                            updateStats();
                            alert('Backup restored successfully! ✨');
                        }
                    }
                } catch (error) {
                    alert('Could not load backup. Please check the file.');
                }
            };
            reader.readAsText(file);
        }

        function showRandomMemory() {
            const allEntries = [];
            
            Object.keys(entries).forEach(roomId => {
                const room = ROOMS.find(r => r.id === roomId);
                if (entries[roomId] && entries[roomId].length > 0) {
                    entries[roomId].forEach(entry => {
                        allEntries.push({ ...entry, roomId, roomTitle: room?.title || 'Unknown' });
                    });
                }
            });

            if (allEntries.length === 0) {
                alert('No memories yet, darling! Start creating some beautiful moments first. ✨');
                return;
            }

            const randomEntry = allEntries[Math.floor(Math.random() * allEntries.length)];
            showMemoryModal(randomEntry);
        }

        function showMemoryModal(entry) {
            const modal = document.getElementById('modal');
            
            let mediaHTML = '';
            if (entry.media && entry.media.length > 0) {
                mediaHTML = '<div class="memory-media-grid">' + 
                    entry.media.map((m, index) => {
                        if (m.type === 'photo') {
                            return `<div class="memory-media-item" onclick="openLightboxDirect(${JSON.stringify(entry.media).replace(/"/g, '&quot;')}, ${index})"><img src="${m.data}" alt="Memory"></div>`;
                        } else if (m.type === 'video') {
                            return `<div class="memory-media-item" onclick="openLightboxDirect(${JSON.stringify(entry.media).replace(/"/g, '&quot;')}, ${index})"><video src="${m.data}" controls></video></div>`;
                        } else if (m.type === 'audio') {
                            return `<div class="memory-media-item"><audio src="${m.data}" controls></audio></div>`;
                        }
                        return '';
                    }).join('') +
                    '</div>';
            }

            const date = new Date(entry.date).toLocaleDateString('en-US', { 
                year: 'numeric', 
                month: 'long', 
                day: 'numeric' 
            });

            modal.innerHTML = `
                <div class="modal-content">
                    <div class="memory-modal-content">
                        <div class="memory-room-badge">${entry.roomTitle}</div>
                        <div class="memory-text">"${entry.text}"</div>
                        ${mediaHTML}
                        <div class="memory-date">Preserved on ${date}</div>
                        <p style="font-size: 13px; color: var(--text-tertiary); text-align: center; margin: 20px 0;">💡 To edit or delete this entry, close this and click on the "${entry.roomTitle}" room</p>
                        <div class="form-actions" style="margin-top: 32px;">
                            <button class="btn btn-secondary" onclick="closeModal()">Close</button>
                            <button class="btn btn-primary" onclick="showRandomMemory()">Another Memory</button>
                        </div>
                    </div>
                </div>
            `;

            modal.classList.add('active');
        }

        function surpriseMe() {
            const surprises = [
                () => {
                    for (let i = 0; i < 12; i++) {
                        setTimeout(() => {
                            const x = window.innerWidth / 2 + (Math.random() - 0.5) * 400;
                            const y = window.innerHeight / 2 + (Math.random() - 0.5) * 400;
                            createSparkle(x, y);
                        }, i * 80);
                    }
                    setTimeout(() => {
                        alert('✨ You are absolutely magnificent, darling! ✨');
                    }, 1000);
                },
                () => {
                    const compliments = [
                        "Your existence is a work of art! 🎨",
                        "Darling, you're simply divine! 💎",
                        "The world is better with you in it! 🌟",
                        "You are fabulous beyond measure! ✨",
                        "Your spirit shines so brightly! 💫",
                        "You deserve all the beautiful things! 🌸"
                    ];
                    alert(compliments[Math.floor(Math.random() * compliments.length)]);
                },
                () => {
                    displayDailyQuote();
                    const quoteEl = document.getElementById('dailyQuote');
                    quoteEl.style.animation = 'none';
                    setTimeout(() => {
                        quoteEl.style.animation = 'fadeIn 0.8s ease';
                    }, 10);
                    alert('New inspiration just for you! 💝');
                },
                () => {
                    for (let i = 0; i < 8; i++) {
                        setTimeout(() => {
                            const kiss = document.createElement('div');
                            kiss.className = 'floating-kiss';
                            kiss.style.left = (30 + Math.random() * 40) + '%';
                            kiss.style.animationDuration = '4s';
                            kiss.style.opacity = '0.25';
                            document.body.appendChild(kiss);
                            setTimeout(() => kiss.remove(), 4000);
                        }, i * 150);
                    }
                    setTimeout(() => {
                        alert('Sending you all the love! 💕');
                    }, 1200);
                }
            ];

            const surprise = surprises[Math.floor(Math.random() * surprises.length)];
            surprise();
        }

        // Lightbox functions
        function openLightbox(entryIndex, mediaIndex) {
            const roomId = currentRoom.id;
            const entry = entries[roomId][entryIndex];
            
            lightboxMedia = entry.media.filter(m => m.type === 'photo' || m.type === 'video');
            currentLightboxIndex = lightboxMedia.findIndex((m, i) => {
                const photoCount = entry.media.slice(0, mediaIndex).filter(m => m.type === 'photo' || m.type === 'video').length;
                return i === photoCount;
            });
            
            showLightboxMedia();
            document.getElementById('lightbox').classList.add('active');
            
            const prevBtn = document.querySelector('.lightbox-prev');
            const nextBtn = document.querySelector('.lightbox-next');
            if (lightboxMedia.length > 1) {
                prevBtn.style.display = 'flex';
                nextBtn.style.display = 'flex';
            } else {
                prevBtn.style.display = 'none';
                nextBtn.style.display = 'none';
            }
        }

        function openLightboxDirect(media, startIndex) {
            lightboxMedia = media.filter(m => m.type === 'photo' || m.type === 'video');
            currentLightboxIndex = startIndex;
            
            showLightboxMedia();
            document.getElementById('lightbox').classList.add('active');
            
            const prevBtn = document.querySelector('.lightbox-prev');
            const nextBtn = document.querySelector('.lightbox-next');
            if (lightboxMedia.length > 1) {
                prevBtn.style.display = 'flex';
                nextBtn.style.display = 'flex';
            } else {
                prevBtn.style.display = 'none';
                nextBtn.style.display = 'none';
            }
        }

        function showLightboxMedia() {
            const content = document.getElementById('lightboxContent');
            const media = lightboxMedia[currentLightboxIndex];
            
            const closeBtn = content.querySelector('.lightbox-close');
            const prevBtn = content.querySelector('.lightbox-prev');
            const nextBtn = content.querySelector('.lightbox-next');
            
            content.innerHTML = '';
            
            if (media.type === 'photo') {
                const img = document.createElement('img');
                img.src = media.data;
                content.appendChild(img);
            } else if (media.type === 'video') {
                const video = document.createElement('video');
                video.src = media.data;
                video.controls = true;
                video.autoplay = true;
                content.appendChild(video);
            }
            
            content.appendChild(closeBtn);
            if (lightboxMedia.length > 1) {
                content.appendChild(prevBtn);
                content.appendChild(nextBtn);
            }
        }

        function closeLightbox() {
            document.getElementById('lightbox').classList.remove('active');
            lightboxMedia = [];
            currentLightboxIndex = 0;
        }

        function navigateLightbox(direction) {
            currentLightboxIndex += direction;
            if (currentLightboxIndex < 0) {
                currentLightboxIndex = lightboxMedia.length - 1;
            } else if (currentLightboxIndex >= lightboxMedia.length) {
                currentLightboxIndex = 0;
            }
            showLightboxMedia();
        }

        // Event listeners
        document.getElementById('modal').addEventListener('click', (e) => {
            if (e.target.id === 'modal') {
                closeModal();
            }
        });

        document.getElementById('lightbox').addEventListener('click', (e) => {
            if (e.target.id === 'lightbox') {
                closeLightbox();
            }
        });

        document.addEventListener('keydown', (e) => {
            if (e.key === 'Escape') {
                if (document.getElementById('lightbox').classList.contains('active')) {
                    closeLightbox();
                } else {
                    closeModal();
                }
            } else if (document.getElementById('lightbox').classList.contains('active')) {
                if (e.key === 'ArrowLeft') {
                    navigateLightbox(-1);
                } else if (e.key === 'ArrowRight') {
                    navigateLightbox(1);
                }
            }
        });
    </script>
</body>
</html>
