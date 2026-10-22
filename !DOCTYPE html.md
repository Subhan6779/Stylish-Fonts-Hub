<!DOCTYPE html>  
<html lang="en">  
<head>  
    <meta charset="UTF-8">  
    <meta name="viewport" content="width=device-width, initial-scale=1.0">  
    <title>FancyTextPro - Unlimited 1000+ Stylish Font Generator</title>  
    <style>  
        * {  
            margin: 0;  
            padding: 0;  
            box-sizing: border-box;  
            font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;  
        }  
  
        body {  
            background-color: #0b0f19;  
            color: #f1f5f9;  
            padding-bottom: 50px;  
        }  
  
        header {  
            background-color: #111827;  
            padding: 20px;  
            text-align: center;  
            border-bottom: 3px solid #8b5cf6;  
            position: sticky;  
            top: 0;  
            z-index: 100;  
        }  
  
        header h1 {  
            font-size: 22px;  
            color: #a78bfa;  
            letter-spacing: 1px;  
            font-weight: 900;  
        }  
  
        header p {  
            color: #9ca3af;  
            font-size: 12px;  
            margin-top: 5px;  
        }  
  
        .container {  
            max-width: 800px;  
            margin: 20px auto;  
            padding: 0 15px;  
        }  
  
        /* Ad Placement Box */  
        .ad-box {  
            background-color: #111827;  
            border: 1px dashed #374151;  
            padding: 12px;  
            text-align: center;  
            color: #6b7280;  
            font-size: 12px;  
            margin-bottom: 20px;  
            border-radius: 8px;  
        }  
  
        /* Input Textbox */  
        .input-box {  
            width: 100%;  
            padding: 16px;  
            font-size: 16px;  
            background-color: #111827;  
            border: 2px solid #8b5cf6;  
            border-radius: 12px;  
            color: white;  
            outline: none;  
            margin-bottom: 15px;  
        }  
  
        /* Stats Counter */  
        .counter-badge {  
            background: #1f2937;  
            color: #a78bfa;  
            padding: 8px 15px;  
            border-radius: 20px;  
            font-size: 13px;  
            font-weight: bold;  
            display: inline-block;  
            margin-bottom: 15px;  
        }  
  
        /* Font Results Grid */  
        .font-card {  
            background-color: #111827;  
            border-radius: 10px;  
            padding: 12px 15px;  
            margin-bottom: 10px;  
            display: flex;  
            align-items: center;  
            justify-content: space-between;  
            border: 1px solid #1f2937;  
            gap: 15px;  
        }  
  
        .font-info {  
            overflow: hidden;  
        }  
  
        .font-title {  
            font-size: 10px;  
            color: #9ca3af;  
            margin-bottom: 3px;  
            font-weight: 600;  
            text-transform: uppercase;  
        }  
  
        .font-text {  
            font-size: 17px;  
            word-break: break-all;  
            color: #ffffff;  
            font-weight: 500;  
        }  
  
        .copy-btn {  
            padding: 7px 14px;  
            background-color: #8b5cf6;  
            color: white;  
            border: none;  
            border-radius: 6px;  
            font-weight: bold;  
            font-size: 12px;  
            cursor: pointer;  
            white-space: nowrap;  
            flex-shrink: 0;  
            transition: 0.2s;  
        }  
  
        .copy-btn.copied {  
            background-color: #10b981;  
        }  
  
        .footer {  
            text-align: center;  
            margin-top: 35px;  
            font-size: 12px;  
            color: #6b7280;  
        }  
    </style>  
