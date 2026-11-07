
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#08091b">
<meta name="description" content="Parallel — A quiet story of kindness, memories, and two different paths.">
<title>Parallel — Somewhere in the Universe</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">

<style>
:root {
  --night: #08091b;
  --navy: #10132c;
  --purple: #29204b;
  --pink: #d9b6ed;
  --red: #ed526d;
  --white: #f5efff;
  --muted: #a7a4c1;
  --serif: 'Cormorant Garamond', serif;
  --sans: 'DM Sans', sans-serif;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
  scroll-padding-top: 75px;
}

body {
  background: var(--night);
  color: var(--white);
  font-family: var(--sans);
  font-weight: 300;
  overflow-x: hidden;
}

a {
  text-decoration: none;
  color: inherit;
}

button {
  font-family: inherit;
  cursor: pointer;
}

/* BACKGROUND */

#stars {
  position: fixed;
  inset: 0;
  z-index: -3;
  pointer-events: none;
  background:
    radial-gradient(ellipse at 20% 20%, rgba(68,44,112,.28), transparent 45%),
    radial-gradient(ellipse at 80% 65%, rgba(39,62,120,.22), transparent 45%),
    linear-gradient(150deg, #08091b, #11132b 50%, #17102e);
}

#stars::before {
  content: "";
  position: absolute;
  inset: 0;
  opacity: .65;
  background-image:
    radial-gradient(1px 1px at 10% 20%, white 99%, transparent),
    radial-gradient(1px 1px at 30% 70%, white 99%, transparent),
    radial-gradient(2px 2px at 70% 30%, #d9b6ed 99%, transparent),
    radial-gradient(1px 1px at 90% 80%, white 99%, transparent),
    radial-gradient(1px 1px at 55% 50%, white 99%, transparent),
    radial-gradient(2px 2px at 20% 90%, #edb7ce 99%, transparent);
  background-size: 250px 250px, 300px 300px,
    350px 350px, 200px 200px, 280px 280px, 400px 400px;
}

#stars::after {
  content: "";
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at center, transparent 20%, rgba(3,4,16,.5) 100%);
}

#meteor-layer {
  position: fixed;
  inset: 0;
  z-index: -1;
  pointer-events: none;
  overflow: hidden;
}

