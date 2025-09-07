###

<!-- Inline SVG banner (no <img> tag) -->
<p align="center">
<svg width="100%" viewBox="0 0 1600 420" xmlns="http://www.w3.org/2000/svg" role="img" aria-labelledby="title desc">
  <title id="title">Full-Stack & Blockchain Engineer — 3D Neon Banner</title>
  <desc id="desc">Animated neon hex grid with isometric cubes and blockchain-themed title rendered via SVG paths and gradients.</desc>

  <defs>
    <!-- Deep-space animated background -->
    <linearGradient id="bgGrad" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0%" stop-color="#0a0f1f">
        <animate attributeName="stop-color" values="#0a0f1f;#0b0e2b;#0a0f1f" dur="14s" repeatCount="indefinite"/>
      </stop>
      <stop offset="100%" stop-color="#101a33">
        <animate attributeName="stop-color" values="#101a33;#131f45;#101a33" dur="14s" repeatCount="indefinite"/>
      </stop>
    </linearGradient>

    <!-- Aurora haze -->
    <radialGradient id="aurora" cx="30%" cy="25%" r="80%">
      <stop offset="0%" stop-color="#4dd0e1" stop-opacity="0.42">
        <animate attributeName="stop-color" values="#4dd0e1;#7c4dff;#00e5ff;#4dd0e1" dur="18s" repeatCount="indefinite"/>
      </stop>
      <stop offset="60%" stop-color="#000" stop-opacity="0"/>
      <stop offset="100%" stop-color="#000" stop-opacity="0"/>
    </radialGradient>

    <!-- Hex grid pattern (built from a path) -->
    <pattern id="hexGrid" width="60" height="34.64" patternUnits="userSpaceOnUse" patternTransform="skewX(-20)">
      <!-- Hexagon as a single path -->
      <path d="M0,17.32 L15,0 L45,0 L60,17.32 L45,34.64 L15,34.64 Z"
            fill="none" stroke="#66fff5" stroke-opacity="0.06" stroke-width="1"/>
    </pattern>

    <!-- Neon glow filter -->
    <filter id="neon">
      <feGaussianBlur in="SourceGraphic" stdDeviation="2.5" result="b1"/>
      <feGaussianBlur in="SourceGraphic" stdDeviation="6" result="b2"/>
      <feMerge>
        <feMergeNode in="b2"/>
        <feMergeNode in="b1"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>

    <!-- Moving sheen mask across title -->
    <linearGradient id="sheenGrad" x1="0" y1="0" x2="1" y2="0">
      <stop offset="0" stop-color="white" stop-opacity="0"/>
      <stop offset="0.5" stop-color="white" stop-opacity="0.9"/>
      <stop offset="1" stop-color="white" stop-opacity="0"/>
    </linearGradient>
    <mask id="sheenMask">
      <rect id="sheenRect" x="-40%" y="0" width="40%" height="100%" fill="url(#sheenGrad)">
        <animate attributeName="x" values="-40%;140%" dur="6s" repeatCount="indefinite"/>
      </rect>
    </mask>

    <!-- Isometric cube faces (gradients) -->
    <linearGradient id="cubeTop" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0" stop-color="#6ff"/>
      <stop offset="1" stop-color="#2af"/>
    </linearGradient>
    <linearGradient id="cubeLeft" x1="1" y1="0" x2="0" y2="1">
      <stop offset="0" stop-color="#0cf"/>
      <stop offset="1" stop-color="#058"/>
    </linearGradient>
    <linearGradient id="cubeRight" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0" stop-color="#38f"/>
      <stop offset="1" stop-color="#0af"/>
    </linearGradient>
  </defs>

  <!-- BACKGROUND -->
  <rect width="1600" height="420" fill="url(#bgGrad)"/>
  <rect width="1600" height="420" fill="url(#aurora)">
    <animateTransform attributeName="transform" type="translate" values="0 0; -40 -12; 0 0" dur="20s" repeatCount="indefinite"/>
  </rect>

  <!-- HEX GRID (parallax) -->
  <g opacity="0.85">
    <rect width="1600" height="420" fill="url(#hexGrid)"/>
    <g opacity="0.28">
      <rect width="1600" height="420" fill="url(#hexGrid)">
        <animateTransform attributeName="transform" type="translate" values="0,0; 22,12; 0,0" dur="16s" repeatCount="indefinite"/>
      </rect>
    </g>
  </g>

  <!-- FLOATING ISO CUBES made purely with <path> -->
  <!-- Cube helper: three faces from a central top rhombus -->
  <g opacity="0.9" filter="url(#neon)">
    <!-- Cube 1 -->
    <g transform="translate(260 300)">
      <!-- top -->
      <path d="M0,-40 L40,-20 L0,0 L-40,-20 Z" fill="url(#cubeTop)"/>
      <!-- left -->
      <path d="M-40,-20 L0,0 L0,38 L-40,18 Z" fill="url(#cubeLeft)"/>
      <!-- right -->
      <path d="M40,-20 L0,0 L0,38 L40,18 Z" fill="url(#cubeRight)"/>
      <!-- subtle shimmer -->
      <path d="M-25,-22 L0,-10 L0,8 L-25,-4 Z" fill="#fff" opacity="0.08"/>
    </g>

    <!-- Cube 2 -->
    <g transform="translate(1340 120) scale(0.9)">
      <path d="M0,-40 L40,-20 L0,0 L-40,-20 Z" fill="url(#cubeTop)"/>
      <path d="M-40,-20 L0,0 L0,38 L-40,18 Z" fill="url(#cubeLeft)"/>
      <path d="M40,-20 L0,0 L0,38 L40,18 Z" fill="url(#cubeRight)"/>
      <path d="M-25,-22 L0,-10 L0,8 L-25,-4 Z" fill="#fff" opacity="0.08"/>
    </g>

    <!-- Cube 3 -->
    <g transform="translate(980 280) scale(1.1)">
      <path d="M0,-40 L40,-20 L0,0 L-40,-20 Z" fill="url(#cubeTop)"/>
      <path d="M-40,-20 L0,0 L0,38 L-40,18 Z" fill="url(#cubeLeft)"/>
      <path d="M40,-20 L0,0 L0,38 L40,18 Z" fill="url(#cubeRight)"/>
      <path d="M-25,-22 L0,-10 L0,8 L-25,-4 Z" fill="#fff" opacity="0.08"/>
    </g>
  </g>

  <!-- TITLE (neon) -->
  <g filter="url(#neon)">
    <!-- Outline via path text conversion alternative: we’ll use <text> for brevity;
         if you need paths only, tell me and I’ll provide a converted path set. -->
    <text x="50%" y="52%" text-anchor="middle"
          font-family="Poppins, Segoe UI, Roboto, Helvetica, Arial, sans-serif"
          font-size="54" letter-spacing="2"
          fill="#b3fff7" stroke="#61f7ff" stroke-width="0.6">
      FULL-STACK & BLOCKCHAIN ENGINEER
    </text>

    <!-- Sheen overlay using mask -->
    <g mask="url(#sheenMask)">
      <text x="50%" y="52%" text-anchor="middle"
            font-family="Poppins, Segoe UI, Roboto, Helvetica, Arial, sans-serif"
            font-size="54" letter-spacing="2" fill="white" opacity="0.9">
        FULL-STACK & BLOCKCHAIN ENGINEER
      </text>
    </g>
  </g>

  <!-- SUBTITLE STACK CHIPS -->
  <g font-family="Inter, Segoe UI, Roboto, Helvetica, Arial, sans-serif"
     font-size="20" fill="#9fdcff" opacity="0.92">
    <text x="50%" y="72%" text-anchor="middle" letter-spacing="3">
      Sui • Solana • Move • Anchor • Foundry • DeFi • NFTs • Walrus • SEAL • Smart Contracts • Wallets
    </text>
  </g>

  <!-- HANDLE -->
  <g font-family="Inter, Segoe UI, Roboto, Helvetica, Arial, sans-serif" font-size="18" fill="#73e8ff" opacity="0.9">
    <text x="50%" y="88%" text-anchor="middle">@CuteCoder-Cat</text>
  </g>