</head>  
<body>  
  
    <header>  
        <h1>✨ FancyTextPro.com</h1>  
        <p>Unlimited 1000+ Stylish Fonts & Gamer Tags Generator</p>  
    </header>  
  
    <div class="container">  
  
        <!-- Top Ad Space -->  
        <div class="ad-box">  
            📢 Google AdSense Advertisement Banner  
        </div>  
  
        <!-- Text Input -->  
        <input type="text" id="userInput" class="input-box" placeholder="Type anything to generate 1000+ styles..." oninput="generateUnlimitedFonts()" value="Chaudhary">  
  
        <div id="counterBadge" class="counter-badge">Generating 1000+ Styles...</div>  
  
        <!-- Font Output Container -->  
        <div id="resultsList"></div>  
  
        <!-- Bottom Ad Space -->  
        <div class="ad-box" style="margin-top: 25px;">  
            📢 Google AdSense Advertisement Banner  
        </div>  
  
    </div>  
  
    <div class="footer">  
        © 2026 FancyTextPro.com | Unlimited Font Generator Engine  
    </div>  
  
    <script>  
        // Unicode character maps for heavy conversion  
        const alphabets = {  
            sansBold: {a:'𝗮',b:'𝗯',c:'𝗰',d:'𝗱',e:'𝗲',f:'𝗳',g:'𝗴',h:'𝗵',i:'𝗶',j:'𝗷',k:'𝗸',l:'𝗹',m:'𝗺',n:'𝗻',o:'𝗼',p:'𝗽',q:'𝗾',r:'𝗿',s:'𝘀',t:'𝘁',u:'𝘂',v:'𝘃',w:'𝘄',x:'𝘅',y:'𝘆',z:'𝘇',A:'𝗔',B:'𝗕',C:'𝗖',D:'𝗗',E:'𝗘',F:'𝗙',G:'𝗚',H:'𝗛',I:'𝗜',J:'𝗝',K:'𝗞',L:'𝗟',M:'𝗠',N:'𝗡',O:'𝗢',P:'𝗣',Q:'𝗤',R:'𝗥',S:'𝗦',T:'𝗧',U:'𝗨',V:'𝗩',W:'𝗪',X:'𝗫',Y:'𝗬',Z:'𝗭'},  
            script: {a:'𝒶',b:'𝒷',c:'𝒸',d:'𝒹',e:'ℯ',f:'𝒻',g:'ℊ',h:'𝒽',i:'𝒾',j:'𝒿',k:'𝓀',l:'𝓁',m:'𝓂',n:'𝓃',o:'ℴ',p:'𝓅',q:'𝓆',r:'𝓇',s:'𝓈',t:'𝓉',u:'𝓊',v:'𝒱',w:'𝓌',x:'𝒳',y:'𝓎',z:'𝒛',A:'𝒜',B:'ℬ',C:'𝒞',D:'𝒟',E:'ℰ',F:'ℱ',G:'𝒢',H:'ℋ',I:'ℐ',J:'𝒥',K:'𝒦',L:'ℒ',M:'ℳ',N:'𝒩',O:'𝒪',P:'𝒫',Q:'𝒬',R:'ℛ',S:'𝒮',T:'𝒯',U:'𝒰',V:'𝒱',W:'𝒲',X:'𝒳',Y:'𝒴',Z:'𝒵'},  
            fraktur: {a:'𝔞',b:'𝔟',c:'𝔠',d:'𝔡',e:'𝔢',f:'𝔣',g:'𝔤',h:'𝔥',i:'𝔦',j:'𝔧',k:'𝔨',l:'𝔩',m:'𝔪',n:'𝔫',o:'𝔬',p:'𝔭',q:'𝔮',r:'𝔯',s:'𝔰',t:'𝔱',u:'𝔲',v:'𝔳',w:'𝔴',x:'𝔵',y:'𝔶',z:'𝔷',A:'𝔄',B:'ℬ',C:'𝔭',D:'𝔇',E:'𝔈',F:'𝔉',G:'𝔊',H:'ℌ',I:'ℑ',J:'𝔍',K:'𝔎',L:'𝔏',M:'Ⓜ',N:'𝔑',O:'𝔒',P:'𝔓',Q:'𝔔',R:'ℜ',S:'𝔖',T:'𝔗',U:'𝔘',V:'𝔙',W:'𝔚',X:'𝔛',Y:'𝔜',Z:'ℨ'},  
            mono: {a:'𝚊',b:'𝚋',c:'𝚌',d:'𝚍',e:'𝚎',f:'𝚏',g:'𝚐',h:'𝚑',i:'𝚒',j:'𝚓',k:'𝚔',l:'𝚕',m:'𝚖',n:'𝚗',o:'𝚘',p:'𝚙',q:'𝚚',r:'𝚛',s:'𝚜',t:'𝚝',u:'𝚞',v:'𝚟',w:'𝚠',x:'𝚡',y:'𝚢',z:'𝚣',A:'𝙰',B:'𝙱',C:'𝙲',D:'𝙳',E:'𝙴',F:'𝙵',G:'𝙶',H:'𝙷',I:'𝙸',J:'𝙹',K:'𝙺',L:'𝙻',M:'𝙼',N:'𝙽',O:'𝙾',P:'𝙿',Q:'𝙌',R:'𝚁',S:'𝚂',T:'𝚃',U:'𝚄',V:'𝚅',W:'𝚆',X:'𝚇',Y:'𝚈',Z:'𝙹'},  
            circle: {a: 'ⓐ', b: 'ⓑ', c: 'ⓒ', d: 'ⓓ', e: 'ⓔ', f: 'ⓕ', g: 'ⓖ', h: 'ⓗ', i: 'ⓘ', j: 'ⓙ', k: 'ⓚ', l: 'ⓛ', m: 'ⓜ', n: 'ⓝ', o: 'ⓞ', p: 'ⓟ', q: 'ⓠ', r: 'ⓡ', s: 'ⓢ', t: 'ⓣ', u: 'ⓤ', v: 'ⓥ', w: 'ⓦ', x: 'ⓧ', y: 'ⓨ', z: 'ⓩ', A: 'Ⓐ', B: 'Ⓑ', C: 'Ⓒ', D: 'Ⓓ', E: 'Ⓔ', F: 'Ⓕ', G: 'Ⓖ', H: 'Ⓗ', I: 'Ⓘ', J: 'Ⓙ', K: 'Ⓚ', L: 'Ⓛ', M: 'Ⓜ', N: 'Ⓝ', O: 'Ⓞ', P: 'Ⓟ', Q: 'Ⓠ', R: 'Ⓡ', S: 'Ⓢ', T: 'Ⓣ', U: 'Ⓤ', V: '⒋', W: '⒌', X: '⒍', Y: '⒎', Z: '⒏'}  
        };  
  
        const prefixes = ["👑", "⚡", "🔥", "💎", "★", "꧁༺", "⚔️", "🎯", "🐉", "🚀", "💀", "💫", "💎", "🔥", "⚡", "👑", "💖", "🍁", "🐾", "🔮"];  
        const suffixes = ["👑", "⚡", "🔥", "💎", "★", "༻꧂", "⚔️", "🎯", "🐉", "🚀", "💀", "💫", "💎", "🔥", "⚡", "👑", "💖", "🍁", "🐾", "🔮"];  
        const midFrames = [" ⫷ ", " ⟅ ", " 【 ", " 〖 ", " 《 ", " ⦅ ", " ⟨ ", " ~*~ ", " -|- ", " *•. ", " ░ ", " ▒ ", " ▓ ", " █ "];  
  
        function convertText(text, map) {  
            return text.split('').map(c => map[c] || c).join('');  
        }  
  
        function generateUnlimitedFonts() {  
            let text = document.getElementById('userInput').value || "Chaudhary";  
            let resultsDiv = document.getElementById('resultsList');  
            resultsDiv.innerHTML = '';  
  
            let totalCount = 1050; // Total 1000+ styles target  
            let fragment = document.createDocumentFragment();  
  
            let baseStyles = [  
                { name: "Bold Sans", t: convertText(text, alphabets.sansBold) },  
                { name: "Cursive Script", t: convertText(text, alphabets.script) },  
                { name: "Gothic Fraktur", t: convertText(text, alphabets.fraktur) },  
                { name: "Monospace", t: convertText(text, alphabets.mono) },  
                { name: "Circled Letters", t: convertText(text, alphabets.circle) }  
            ];  
  
            let counter = 1;  
  
            // Loop to generate unlimited variations dynamically  
            while(counter <= totalCount) {  
                let p = prefixes[counter % prefixes.length];  
                let s = suffixes[counter % suffixes.length];  
                let m = midFrames[counter % midFrames.length];  
                let base = baseStyles[counter % baseStyles.length].t;  
  
                let generatedVal = `${p}${m}${base}${m.split('').reverse().join('')}${s}`;  
                if(counter % 7 === 0) generatedVal = `${p} ${text.toUpperCase()} ${s}`;  
                if(counter % 13 === 0) generatedVal = text.split('').join('̷');  
                if(counter % 19 === 0) generatedVal = text.split('').map(c => `[${c}]`).join('');  
  
                let card = document.createElement('div');  
                card.className = 'font-card';  
                card.innerHTML = `  
                    <div class="font-info">  
                        <div class="font-title">Style #${counter}</div>  
                        <div class="font-text">${generatedVal}</div>  
                    </div>  
                    <button class="copy-btn" onclick="copyText('${generatedVal.replace(/'/g, "\\'")}', this)">Copy</button>  
                `;  
                fragment.appendChild(card);  
                counter++;  
            }  
  
            resultsDiv.appendChild(fragment);  
            document.getElementById('counterBadge').innerText = `🔥 Generated ${totalCount}+ Unlimited Styles!`;  
        }  
  
        function copyText(text, btn) {  
            navigator.clipboard.writeText(text);  
            btn.innerText = "Copied! ✓";  
            btn.classList.add('copied');  
            setTimeout(() => {  
                btn.innerText = "Copy";  
                btn.classList.remove('copied');  
            }, 1200);  
        }  
  
        // Run on load  
        generateUnlimitedFonts();  
    </script>  
</body>  
</html>  