.meteor {
  position: absolute;
  width: 2px;
  height: 110px;
  background: linear-gradient(to bottom, transparent, #fff, #ed9fcb);
  transform: rotate(42deg);
  opacity: 0;
  animation: meteorFall 2.5s linear forwards;
  filter: drop-shadow(0 0 5px #d5a6ff);
}

@keyframes meteorFall {
  0% { opacity: 0; transform: translate(0,0) rotate(42deg); }
  10% { opacity: .9; }
  75% { opacity: .8; }
  100% { opacity: 0; transform: translate(-300px,500px) rotate(42deg); }
}

/* PRELOADER */

.preloader {
  position: fixed;
  inset: 0;
  background: #08091b;
  z-index: 9999;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  transition: opacity 1s, visibility 1s;
}

.preloader.hide {
  opacity: 0;
  visibility: hidden;
}

.preloader h1 {
  font-family: var(--serif);
  font-size: 58px;
  font-style: italic;
  font-weight: 300;
  color: var(--pink);
}

.preloader p {
  font-size: 9px;
  letter-spacing: 5px;
  margin-top: 12px;
  color: var(--muted);
}

/* NAVIGATION */

nav {
  position: fixed;
  top: 0;
  width: 100%;
  z-index: 100;
  padding: 17px 8%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  background: rgba(8,9,27,.75);
  backdrop-filter: blur(16px);
  border-bottom: 1px solid rgba(200,170,230,.1);
}

.logo {
  font-family: var(--serif);
  font-size: 29px;
  font-style: italic;
  color: var(--pink);
  letter-spacing: 1px;
}

.nav-links {
  display: flex;
  gap: 30px;
}

.nav-links a {
  font-size: 9px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--muted);
  transition: .3s;
}

.nav-links a:hover {
  color: white;
}

.menu-btn {
  display: none;
  background: none;
  border: 0;
  color: white;
  font-size: 24px;
}

/* HERO */

.hero {
  min-height: 92vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  text-align: center;
  padding: 110px 20px 75px;
  overflow: hidden;
  background: radial-gradient(ellipse at 50% 45%, rgba(89,67,143,.25), transparent 55%);
}

.hero-content {
  position: relative;
  z-index: 3;
  max-width: 850px;
  animation: fadeUp 2s ease both;
}

.eyebrow {
  font-size: 9px;
  letter-spacing: 6px;
  color: #bca7df;
  text-transform: uppercase;
  margin-bottom: 25px;
}

.hero h1 {
  font-family: var(--serif);
  font-size: clamp(85px, 15vw, 165px);
  line-height: .9;
  font-weight: 300;
  font-style: italic;
  color: #f2e7ff;
  text-shadow: 0 0 45px rgba(183,139,255,.35);
}

.hero-subtitle {
  font-family: var(--serif);
  font-size: clamp(20px, 3vw, 29px);
  font-style: italic;
  color: #cbb7e6;
  margin-top: 25px;
}

.hero-description {
  font-size: 9px;
  letter-spacing: 4px;
  color: #9290b2;
  margin-top: 17px;
}

.open-btn {
  display: inline-block;
  margin-top: 38px;
  padding: 13px 32px;
  border: 1px solid rgba(218,183,240,.6);
  color: #e9d8ff;
  font-size: 9px;
  letter-spacing: 3px;
  border-radius: 40px;
  transition: .4s;
}

.open-btn:hover {
  background: rgba(218,183,240,.15);
  box-shadow: 0 0 25px rgba(180,135,240,.2);
  transform: translateY(-4px);
}

.scroll-note {
  position: absolute;
  bottom: 25px;
  font-size: 9px;
  letter-spacing: 4px;
  color: #8c89ac;
}

/* RED THREAD */

.thread {
  position: absolute;
  width: 100%;
  height: 100%;
  inset: 0;
  z-index: 1;
  pointer-events: none;
  opacity: .75;
}

.thread path {
  fill: none;
  stroke: var(--red);
  stroke-width: 1.2;
  stroke-dasharray: 9 5;
  filter: drop-shadow(0 0 6px rgba(237,82,109,.8));
  animation: threadFlow 12s linear infinite;
}

@keyframes threadFlow {
  to { stroke-dashoffset: -150; }
}

.thread-dot {
  fill: #ff8298;
  filter: drop-shadow(0 0 8px #ff526e);
  animation: pulse 2s ease-in-out infinite alternate;
}

@keyframes pulse {
  to { opacity: .35; }
}

/* GENERAL SECTIONS */

section {
  padding: 75px 8%;
  position: relative;
}

.section-heading {
  text-align: center;
  margin-bottom: 35px;
}

.section-heading h2 {
  font-family: var(--serif);
  font-size: clamp(40px, 6vw, 62px);
  font-weight: 300;
  font-style: italic;
  color: #e9d8f9;
  margin-top: 10px;
}

.section-heading p {
  font-size: 11px;
  color: var(--muted);
  margin-top: 8px;
  letter-spacing: 1px;
}

/* INTRO */

.intro {
  background: linear-gradient(180deg, rgba(17,19,43,.9), rgba(17,14,39,.92));
}

.intro-content {
  max-width: 700px;
  margin: auto;
  text-align: center;
}

.intro-content p {
  font-family: var(--serif);
  font-size: 25px;
  line-height: 1.65;
  color: #c4bad7;
}

.intro-content .highlight {
  color: #e7c6d8;
  font-style: italic;
}

/* CHAPTERS */

.chapters {
  background: linear-gradient(180deg, rgba(17,14,39,.92), rgba(12,15,36,.94));
}

.chapter-list {
  max-width: 790px;
  margin: auto;
}

.chapter {
  display: grid;
  grid-template-columns: 1fr;
  gap: 8px;
  padding: 23px 12px;
  border-bottom: 1px solid rgba(200,170,230,.15);
  transition: .4s;
}

.chapter:hover {
  padding-left: 22px;
  border-color: rgba(237,82,109,.45);
}

.chapter-content h3 {
  font-family: var(--serif);
  font-size: 30px;
  color: #e5d3f5;
  font-weight: 400;
  margin-bottom: 7px;
}

.chapter-content p {
  font-size: 12px;
  color: #aaa4c3;
  line-height: 1.9;
}

/* HOPE */

.hope {
  background:
    radial-gradient(ellipse at 50% 50%, rgba(73,57,117,.3), transparent 65%),
    rgba(12,15,36,.8);
}

.hope-content {
  max-width: 780px;
  margin: auto;
  text-align: center;
  padding: 38px 35px;
  border: 1px solid rgba(199,164,230,.18);
  background: rgba(28,25,58,.35);
}

.hope-content p {
  font-family: var(--serif);
  font-size: 23px;
  line-height: 1.8;
  color: #c9bddb;
}

.hope-content em {
  color: #edb8d3;
}

/* MEMORY */

.memory {
  background:
    radial-gradient(ellipse at 50% 50%, rgba(64,45,105,.32), transparent 65%);
}

.memory-card {
  max-width: 760px;
  margin: auto;
  text-align: center;
  padding: 45px 45px;
  border: 1px solid rgba(199,164,230,.2);
  background: rgba(28,25,58,.45);
  backdrop-filter: blur(12px);
  box-shadow: 0 0 60px rgba(55,40,105,.15);
}

.memory-card h3 {
  font-family: var(--serif);
  font-size: 38px;
  font-style: italic;
  font-weight: 300;
  color: #e9cce9;
  margin-bottom: 17px;
}

.memory-card p {
  font-family: var(--serif);
  font-size: 23px;
  line-height: 1.75;
  color: #c0b4d1;
}

/* CONVERSATIONS */

.conversations {
  background: rgba(9,11,29,.7);
}

.conversation-content {
  max-width: 690px;
  margin: auto;
  text-align: center;
}

.conversation-content p {
  font-family: var(--serif);
  font-size: 25px;
  line-height: 1.75;
  color: #c6bbd9;
}

.conversation-content em {
  color: #edb8d3;
}

/* PATHS */

.paths {
  background:
    radial-gradient(ellipse at 50% 100%, rgba(85,51,116,.3), transparent 65%);
  text-align: center;
}

.paths-content {
  max-width: 700px;
  margin: auto;
}

.paths-content p {
  font-family: var(--serif);
  font-size: 24px;
  line-height: 1.75;
  color: #c4b8d6;
}

/* LETTER */

.letter-section {
  background: linear-gradient(180deg, rgba(14,14,37,.95), rgba(22,17,47,.95));
}

.letter-envelope {
  max-width: 550px;
  margin: auto;
  padding: 40px 35px;
  text-align: center;
  background: rgba(35,29,63,.65);
  border: 1px solid rgba(215,185,235,.25);
  box-shadow: 0 0 50px rgba(65,44,100,.2);
}

.stamp {
  font-size: 30px;
  color: #ed718c;
}

.letter-envelope h3 {
  font-family: var(--serif);
  font-size: 38px;
  font-weight: 300;
  font-style: italic;
  color: #e7d4f7;
  margin: 12px 0;
}

.letter-envelope > p {
  font-size: 11px;
  line-height: 2;
  color: #aaa4c3;
}

.letter-btn {
  margin-top: 25px;
  background: transparent;
  border: 1px solid rgba(225,174,201,.6);
  color: #f1d9e9;
  border-radius: 40px;
  padding: 12px 28px;
  font-size: 9px;
  letter-spacing: 2px;
  transition: .3s;
}

.letter-btn:hover {
  background: rgba(237,82,109,.15);
  border-color: var(--red);
}

.letter-content {
  display: none;
  margin-top: 25px;
  padding-top: 25px;
  border-top: 1px solid rgba(200,170,230,.2);
  animation: fadeUp .8s ease;
}

.letter-content.show {
  display: block;
}

.letter-content p {
  font-family: var(--serif);
  font-size: 21px;
  line-height: 1.8;
  color: #c8bdd9;
}

/* FINAL */

.final {
  min-height: 85vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  overflow: hidden;
  background:
    radial-gradient(ellipse at 50% 45%, rgba(105,71,147,.27), transparent 60%),
    linear-gradient(180deg, #11132c, #090a1d);
}

.final-content {
  max-width: 850px;
  position: relative;
  z-index: 2;
}

.final h2 {
  font-family: var(--serif);
  font-size: clamp(48px, 8vw, 85px);
  font-style: italic;
  font-weight: 300;
  color: #eadbfa;
  margin: 25px 0;
  text-shadow: 0 0 35px rgba(195,151,240,.3);
}

.final-quote {
  font-family: var(--serif);
  font-size: clamp(24px, 4vw, 36px);
  line-height: 1.6;
  color: #d3c2e8;
}

.final-note {
  font-family: var(--serif);
  font-style: italic;
  color: #f17b96;
  font-size: 25px;
  margin-top: 35px;
}

/* FOOTER */

footer {
  padding: 30px 20px;
  text-align: center;
  background: #08091b;
  border-top: 1px solid rgba(200,170,230,.1);
}

footer p {
  font-family: var(--serif);
  font-size: 27px;
  font-style: italic;
  color: #d6b9ed;
}

footer small {
  display: block;
  font-size: 9px;
  letter-spacing: 3px;
  color: #85819e;
  margin-top: 10px;
}

/* MUSIC STATUS */

.music-status {
  position: fixed;
  z-index: 200;
  bottom: 22px;
  right: 22px;
  display: flex;
  align-items: center;
  gap: 9px;
  background: rgba(22,19,48,.88);
  border: 1px solid rgba(214,178,236,.3);
  color: #e9d8f5;
  padding: 10px 15px;
  border-radius: 40px;
  backdrop-filter: blur(12px);
  font-size: 9px;
  letter-spacing: 1px;
  box-shadow: 0 0 25px rgba(70,40,100,.25);
}

.music-status.playing .music-icon {
  animation: musicPulse 1s infinite alternate;
}

.music-icon {
  font-size: 15px;
}

@keyframes musicPulse {
  to { transform: scale(1.3); }
}

/* REVEAL */

.reveal {
  opacity: 0;
  transform: translateY(25px);
  transition: opacity 1s ease, transform 1s ease;
}

.reveal.active {
  opacity: 1;
  transform: translateY(0);
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(25px); }
  to { opacity: 1; transform: translateY(0); }
}

/* RESPONSIVE */

@media(max-width: 768px) {
  nav {
    padding: 15px 6%;
  }

  .menu-btn {
    display: block;
  }

  .nav-links {
    display: none;
    position: absolute;
    top: 60px;
    left: 0;
    width: 100%;
    background: rgba(10,11,30,.97);
    padding: 22px;
    flex-direction: column;
    gap: 22px;
    border-bottom: 1px solid rgba(200,170,230,.15);
  }

  .nav-links.open {
    display: flex;
  }

  section {
    padding: 65px 7%;
  }

  .hero {
    min-height: 90vh;
  }

  .chapter {
    padding: 20px 4px;
  }

  .chapter-content h3 {
    font-size: 26px;
  }

  .memory-card,
  .hope-content {
    padding: 30px 22px;
  }

  .memory-card p,
  .intro-content p,
  .conversation-content p,
  .paths-content p,
  .hope-content p {
    font-size: 21px;
  }

  .letter-envelope {
    padding: 35px 22px;
  }

  .music-status {
    bottom: 14px;
    right: 14px;
  }
}

@media(prefers-reduced-motion: reduce) {
  *, *::before, *::after {
    animation-duration: .01ms !important;
    transition-duration: .01ms !important;
    scroll-behavior: auto !important;
  }
}
</style>
</head>

<body>

<div id="stars"></div>
<div id="meteor-layer"></div>

<!-- PRELOADER -->

<div class="preloader" id="preloader">
  <h1>Parallel</h1>
  <p>UNDER THE SAME SKY</p>
</div>

<!-- MUSIC -->

<audio id="bgMusic" src="sparkle.mp3" autoplay loop preload="auto"></audio>

<div class="music-status" id="musicStatus">
  <span class="music-icon" id="musicIcon">♫</span>
  <span id="musicText">MUSIC</span>
</div>

<!-- NAVIGATION -->

<nav>
  <a href="#home" class="logo">parallel.</a>

  <button class="menu-btn" id="menuBtn" aria-label="Open menu" aria-expanded="false">☰</button>

  <div class="nav-links" id="navLinks">
    <a href="#home">Home</a>
    <a href="#beginning">Our Story</a>
    <a href="#memories">Memories</a>
    <a href="#letter">A Letter</a>
    <a href="#ending">Somewhere</a>
  </div>
</nav>

<!-- HERO -->

<header class="hero" id="home">

  <svg class="thread" viewBox="0 0 1440 900" preserveAspectRatio="none">
    <path d="M-100 720 C200 300, 400 950, 720 450 S1150 100, 1550 500"/>
    <path d="M-100 250 C250 600, 550 50, 850 420 S1200 800, 1550 200"
          opacity=".35" stroke-width=".7"/>
    <circle class="thread-dot" cx="720" cy="450" r="4"/>
  </svg>

  <div class="hero-content">
    <div class="eyebrow">A STORY WRITTEN UNDER THE STARS</div>

    <h1>Parallel</h1>

    <p class="hero-subtitle">
      Two paths. One universe. Different journeys.
    </p>

    <p class="hero-description">
      KINDNESS · MEMORIES · DISTANCE · TIME
    </p>

    <a href="#beginning" class="open-btn">
      EXPLORE THE STORY &nbsp; ↓
    </a>
  </div>

  <div class="scroll-note">
    SOMEWHERE UNDER THE SAME SKY
  </div>
</header>

<!-- INTRO -->

<section class="intro reveal" id="beginning">

  <div class="section-heading">
    <h2>Before the story begins</h2>
  </div>

  <div class="intro-content">
    <p>
      Some people enter our lives quietly.
      They don't always stay beside us,
      but somehow, their kindness remains.
    </p>

    <br>

    <p class="highlight">
      This is a little story about two people,
      their conversations, the kindness they shared,
      and the moments that became part of a memory.
    </p>
  </div>

</section>

<!-- CHAPTERS -->

<section class="chapters reveal">

  <div class="section-heading">
    <h2>The Chapters</h2>
    <p>Every little part has its own meaning.</p>
  </div>

  <div class="chapter-list">

    <article class="chapter">
      <div class="chapter-content">
        <h3>How It All Began</h3>
        <p>
          At first, Minji was simply someone I knew from afar.
          Someone who seemed cool, popular, thoughtful,
          and wise in his own way.
          I never imagined that one day,
          we would become part of each other's stories.
        </p>
      </div>
    </article>

    <article class="chapter">
      <div class="chapter-content">
        <h3>A Little Unexpected</h3>
        <p>
          One day, he reached out and started a conversation.
          I never expected to discover that he had feelings for me.
          I wasn't ready for a relationship back then,
          so we chose to remain friends.
        </p>
      </div>
    </article>

    <article class="chapter">
      <div class="chapter-content">
        <h3>The Kindness I Remember</h3>
        <p>
          What stayed with me was his kindness.
          He was someone who cared, supported me,
          and believed in me when I needed it.
          Even the little things he did
          became something meaningful to remember.
        </p>
      </div>
    </article>

    <article class="chapter">
      <div class="chapter-content">
        <h3>When I Felt Lost</h3>
        <p>
          There were moments when life felt heavier than usual,
          when hope seemed difficult to find.
          Yet, somewhere in those difficult days,
          I began to understand that even the smallest kindness
          could make a difference.
        </p>
      </div>
    </article>

    <article class="chapter">
      <div class="chapter-content">
        <h3>Conversations Beyond Words</h3>
        <p>
          We didn't talk every day.
          Our conversations were rare,
          but whenever we did talk,
          there was always something meaningful to take away.
        </p>
      </div>
    </article>

    <article class="chapter">
      <div class="chapter-content">
        <h3>Different Paths</h3>
        <p>
          Life eventually took us in different directions.
          Some chapters came to an end,
          and many memories are no longer there to revisit.
          What remains are the things I still remember
          and the kindness I will always appreciate.
        </p>
      </div>
    </article>

  </div>
</section>

<!-- HOPE -->

<section class="hope reveal">

  <div class="section-heading">
    <h2>Where Hope Finds Its Way</h2>
  </div>

  <div class="hope-content">
    <p>
      The magical thing about hope is that it often flourishes
      at the edge of despair, in places like hospital waiting rooms
      and refugee camps. Like wildflowers growing in the most barren
      soil, as if God had deliberately placed them there to remind
      humanity of its true nature.
    </p>

    <br>

    <p>
      Yet, the New Year is where hope grows like an anomaly,
      surrounded by celebrations and bursts of fireworks.
      And as I watched the seconds slowly move toward the beginning
      of a new year, I came to realize something.
    </p>

    <br>

    <p>
      Perhaps hope is also humanity's victory over uncertainty.
      And just like every victory, <em>hope deserves to be celebrated.</em>
    </p>
  </div>

</section>

<!-- MEMORIES -->

<section class="memory reveal" id="memories">

  <div class="section-heading">
    <h2>Little Things That Matter</h2>
  </div>

  <div class="memory-card">
    <h3>To the little things...</h3>

    <p>
      The times you helped me with something,
      the moments you listened,
      the way you read my writings,
      and the way you responded
      when I needed someone to believe in me.
    </p>

    <br>

    <p>
      Maybe they seemed like ordinary things to you.
      But they became little pieces of kindness
      that I will always carry with me.
    </p>
  </div>

</section>

<!-- CONVERSATIONS -->

<section class="conversations reveal">

  <div class="section-heading">
    <h2>Beyond Conversations</h2>
  </div>

  <div class="conversation-content">
    <p>
      We didn't need to talk every day.
      We rarely had long conversations.
      But somehow, every time we talked,
      <em>our conversations always felt extraordinary.</em>
    </p>

    <br>

    <p>
      Some conversations may be short,
      but the thoughts they leave behind
      can stay with us for a long time.
    </p>
  </div>

</section>

<!-- DIFFERENT PATHS -->

<section class="paths reveal">

  <div class="section-heading">
    <h2>Different Paths</h2>
  </div>

  <div class="paths-content">
    <p>
      I know we are living our own lives now.
      We have our own responsibilities,
      dreams, and places to reach.
    </p>

    <br>

    <p>
      I don't know where life will take us.
      Maybe our paths will cross someday,
      maybe they will continue in different directions.
      But I hope that wherever you are,
      life continues to be kind to you.
    </p>
  </div>

</section>

<!-- LETTER -->

<section class="letter-section reveal" id="letter">

  <div class="section-heading">
    <h2>Dear Minji,</h2>
  </div>

  <div class="letter-envelope">

    <div class="stamp">♡</div>

    <h3>A little letter for you</h3>

    <p>
      Some words deserve a quiet place
      to be remembered.
    </p>

    <button class="letter-btn" id="letterBtn" aria-expanded="false">
      OPEN THIS LETTER
    </button>

    <div class="letter-content" id="letterContent">

      <p>
        Thank you for being kind to me.
        Thank you for believing in me,
        for caring in your own way,
        and for being a light during a time
        when I needed one.
      </p>

      <br>

      <p>
        I hope life brings you beautiful things.
        I hope you keep growing,
        finding happiness,
        and becoming everything you wish to be.
      </p>

      <br>

      <p>
        Wherever life takes us,
        I will always wish you well.
      </p>

      <br>

      <p style="font-style:italic;color:#ed9bb7">
        With warmth,<br>
        Nasywa.
      </p>

    </div>
  </div>
</section>

<!-- ENDING -->

<section class="final reveal" id="ending">

  <svg class="thread" viewBox="0 0 1440 900" preserveAspectRatio="none">
    <path d="M-100 700 C250 200, 450 900, 730 440 S1100 100, 1500 650"/>
  </svg>

  <div class="final-content">

    <div class="eyebrow">
      TWO LIVES, TWO DIFFERENT DIRECTIONS
    </div>

    <h2>Somewhere, Someday</h2>

    <p class="final-quote">
      "Maybe we are not walking on the same path right now,
      but I hope someday life will be kind enough
      to bring us together."
    </p>

    <p class="final-note">
      Just a quiet thought, somewhere in the universe.
    </p>

    <p style="margin-top:40px;font-size:9px;letter-spacing:4px;color:#aaa0c4;">
      UNDER THE SAME SKY, SOMEWHERE IN THIS UNIVERSE.
    </p>

  </div>
</section>

<footer>
  <p>Parallel.</p>
  <small>TWO PATHS · ONE UNIVERSE · DIFFERENT JOURNEYS</small>
  <small>© 2026 — MADE WITH LOVE</small>
</footer>

<script>

/* PRELOADER */

window.addEventListener("load", () => {
  setTimeout(() => {
    document.getElementById("preloader").classList.add("hide");
  }, 900);
});

/* MOBILE MENU */

const menuBtn = document.getElementById("menuBtn");
const navLinks = document.getElementById("navLinks");

menuBtn.addEventListener("click", () => {
  const isOpen = navLinks.classList.toggle("open");
  menuBtn.setAttribute("aria-expanded", isOpen);
  menuBtn.textContent = isOpen ? "×" : "☰";
});

document.querySelectorAll(".nav-links a").forEach(link => {
  link.addEventListener("click", () => {
    navLinks.classList.remove("open");
    menuBtn.setAttribute("aria-expanded", "false");
    menuBtn.textContent = "☰";
  });
});

/* AUTOMATIC BACKGROUND MUSIC */

const bgMusic = document.getElementById("bgMusic");
const musicStatus = document.getElementById("musicStatus");
const musicIcon = document.getElementById("musicIcon");
const musicText = document.getElementById("musicText");

bgMusic.volume = 0.45;

function updateMusicStatus() {
  if (!bgMusic.paused) {
    musicStatus.classList.add("playing");
    musicIcon.textContent = "♫";
    musicText.textContent = "NOW PLAYING";
  } else {
    musicStatus.classList.remove("playing");
    musicIcon.textContent = "♪";
    musicText.textContent = "MUSIC PAUSED";
  }
}

async function attemptAutoplay() {
  try {
    await bgMusic.play();
    updateMusicStatus();
  } catch (error) {
    musicStatus.classList.remove("playing");
    musicIcon.textContent = "♪";
    musicText.textContent = "MUSIC BLOCKED";
  }
}

window.addEventListener("load", attemptAutoplay);
bgMusic.addEventListener("play", updateMusicStatus);
bgMusic.addEventListener("pause", updateMusicStatus);

/* LETTER */

const letterBtn = document.getElementById("letterBtn");
const letterContent = document.getElementById("letterContent");

letterBtn.addEventListener("click", () => {
  const isOpen = letterContent.classList.toggle("show");

  letterBtn.textContent = isOpen
    ? "CLOSE THIS LETTER"
    : "OPEN THIS LETTER";

  letterBtn.setAttribute("aria-expanded", isOpen);
});

/* SCROLL REVEAL */

const observer = new IntersectionObserver(entries => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add("active");
    }
  });
}, {
  threshold: 0.12
});

document.querySelectorAll(".reveal").forEach(section => {
  observer.observe(section);
});

/* METEOR SHOWER */

function createMeteor() {
  if (document.hidden) return;

  const meteor = document.createElement("div");
  meteor.className = "meteor";

  meteor.style.left = (20 + Math.random() * 90) + "%";
  meteor.style.top = (Math.random() * 40) + "%";

  document.getElementById("meteor-layer").appendChild(meteor);

  setTimeout(() => meteor.remove(), 3000);
}

setInterval(createMeteor, 1800);

/* PAUSE DECORATIVE EFFECTS WHEN TAB IS HIDDEN */

document.addEventListener("visibilitychange", () => {
  document.getElementById("meteor-layer").style.display =
    document.hidden ? "none" : "block";
});

</script>

</body>
</html>