</svg>
</p>


<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=CuteCoder-Cat&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=en&hide_border=false" height="150" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=CuteCoder-Cat&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=5&theme=dracula&hide_border=false" height="150" alt="languages graph"  />
</div>

<h2 font-weight="bold">❄ᗩ𝒷𝑜𝓊𝓉 ൱𝑒</h2>

###
<p align="left">  
𝐈’𝐦 𝐚 𝐛𝐥𝐨𝐜𝐤𝐜𝐡𝐚𝐢𝐧 𝐝𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐫 𝐬𝐩𝐞𝐜𝐢𝐚𝐥𝐢𝐳𝐢𝐧𝐠 𝐢𝐧 𝐒𝐮𝐢 𝐚𝐧𝐝 𝐒𝐨𝐥𝐚𝐧𝐚, 𝐰𝐢𝐭𝐡 𝐞𝐱𝐭𝐞𝐧𝐬𝐢𝐯𝐞 𝐞𝐱𝐩𝐞𝐫𝐢𝐞𝐧𝐜𝐞 𝐛𝐮𝐢𝐥𝐝𝐢𝐧𝐠 𝐍𝐅𝐓 𝐠𝐚𝐦𝐞𝐬, 𝐦𝐚𝐫𝐤𝐞𝐭𝐩𝐥𝐚𝐜𝐞𝐬, 𝐃𝐞𝐟𝐢 𝐚𝐧𝐝 𝐞𝐯𝐞𝐧 𝐢𝐧𝐭𝐞𝐠𝐫𝐚𝐭𝐢𝐧𝐠 𝐦𝐞𝐭𝐚𝐯𝐞𝐫𝐬𝐞 𝐟𝐞𝐚𝐭𝐮𝐫𝐞𝐬.<br>
𝐈 𝐭𝐫𝐮𝐥𝐲 𝐛𝐞𝐥𝐢𝐞𝐯𝐞 𝐭𝐡𝐚𝐭 𝐚 𝐬𝐤𝐢𝐥𝐥𝐞𝐝 𝐝𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐫 𝐥𝐢𝐤𝐞 𝐦𝐲𝐬𝐞𝐥𝐟 𝐜𝐚𝐧 𝐛𝐫𝐢𝐧𝐠 𝐫𝐞𝐚𝐥 𝐯𝐚𝐥𝐮𝐞 𝐭𝐨 𝐲𝐨𝐮𝐫 𝐩𝐫𝐨𝐣𝐞𝐜𝐭.<br>
𝐈𝐟 𝐭𝐡𝐞𝐫𝐞 𝐚𝐫𝐞 𝐚𝐧𝐲 𝐨𝐩𝐞𝐧𝐢𝐧𝐠 𝐝𝐞𝐯 𝐩𝐨𝐬𝐢𝐭𝐢𝐨𝐧 𝐢𝐧 𝐭𝐡𝐢𝐬 𝐩𝐫𝐨𝐣𝐞𝐜𝐭, 𝐈’𝐝 𝐥𝐨𝐯𝐞 𝐭𝐨 𝐜𝐨𝐥𝐥𝐚𝐛𝐨𝐫𝐚𝐭𝐞 𝐚𝐧𝐝 𝐜𝐫𝐞𝐚𝐭𝐞 𝐬𝐨𝐦𝐞𝐭𝐡𝐢𝐧𝐠 𝐚𝐦𝐚𝐳𝐢𝐧𝐠 𝐭𝐨𝐠𝐞𝐭𝐡𝐞𝐫.<br>
𝐋𝐨𝐨𝐤𝐢𝐧𝐠 𝐟𝐨𝐫𝐰𝐚𝐫𝐝 𝐭𝐨 𝐡𝐞𝐚𝐫𝐢𝐧𝐠 𝐟𝐫𝐨𝐦 𝐲𝐨𝐮!
</p>
###
<div align="center">
  <img src="https://github-profile-trophy.vercel.app?username=CuteCoder-Cat&theme=dracula&column=-1&row=1&margin-w=8&margin-h=8&no-bg=false&no-frame=false&order=4" height="150" alt="trophy graph"  />
