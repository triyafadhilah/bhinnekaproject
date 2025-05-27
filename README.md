<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bhinneka - Media Pembelajaran Budaya Indonesia</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap');
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: #f8fafc;
        }
        
        /* Accessibility Features */
        .focus-visible:focus {
            outline: 3px solid #3b82f6;
            outline-offset: 2px;
        }
        
        /* Skip to content link */
        .skip-link {
            position: absolute;
            top: -40px;
            left: 0;
            background: #3b82f6;
            color: white;
            padding: 8px;
            z-index: 100;
            transition: top 0.3s;
        }
        
        .skip-link:focus {
            top: 0;
        }
        
        /* Card Flip Animation */
        .card-flip {
            perspective: 1000px;
            height: 150px;
        }
        
        .card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            transition: transform 0.6s;
            transform-style: preserve-3d;
        }
        
        .card-flip.flipped .card-inner {
            transform: rotateY(180deg);
        }
        
        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 0.5rem;
        }
        
        .card-back {
            transform: rotateY(180deg);
        }
        
        /* Memory Card Game */
        .memory-card {
            perspective: 1000px;
            transform-style: preserve-3d;
            transition: transform 0.5s;
        }
        
        .memory-card.flipped {
            transform: rotateY(180deg);
        }
        
        /* Drag and Drop */
        .drag-item {
            cursor: grab;
            user-select: none;
        }
        
        .drag-item:active {
            cursor: grabbing;
        }
        
        .drop-target {
            border: 2px dashed #ccc;
            transition: all 0.3s;
        }
        
        .drop-target.highlight {
            border-color: #4ade80;
            background-color: rgba(74, 222, 128, 0.1);
        }
        
        .drop-target.correct {
            border-color: #4ade80;
            background-color: rgba(74, 222, 128, 0.2);
        }
        
        /* Quiz Options */
        .quiz-option:hover {
            background-color: #f0fdf4;
        }
        
        .quiz-option.selected {
            background-color: #dcfce7;
            border-color: #4ade80;
        }
        
        .quiz-option.correct {
            background-color: #d1fae5;
            border-color: #34d399;
        }
        
        .quiz-option.incorrect {
            background-color: #fee2e2;
            border-color: #f87171;
        }
        
        /* Content Containers */
        .content-container {
            display: none;
        }
        
        .content-container.active {
            display: block;
        }
        
        /* Navigation Buttons */
        .nav-link {
            position: relative;
            transition: all 0.3s;
        }
        
        .nav-link::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -2px;
            left: 0;
            background-color: #3b82f6;
            transition: width 0.3s;
        }
        
        .nav-link:hover::after {
            width: 100%;
        }
        
        .nav-link.active::after {
            width: 100%;
        }
        
        /* Game Cards */
        .game-card {
            transition: all 0.3s;
        }
        
        .game-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
        }
        
        /* Word Scramble */
        .word-scramble-letter {
            cursor: pointer;
            transition: all 0.2s;
        }
        
        .word-scramble-letter:hover {
            transform: translateY(-5px);
        }
        
        /* Timeline */
        .timeline-item {
            position: relative;
        }
        
        .timeline-item::before {
            content: '';
            position: absolute;
            left: 15px;
            top: 0;
            height: 100%;
            width: 2px;
            background-color: #3b82f6;
        }
        
        .timeline-item:first-child::before {
            top: 50%;
        }
        
        .timeline-item:last-child::before {
            height: 50%;
        }
        
        .timeline-dot {
            position: relative;
            z-index: 2;
            background-color: #3b82f6;
        }
        
        /* High Contrast Mode */
        .high-contrast {
            filter: contrast(1.5);
        }
        
        /* Large Text Mode */
        .large-text {
            font-size: 1.2em;
            line-height: 1.6;
        }
        
