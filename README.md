
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Special Surprise</title>
    <style>
        :root {
            --primary: #ff4d6d;
            --secondary: #ffccd5;
            --bg: #fff0f3;
        }
        body {
            margin: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: var(--bg);
            font-family: 'Segoe UI', sans-serif;
            overflow-x: hidden;
        }

        /* Envelope Styles */
        .envelope-wrapper {
            cursor: pointer;
            transition: transform 0.3s;
        }
        .envelope {
            position: relative;
            width: 280px;
            height: 180px;
            background: #ff8fa3;
            border-radius: 0 0 10px 10px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        .envelope::before {
            content: "";
            position: absolute;
            top: -100px;
            left: 0;
            border-left: 140px solid transparent;
            border-right: 140px solid transparent;
            border-bottom: 100px solid #ff8fa3;
            z-index: 2;
        }
        .heart-seal {
            position: absolute;
            top: -10px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 30px;
            z-index: 3;
            animation: pulse 1.5s infinite;
        }

        /* Message Card Styles */
        .card {
            background: white;
            width: 90%;
            max-width: 500px;
            padding: 2rem;
            border-radius: 20px;
            box-shadow: 0 15px 35px rgba(0,0,0,0.1);
            text-align: center;
            display: none;
            max-height: 80vh;
            overflow-y: auto;
        }
        .story-text {
            font-size: 1.05rem;
            line-height: 1.6;
            color: #444;
            text-align: left;
            white-space: pre-line;
            margin-bottom: 20px;
        }
        
        /* Final Proposal Styles */
        .proposal-card { display: none; text-align: center; }
        .buttons { display: flex; justify-content: center; gap: 15px; margin-top: 25px; }
        button {
            padding: 12px 30px;
            font-size: 1.1rem;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: 0.3s;
        }
        .btn-next { background: var(--primary); color: white; width: 100%; }
        #yesBtn { background: var(--primary); color: white; }
        #noBtn { background: #999; color: white; position: relative; }

        @keyframes pulse {
            0% { transform: translateX(-50%) scale(1); }
            50% { transform: translateX(-50%) scale(1.2); }
            100% { transform: translateX(-50%) scale(1); }
        }
        .hidden { display: none !important; }
    </style>
</head>
<body>

    <div id="envelopeSection" class="envelope-wrapper" onclick="openEnvelope()">
        <div class="envelope">
            <div class="heart-seal">❤️</div>
        </div>
        <p style="text-align: center; color: #d63384; font-weight: bold; margin-top: 20px;">You have a letter...</p>
    </div>

    <div id="messageCard" class="card">
        <div class="story-text">
Helloo!💗
We were once just a stranger didn’t even knew how we both are just random stranger. When i texted you i never knew you would become so special for me like everything with you feels right even if its wrong. Just like talking everyday the day came we met in person both of us shy didn’t knew what to talk how to talk😅but anyhow we managed.

As talking daily we booked journey from stranger to friends and then friends to best friends. As going through journey we known each other like no one did we both came to know each others secrets nd all dark side white side tbh best friends are those who stays even after seeing your flaws🤭

Randomly we started getting more close being with you felt so nice that i didn’t knew how to stay without you like you are the only friend for me.!

We grew up old together ik we didn’t spend much time but its more than 4 years now can u bealive we still together even after fighting so much😅 cause baby me cheez badi hu mast mast🫣 with me u will lovee ur life. Things weren’t good in between like we know every friendship has ups and down jaha pyar hai vaha ladaii bhi hai but we dealed with it😁 as the days passed we came moree close ik i started to feel for you i started falling for you but i decided not to share this to u untill the right moment comes and the day comes u shared something i was soo happy from then like i won the world. Sometimes i was scared of you will it work together?

Being with you taught me what comfort feels like. You became my safe place, my person, the one I want to tell everything to—good days, bad days, silly things, everything. With you, I can be myself without pretending, without fear of being judged. And that means everything to me. No matter what name we give us friends, best friends, something more! I just know one thing: I want you in my life. Today, tomorrow, and all the days that come after.
        </div>
        <button class="btn-next" onclick="showProposal()">Click for one more thing...</button>
    </div>

    <div id="proposalCard" class="card">
        <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHp4Zmt4Zmt4Zmt4Zmt4Zmt4Zmt4Zmt4Zmt4Zmt4Zmt4Zmt4JmVwPXYxX2ludGVybmFsX2dpZl9ieV9pZCZjdD1z/L4lvB7Ssh_pB9Q29mR/giphy.gif" width="150">
        <h1 style="color: #d32f2f;">So... will you be mine forever? 💍</h1>
        <div class="buttons">
            <button id="yesBtn" onclick="celebrate()">Yes!</button>
            <button id="noBtn" onmouseover="moveButton()">No</button>
        </div>
    </div>

    <div id="successCard" class="card">
               <h1>Yayyy!!Finally I can call you MINE❤️</h1>
        <p> You said yess i knew you would say yes my cutie pie!❤️</p>
    </div>

    <script>
        function openEnvelope() {
            document.getElementById('envelopeSection').classList.add('hidden');
            document.getElementById('messageCard').style.display = 'block';
        }

        function showProposal() {
            document.getElementById('messageCard').style.display = 'none';
            document.getElementById('proposalCard').style.display = 'block';
        }

        function moveButton() {
            const btn = document.getElementById('noBtn');
            const x = Math.random() * (window.innerWidth - btn.offsetWidth);
            const y = Math.random() * (window.innerHeight - btn.offsetHeight);
            btn.style.position = 'fixed';
            btn.style.left = x + 'px';
            btn.style.top = y + 'px';
        }

        function celebrate() {
            document.getElementById('proposalCard').style.display = 'none';
            document.getElementById('successCard').style.display = 'block';
            document.body.style.backgroundColor = '#ffc1cf';
        }
    </script>
</body>
</html>