</div>

<h2 font-weight="bold">🌠Ꚃ𝓀𝒾𝓁𝓁𝓈</h2>

###

<table align="center">
<tr>
    <td align="center" width="90">
      <img src="https://github.com/kroim/profile/blob/master/icons/icon_nft.png?raw=true" height="45" >
      <br>NFT
    </td>
    <td align="center" width="90">
      <img src="https://github.com/kroim/profile/blob/master/icons/icon_defi.png?raw=true" height="45" >
      <br>DeFi
    </td>
    <td align="center" width="90">
      <img src="https://s2.coinmarketcap.com/static/img/coins/64x64/1027.png" width="48" height="48" alt="Ethereum" />
      <br>Ethereum
    </td>
    <td align="center" width="90">
      <img src="https://s2.coinmarketcap.com/static/img/coins/64x64/5426.png" width="48" height="48" style="border-radius: 15px;" alt="Solana" />
      <br>Solana
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=solidity" width="45" height="45" alt="Solidity" />
      <br>Solidity
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=rust" width="45" height="45" alt="Rust" />
      <br>Rust
    </td>
    <td align="center" width="90">
      <img src="./anchor.png" alt="Anchor" width="55" height="55" />
      <br>Anchor
    </td>
    <td align="center" width="90">
      <img src="./foundry.png" alt="icon" width="55" height="55" />
      <br>Foundry
    </td>
    <td align="center" width="90">
      <img src="./hardhat.svg" alt="HardHat" width="55" height="55" />
      <br>HardHat
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=rails" width="45" height="45" alt="rails" />
      <br>Rails
    </td>
  </tr>
  <tr>
    <td align="center" width="90">
      <img src="https://techstack-generator.vercel.app/react-icon.svg" alt="icon" width="55" height="55" />
      <br>React
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=nextjs" width="45" height="45" alt="Next.js" />
      <br>Next.js
    </td>
    <td align="center" width="90">
      <img src="https://techstack-generator.vercel.app/react-icon.svg" alt="icon" width="55" height="55" />
      <br>React Native
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=nuxtjs" width="45" height="45" alt="Nuxt.js" />
      <br>Nuxt.js
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=angular" width="45" height="45" alt="Angular" />
      <br>Angular
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=svelte" width="45" height="45" alt="Svelte" />
      <br>Svelte
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=tailwind" width="45" height="45" alt="Tailwind" />
      <br>Tailwind
    </td>
    <td align="center" width="90">
        <img src="https://techstack-generator.vercel.app/graphql-icon.svg" width="48" height="48" alt="GraphQL" />
      <br>GraphQL
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=threejs" width="45" height="45" alt="Three.js" />
      <br>Three.js
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=androidstudio" width="45" height="45" alt="AndroidStudio" />
      <br>Android
    </td>
  </tr>
  <tr>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=ruby" width="45" height="45" alt="Ruby" />
      <br>Ruby
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=go" title="GoLang" alt="GoLang " width="45" height="45"/>
      <br>GoLang
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=express" width="45" height="45" alt="Express" />
      <br>Express
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=nestjs" width="45" height="45" alt="Nest.js" />
      <br>Nest.js
    </td>
    <td align="center" width="90">
      <img src="https://techstack-generator.vercel.app/django-icon.svg" alt="icon" width="55" height="55" />
      <br>Django
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=laravel" width="45" height="45" alt="Laravel" />
      <br>Laravel
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=flutter" width="45" height="45" alt="Flutter" />
      <br>Flutter
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=mongodb" width="45" height="45" alt="MongoDB" />
      <br>MongoDB
    </td>
    <td align="center" width="90">
      <img src="https://skillicons.dev/icons?i=postgres" width="45" height="45" alt="PostgreSQL" />
      <br>PostgreSQL
    </td>
    <td align="center" width="90">
      <img src="https://techstack-generator.vercel.app/python-icon.svg" alt="icon" width="55" height="55" />
      <br>Python
    </td>
  </tr>
</table>
<br/>

<h2 font-weight="bold">✨ᑕ𝑜𝓃𝓉𝒶𝒸𝓉</h2>

###
<div align="center">
  <img src="https://img.shields.io/static/v1?message=Discord&logo=discord&label=&color=7289DA&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="discord logo"  />
  <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=D14836&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="gmail logo"  />
  <img src="https://img.shields.io/static/v1?message=Telegram&logo=telegram&label=&color=2CA5E0&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="telegram logo"  />
  <img src="https://img.shields.io/static/v1?message=Slack&logo=slack&label=&color=4A154B&logoColor=white&labelColor=&style=for-the-badge" height="25" alt="slack logo"  />
</div>
