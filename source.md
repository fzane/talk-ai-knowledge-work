---
marp: true
size: 16:9
paginate: false
backgroundColor: "#a0a0a0"   # parchment yellow
/* backgroundColor: #ffffff */
style: |
  /* ===== Global full-bleed canvas with simple, modular primitives ===== */
  section {
    padding: 0 !important;
    margin: 0 !important;
    font-family: system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, sans-serif;
    color: #111;
  }
  .slide-canvas {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    overflow: hidden;
    box-sizing: border-box;
  }
  .bg-img {
    position: absolute;
    inset: 0;
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  /* Primitive blocks (appearance only; no per-slide positioning here) */
  .QuoteCard {
    position: absolute; /* Positioned per-slide in local <style> */
    max-width: 58%;
    padding: 14px 18px;
    background: #fff;
    border: 2px solid #222;
    box-shadow: none !important;   /* No shadows per request */
    color: #111;
    box-sizing: border-box;
    /* 'Ripped paper' feel via rough-ish edges */
    clip-path: polygon(
      2% 0%, 98% 0%, 100% 8%, 98% 16%, 100% 28%, 98% 40%,
      100% 52%, 98% 64%, 100% 76%, 98% 88%, 98% 100%,
      2% 100%, 0% 92%, 2% 84%, 0% 72%, 2% 60%, 0% 48%,
      2% 36%, 0% 24%, 2% 12%, 0% 4%
    );
  }
  .quote-text { font-family: Georgia, 'Times New Roman', serif; font-size: 24px; line-height: 1.25; }
  .quote-cite { margin-top: 8px; font-size: 16px; letter-spacing: .2px; }

  .ScrimBox {
    position: absolute; /* Positioned per-slide */
    padding: 18px 22px;
    background: rgba(0,0,0,0.58);
    color: #fff;
    border: 2px solid #fff;
    box-shadow: none !important;
    box-sizing: border-box;
  }

  .LargeText {
    position: absolute; /* Positioned per-slide */
    font-weight: 800;
    font-size: 84px;
    line-height: 1.05;
    letter-spacing: -0.5px;
    text-wrap: balance;
  }

  .TaskCard, .DocCard, .JobCard, .Callout, .Bubble, .Badge {
    position: absolute; /* Positioned per-slide */
    background: #fff;
    border: 2px solid #222;
    box-shadow: none !important;
    padding: 14px 16px;
    box-sizing: border-box;
  }
  .TaskCard { font-size: 24px; }
  .DocCard  { font-size: 22px; }
  .JobCard  { font-size: 22px; }
  .Callout  { font-size: 24px; background: #f6f6f6; }
  .Bubble   { background: #fff; border-radius: 12px; }
  .Badge    { font-weight: 700; padding: 6px 10px; border-radius: 8px; background: #111; color: #fff; }

  .strike { text-decoration: line-through; }
  .mono   { font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace; }

    /* === Section dividers: dark background + extra-bold white type === */
    .slide-canvas.s-sec1,
    .slide-canvas.s-sec2,
    .slide-canvas.s-sec3 {
    background-color: #0f1115 !important;   /* full-bleed dark */
    }

    .slide-canvas.s-sec1 .LargeText,
    .slide-canvas.s-sec2 .LargeText,
    .slide-canvas.s-sec3 .LargeText {
    color: #fff;
    font-weight: 900;                        /* much thicker */
    /* If your font supports variable weights, this helps too: */
    font-variation-settings: "wght" 950;
    font-size: 110px;
    letter-spacing: -1px;
    line-height: 1.02;
    }

---

<style>
  .s-sec1 .LargeText { left: 50%; top: 50%; transform: translate(-50%,-50%); text-align: center; }
</style>
<div class="slide-canvas s-sec1">
  <div class="LargeText">Knowledge Work Is Changing</div>
</div>

<!--
Setting The Stage
(Section divider slide)
-->

---

<style>
  .s-news .q1 { left: 6%;  top: 10%; transform: rotate(-6deg); width: 80%; }
  .s-news .q2 { left: 26%; top: 36%; transform: rotate(5deg);  width: 76%; }
  .s-news .q3 { left: 8%;  top: 58%; transform: rotate(-3deg); width: 78%; }
  .s-news .q4 { left: 28%; top: 78%; transform: rotate(6deg);  width: 72%; }
  .s-news .quote-text { font-size: 26px; }
</style>
<div class="slide-canvas s-news">
  <div class="QuoteCard q1">
    <div class="quote-text">“In 2023, researchers introduced new benchmarks—MMMU, GPQA, and SWE-bench—to test the limits of advanced AI systems. Just a year later, performance sharply increased: scores rose by 18.8, 48.9, and 67.3 percentage points”</div>
    <div class="quote-cite">Stanford HAI, AI Index 2025</div>
  </div>
  <div class="QuoteCard q2">
    <div class="quote-text">“Yet the current AI-related capex boom ... already
accounts for more than one-third of Q2-2025 U.S. economic growth.”</div>
    <div class="quote-cite">Carlyle Compass Report, July 2025</div>
  </div>
  <div class="QuoteCard q3">
    <div class="quote-text">“We predict that the impact of superhuman AI over the next decade will be enormous, exceeding that of the Industrial Revolution.”</div>
    <div class="quote-cite">AI 2027 Report</div>
  </div>
  <div class="QuoteCard q4">
    <div class="quote-text">“We will need fewer people doing some of the jobs that are being done today, and more people doing other types of jobs.”</div>
    <div class="quote-cite">Andy Jassy, Amazon CEO, June 2025</div>
  </div>
</div>

<!--
Your Newsfeed Is Flooded With AI Stories
Assuming you're not living under a rock, you're seeing alot of news about AI - market trends, model releases, data center construction, etc.  It's hard for a nonexpert to distinguish hype from reality. But also, once you use one of these models for a bit, it's hard to say that there's nothing new here.
-->

---

<style>
  .s-me .ScrimBox { left: 50%; top: 78%; transform: translate(-50%,-50%); font-size: 48px; text-align: center; padding: 22px 28px; }
</style>
<div class="slide-canvas s-me">
  <img class="bg-img" src="./images/office-me.png" alt="Office scene" />
  <div class="ScrimBox">But what about <em>MY</em> job?</div>
</div>

<!--
But What Does It Mean For ME?
Instead of getting long term investment advice, the question you're probably more interested in is: "What is going to happen to *my* job?" This talk is going to try to help with that in two ways.  First, to give you a mental model to think about what's happening and where it's going.  Second, do give you some concrete practices to get you started working with AI.
-->

---


<style>
  section {
    display: flex;
    justify-content: center;
    align-items: center;
    background: #999;
  }
  
  .cal-wrapper {
    width: 500px;
    height: 600px;
    background: white;
    border: 2px solid #222;
    border-radius: 18px;
    display: flex;
    flex-direction: column;
    overflow: hidden;
  }
  
  .cal-header {
    height: 52px;
    border-bottom: 2px solid #222;
    display: flex;
    align-items: center;
    padding: 0 16px;
    font-weight: 800;
    flex-shrink: 0;
  }
  
  .cal-content {
    flex: 1;
    position: relative;
    background-image: 
      repeating-linear-gradient(
        to bottom,
        transparent 0px,
        transparent 66px,
        #e9e9e9 66px,
        #e9e9e9 69px
      );
  }

  .events-area {
    margin-left: 60px;
    margin-right: 12px;
    height: 100%;
    position: relative;
  }
  
  .evt {
    position: absolute;
    left: 0;
    right: 0;
    background: #f7f9ff;
    border: 2px solid #222;
    border-radius: 12px;
    padding: 8px;
    font-size: 13px;
  }
  
  .evt-1 { top: 15px; height: 45px; border-left: 6px solid #1a73e8; }
  .evt-2 { top: 90px; height: 45px; border-left: 6px solid #1a73e8; }
  .evt-3 { top: 207px; height: 60px; border-left: 6px solid #fbbc05; }
  .evt-4 { top: 310px; height: 90px; border-left: 6px solid #fbbc05; }
  
  .evt b { display: block; font-size: 14px; margin-bottom: 2px; }
  .evt i { font-style: normal; color: #666; font-size: 11px; }
</style>

<div class="cal-wrapper">
  <div class="cal-header">Today — Day View</div>
  <div class="cal-content">
    <div class="events-area">
      <div class="evt evt-1"><b>Reply to emails</b><i>9:15–10:00</i></div>
      <div class="evt evt-2"><b>Review customer feedback</b><i>10:30–11:15</i></div>
      <div class="evt evt-3"><b>Lead RFP Response Review</b><i>1:00–2:00</i></div>
      <div class="evt evt-4"><b>Write strategy proposal</b><i>3:00–4:30</i></div>
    </div>
  </div>
</div>

<!--
What Actually *Is* Your Job Anyway?
Let's start not with AI, but with trying to figure out what your job actually is.  Let's assume you're an accountant or a programmer or a legal assistant or something like that.  You probably think of your job as a single thing - programming - but if we look at your calendar, I bet we'll see your time split between different things: "doing" the work (writing the code, making the spreadsheet) and "deciding" what work to do (planning, managing, strategizing).  This means your job isn't really one thing, but a bundle of different activities.
-->

---

<style>
  .s-drucker .QuoteCard { width: 35%; }
  .s-drucker .q1 { top: 14%; left: 10%;}
  .s-drucker .q2 { top: 20%; left: 50%;}
  .s-drucker .q3 { top: 66%; left: 25%; width: 50%}
</style>
<div class="slide-canvas s-drucker">
  <div class="QuoteCard q1">
    <div class="quote-text">“Work on knowledge-worker productivity therefore begins with asking the knowledge workers themselves: What is your task? What should it be? What should you be expected to contribute? and What hampers you in doing your task and should be eliminated?”</div>
    <div class="quote-cite">—Peter Drucker, <em>The Daily Drucker</em></div>
  </div>
  <div class="QuoteCard q2">
    <div class="quote-text">“For, once beyond the apprentice stage, knowledge workers must know more about their job than their boss does—or else they are no good at all. In fact, that they know more about their job than anybody else in the organization is part of the definition of knowledge workers.”</div>
    <div class="quote-cite">—Peter Drucker, <em>The Essential Drucker</em></div>
  </div>
  <div class="QuoteCard q3">
    <div class="quote-text">“Knowledge workers own the means of production. It is the knowledge between their ears. And it is a totally portable and enormous capital asset.”</div>
    <div class="quote-cite">—Peter Drucker, <em>Management Challenges for the 21st Century</em></div>
  </div>
</div>

<!--
You Really Are The Boss Of You
This pattern of work - a mix of doing and deciding - was noticed as a new pattern way back in the 1960s.  Peter Drucker saw these jobs emerging - people who weren't working with their hands in the factory but also weren't executives - and coined the term "knowledge work".

He pointed out that this style of work makes you the manager of your own one-person department - you're both the boss and the worker - because only you both understand the task and can actually do it.  That's the way we - accountants and programmers and graphic designers - have worked ever since.

But now AI is putting pressure on this bundle of doing + deciding inside a single person.
-->

---


<style>
  .s-gx3 .bg{
    position:absolute; inset:0;
    width:100%; height:100%; object-fit:cover;
  }
  .s-gx3 .wrap{
    position:absolute; left:50%; top:50%;
    transform:translate(-50%,-50%);
    text-align:center;
  }
  .s-gx3 .line{
    font-weight:800; font-size:84px; line-height:1.08; letter-spacing:-0.5px;
    white-space:nowrap; /* exactly two lines */
  }

  /* Cross out “puck” with an X */
  .s-gx3 .puck{
    position:relative; display:inline-block; padding:0 10px;
  }
  .s-gx3 .puck::before,
  .s-gx3 .puck::after{
    content:""; position:absolute; left:-8%; right:-8%; top:50%;
    border-top:8px solid #111;
    transform-origin:center;
  }
  .s-gx3 .puck::before{ transform:rotate(26deg); }
  .s-gx3 .puck::after { transform:rotate(-26deg); }

  /* Bold, slightly tilted “AI” set off to the left of line 2 */
  .s-gx3 .ai{
    position:absolute;
    top:calc(50% + 44px); /* near the second line */
    left:18%;             /* off to the left */
    transform:rotate(-12deg);
    font-weight:900; font-size:110px; color:#c40000;
    pointer-events:none;
  }

  /* Attribution at bottom center */
  .s-gx3 .attrib{
    position: static;           /* was absolute */
    transform: none;
    margin-top: 12px;           /* space under the quote */
    font-size: 28px;
    font-weight: 600;
  }
</style>

<div class="slide-canvas s-gx3">
  <img class="bg" src="./images/hockey.png" alt="Hockey background" />
  <div class="wrap">
    <div class="line">Skate to where the</div>
    <div class="line"><span class="puck">puck</span> is going</div>
    <div class="attrib">- Wayne Gretzsky</div>
  </div>
  <div class="ai">AI</div>
</div>

<!--
Getting A Handle On The Future
Let's switch from thinking about your jobs to thinking about AI and how it will change our jobs and careers.  At this point, you might say "Hold on!  You just started with a bunchn of headlines about how AI is changing so fast.  How can we possibly plan for our futures?"

The answer is that we need to understand the path that AI technology is on, why it's on that path, project that into the future, and "skate to where the puck is going"

That might seem impossible, but remember that a few years ago GPT-4 was a magic technology no one had seen before.  Now, there are Google Gemini, Anthropic Claude, xAI Grok, Deepseek, Kimi, and a few others.  And they all do roughly similar things to roughly similar levels of ability.  The fact that the industry is converging in this way says that there is probably something structural driving it that we can "skate to".
-->

---

<style>
  /* ===== Four separate boxes with downward arrows (no outer container) ===== */
  .s-blueprint-steps .box{
    position:absolute; left:8%; right:8%;
    height:14%;
    background:#fff; border:2px solid #222; border-radius:12px;
    display:grid; grid-template-columns: 280px 1fr; column-gap:16px;
    align-items:center; padding:12px 16px; box-sizing:border-box;
  }
  .s-blueprint-steps .b1{ top:10%; }
  .s-blueprint-steps .b2{ top:32%; }
  .s-blueprint-steps .b3{ top:54%; }
  .s-blueprint-steps .b4{ top:76%; }

  .s-blueprint-steps .step{
    justify-self:start; font-weight:800;
    border:2px solid #222; border-radius:8px; padding:6px 10px;
    background:#fff; font-size:24px;
  }
  .s-blueprint-steps .desc{ font-size:20px; }
  .s-blueprint-steps .mono{
    font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", monospace;
  }

  /* Short, thick black arrows between boxes */
  .s-blueprint-steps .arrow{
    position:absolute; left:50%; transform:translateX(-50%);
    width:10px; height:28px; background:#111; border-radius:5px;
  }
  .s-blueprint-steps .arrow::after{
    content:""; position:absolute; left:50%; transform:translateX(-50%);
    top:100%;
    border-style:solid; border-width:12px 10px 0 10px; /* pointing down */
    border-color:#111 transparent transparent transparent;
  }
  .s-blueprint-steps .a1{ top:26%; }
  .s-blueprint-steps .a2{ top:48%; }
  .s-blueprint-steps .a3{ top:70%; }
</style>

<div class="slide-canvas s-blueprint-steps">
  <div class="box b1">
    <div class="step">Next token</div>
    <div class="desc mono">The capital of Canada is ...</div>
  </div>

  <div class="arrow a1"></div>

  <div class="box b2">
    <div class="step">Instruction tuning</div>
    <div class="desc mono">Respond to questions with answers<br>"You" means the AI</div>
  </div>

  <div class="arrow a2"></div>

  <div class="box b3">
    <div class="step">RLHF</div>
    <div class="desc mono">This is an okay essay, but that is a better essay.</div>
  </div>

  <div class="arrow a3"></div>

  <div class="box b4">
    <div class="step">Reasoning + RLVR</div>
    <div class="desc mono">Complete math quizzes<br>Think out loud but only return your final answer</div>
  </div>
</div>

<!--
AI Isn't Magic, It's (Just) Brilliant Pattern Matching

There's a tendency to view AI as magic because of all the sci-fi stories we've read.  Viewed another way, it's just a pattern matching machine being put through and increasingly sophisticated set of schools.

It starts with being able to finish sentences - to do that you need to understand basic grammar and facts about the world.  Then it learns to play the "chat" game - in the internet documents it read "you" didn't mean "you, the AI", but here it does.

Now it's finished elementary school and it knows how to read and play well with others.  Now it needs to get better.  First, we have it write essays and have the (human) teacher tell it which essays are good and bad.  Second, for areas like math and logic and programming where we can make up easy-to-grade questions, we have have it take quizzes over and over.

That's actually all it is.  And that's the "convergence" - If there is a skill that we can teach and test at scale with humans, then we can train the AI to do it, as long at it is economically valuable.  It makes input-output machines that can mimic these human skills.
-->

---


<style>
  .s-tool-pol2c .polaroid{
    position:absolute; left:5%; bottom:18%;   /* raised from 12% */
    width:26%; height:38%;
    background:#fff; border:2px solid #222; box-shadow:none; box-sizing:border-box;
  }
  .s-tool-pol2c .polaroid .photo{
    position:absolute; left:4%; right:4%; top:4%; bottom:18%;
    border:2px solid #222; overflow:hidden; background:#eee;
  }
  .s-tool-pol2c .polaroid .photo img{
    width:100%; height:100%; object-fit:cover; display:block;
  }
  .s-tool-pol2c .polaroid .label{
    position:absolute; left:0; right:0; bottom:4%;
    text-align:center; font-size:14px; letter-spacing:.3px;
  }

  /* Bubble raised to keep the pair visually centered */
  .s-tool-pol2c .bubble{
    position:absolute; left:33%; top:48%;     /* was 56% */
    transform:translateY(-50%);
    width:58%;
    background:#fff; color:#111;
    border:2px solid #222; border-radius:18px;
    padding:22px 26px; box-shadow:none; box-sizing:border-box;
    font-size:36px; line-height:1.2;
  }
  .s-tool-pol2c .bubble::before{
    content:""; position:absolute; left:-40px; top:50%; margin-top:-14px;
    border-width:14px 40px 14px 0; border-style:solid;
    border-color:transparent #222 transparent transparent;
  }
  .s-tool-pol2c .bubble::after{
    content:""; position:absolute; left:-36px; top:50%; margin-top:-12px;
    border-width:12px 36px 12px 0; border-style:solid;
    border-color:transparent #fff transparent transparent;
  }
</style>

<div class="slide-canvas s-tool-pol2c">
  <div class="polaroid">
    <div class="photo">
      <img src="./images/jensen-huang.png" alt="Jensen Huang">
    </div>
    <div class="label">Jensen&nbsp;Huang, NVIDIA CEO</div>
  </div>

  <div class="bubble">
    “These AI data centers, if you will, are improperly described. They are, in fact, AI factories. You apply energy to it, and it produces something incredibly valuable, and these things are called tokens.”
  </div>
</div>

<!--
Industrial-Scale Cognition

Once we see that it's an input-output machine - ask Jensen Huang puts it a "cognitive factory" or an "AI factory" - then we should be asking how we can get the most out of it.

However, the kinds of outputs that AI makes - documents, images, etc - are different.  Every iPhone is exactly like every other iPhone - it's supposed to be!  But every document is supposed to be unique, to say something that the other documents didn't already say, because documents are information, and information can be copied.

How to achieve this "uniqueness at scale" is the core question.  Let's try to find a mental model of this, and then turn that insight into some specific practices.
-->

---

<style>
  /* ===== Slide 2: “AI Looks Like Something Familiar” — masks, right = gig workers (no custom bg) ===== */
  .s-masks-doors .polaroid{
    position:absolute; width:28%; height:58%;
    top:18%; background:#fff; border:2px solid #222; box-shadow:none; box-sizing:border-box;
  }
  .s-masks-doors .p-left  { left:6%;  transform:rotate(-4deg); }
  .s-masks-doors .p-mid   { left:36%; transform:rotate(3deg); }
  .s-masks-doors .p-right { right:6%; transform:rotate(-2deg); }

  .s-masks-doors .photo{
    position:absolute; left:4%; right:4%; top:4%; bottom:20%;
    border:2px solid #222; background:#fff; overflow:hidden;
    display:flex; align-items:center; justify-content:center;
  }
  .s-masks-doors .label{
    position:absolute; left:0; right:0; bottom:6%;
    text-align:center; font-size:16px; letter-spacing:.2px;
  }

  /* Simple UI illusions inside .photo (white-box style) */
  .s-masks-doors .searchbar{
    width:86%; height:44px; border:2px solid #222; border-radius:24px; background:#fff;
  }
  .s-masks-doors .chatstack{
    width:86%; display:grid; row-gap:10px;
  }
  .s-masks-doors .chatstack .row{
    height:36px; border:2px solid #222; border-radius:12px; background:#fff;
  }
  .s-masks-doors .jobcard{
    width:88%; border:2px solid #222; border-radius:12px; background:#fff; padding:10px; box-sizing:border-box;
  }
  .s-masks-doors .jobline{ height:18px; border:2px solid #222; border-radius:8px; background:#f6f6f6; margin:6px 0; }

  /* “Correct” mark as a white tag */
  .s-masks-doors .ok{
    position:absolute; right:10px; top:10px;
    border:2px solid #222; border-radius:8px; padding:4px 8px; font-weight:800; background:#fff;
  }
</style>
<div class="slide-canvas s-masks-doors">
  <!-- Left: Search habits -->
  <div class="polaroid p-left">
    <div class="photo">
      <div class="searchbar"></div>
    </div>
    <div class="label">Google Search<br>Question -> Default Answer</div>
    <div class="ok">X</div>
  </div>

  <!-- Middle: Chat habits -->
  <div class="polaroid p-mid">
    <div class="photo">
      <div class="chatstack" style="align-items:center;">
        <div class="row" style="width:92%;"></div>
        <div class="row" style="width:76%;"></div>
        <div class="row" style="width:88%;"></div>
        <div class="row" style="width:70%;"></div>
      </div>
    </div>
    <div class="label">Slack<br>Back-and-forth discussion</div>
    <div class="ok">X</div>
  </div>

  <!-- Right: Gig workers (correct mental model) -->
  <div class="polaroid p-right">
    <div class="photo">
      <div class="jobcard">
        <div class="jobline" style="width:80%;"></div>
        <div class="jobline" style="width:60%;"></div>
        <div class="jobline" style="width:90%;"></div>
        <div class="jobline" style="width:72%;"></div>
      </div>
    </div>
    <div class="label">Gig Workers<br>Task Brief->Results</div>
    <div class="ok">✓</div>
  </div>
</div>

<!--
AI Looks Like Something Familiar, But That's a Trap

When we first encounter AI, we see it in a UI with a text box.  That makes us want to use it like we use other UIs with a text box.

We see it like Google Search, and we ask a question, and get back some answer.  That's important, but under-uses it.  The AI could return many different answers, but search is about returning the "standard" answer, not the "for me, for this specific case" answer.

We also see it like Slack (or Discord or SMS), and we have conversations with it.  Again, that's valuable - sometimes the only way to figure out what you think is to use conversations to put your thinking into words.  But once you know what you want, that's a slow way to do it.  And it makes you think of the AI like a colleague - with agency and memory and learning - rather than as a tool.

Instead, I want to suggest a different model for working with AI - AI as gig workers.  Instead of asking it questions, or chatting, you ask it to do tasks, which you specify in a brief, and you get back results.
-->

---

<style>
  .s-sec2 .LargeText { left: 50%; top: 50%; transform: translate(-50%,-50%); text-align: center; }
</style>
<div class="slide-canvas s-sec2">
  <div class="LargeText">How To Work With AI</div>
</div>

<!--
How To Work With AI
(Section divider slide)
-->

---

<style>
  /* Title box directly above, same width as the page */
  .s-pr .titleBox {
    position: absolute;
    left: 50%;
    top: 18%;
    transform: translate(-50%, -50%);
    width: 76%;                 /* match .page width */
    background: #fff;
    border: 2px solid #222;
    border-radius: 14px;
    padding: 14px 24px;
    box-sizing: border-box;
    text-align: center;
    font-size: 34px;
    font-weight: 900;
    letter-spacing: 0.2px;
    white-space: nowrap;         /* keep on one line */
  }

  .s-pr .page {
    position: absolute;
    left: 50%;
    top: 56%;                    /* lowered slightly to sit under title box */
    transform: translate(-50%,-50%);
    width: 76%;
    padding: 28px 32px 36px 32px;
    background: #fff;
    border: 2px solid #222;
    border-radius: 14px;
    box-shadow: none;
    box-sizing: border-box;
  }
  .s-pr .avatar {
    position: absolute;
    left: 24px;
    top: 24px;
    width: 72px;
    height: 72px;
    object-fit: cover;
    border-radius: 50%;
    border: 2px solid #222;
  }
  .s-pr .name {
    position: absolute;
    left: 116px; /* 24px (padding) + 72px (avatar) + 20px gap */
    top: 40px;
    font-size: 22px;
    font-weight: 700;
  }
  .s-pr .body {
    margin-top: 116px; /* space for avatar/name area */
    display: grid;
    row-gap: 22px;
  }
  .s-pr .row {
    display: grid;
    grid-template-columns: 1fr auto;
    align-items: center;
    column-gap: 18px;
  }
  .s-pr .q { font-size: 28px; }
  .s-pr .stars { display: flex; gap: 6px; }
  .s-pr .star { font-size: 32px; line-height: 1; color: #c7c7c7; }
  .s-pr .star.sel { color: #f5c518; }
</style>

<div class="slide-canvas s-pr">
  <div class="titleBox">Human Manager - 360 Performance Review</div>

  <div class="page">
    <img class="avatar" src="./images/ai-profile.png" alt="AI profile" />
    <div class="name">AI Gig Worker #37</div>
    <div class="body">
      <div class="row">
        <div class="q">“My manager provides me clear direction.”</div>
        <div class="stars" aria-label="2 of 5">
          <span class="star sel">★</span><span class="star sel">★</span><span class="star">☆</span><span class="star">☆</span><span class="star">☆</span>
        </div>
      </div>
      <div class="row">
        <div class="q">“My manager finds me important work to do.”</div>
        <div class="stars" aria-label="3 of 5">
          <span class="star sel">★</span><span class="star sel">★</span><span class="star sel">★</span><span class="star">☆</span><span class="star">☆</span>
        </div>
      </div>
      <div class="row">
        <div class="q">“My manager gives useful feedback quickly.”</div>
        <div class="stars" aria-label="2 of 5">
          <span class="star sel">★</span><span class="star sel">★</span><span class="star">☆</span><span class="star">☆</span><span class="star">☆</span>
        </div>
      </div>
    </div>
  </div>
</div>

<!--
How Are You At Managing AI Gig Workers?

Let's connect the dots. Drucker said you're a manager-and-worker.  AI is a great worker, but not at all a manager.  This suggests that you need to become the manager.  So how are you at that?

If you're like most people - especially people who have never managed before - probably pretty terrible.  When we're both the manager assigning the task, and the worker doing the task, we can be very loose about how the task is define, what result we want back, what the priorities are, etc.  But if we give the task to someone else, we need to be much more precise and much more thoughtful in how we delegate work.
-->

---

<style>
  .s-context .wrap {
    position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    width: 86%;
    max-width: 1200px;
  }
  .s-context .box {
    background: #fff;
    border: 2px solid #222;
    border-radius: 18px;
    padding: 28px 36px;
    box-sizing: border-box;
  }
  .s-context .LargeText {
    position: static;                 /* inside the box */
    text-align: center;
    font-size: 68px;
    line-height: 1.06;
    letter-spacing: -0.5px;
  }
  .s-context .red { color: #c40000; } /* replaced the previous white */
</style>
<div class="slide-canvas s-context">
  <div class="wrap">
    <div class="box">
      <div class="LargeText">
        If you’re not pasting in context,<br/>
        <span class="red">you’re probably doing it wrong.</span>
      </div>
    </div>
  </div>
</div>

<!--
You Still Need To Tell Them What To Do

This is probably the most important lesson to remember from this talk.  The way the AI models work, you're (mostly) getting a new AI Gig Worker every time.  That person hasn't had water cooler chats with you about the strategy, or sat in on all your meetings.  So unless you tell them what matters to you for this job, they don't know.

You can ask them to do the task anyways, and you will get an answer, but it will be the "default" answer.  "Create sample financials for a new restaurant" rather than "Create sample financials for a 7000 sq ft chinese restaurant in the boston suburbs".

The more details you put in, the more you get the "for me" answer, not the "default answer".  And once you do this a few times, you realize that you need to explain alot.  That's ok.  We have copy-paste!
-->

---

<style>
/* ===== Post a Job (compact, top-to-bottom; true 2/3 : 1/3 split) ===== */
.s-job-vert .wrap{position:absolute;left:5%;right:5%;top:6%;bottom:6%;display:grid;grid-template-columns:55% 43%;column-gap:2%}

/* Cards that DO participate in layout (not absolute) */
.s-job-vert .Panel,.s-job-vert .PromptPanel{position:relative !important;background:#fff;border:2px solid #222;border-radius:12px;padding:14px 16px;box-sizing:border-box;height:100%;overflow:auto}

/* Section blocks on the left */
.s-job-vert .sec{border:2px dashed #999;border-radius:12px;padding:12px 14px;margin-top:12px;background:#fff}
.s-job-vert .sec:first-of-type{margin-top:0}
.s-job-vert .label{font-size:16px;color:#555;margin-bottom:6px}
.s-job-vert .kv{font-size:20px;line-height:1.32}
.s-job-vert ul{margin:6px 0 0 1.1em;padding:0;font-size:20px;line-height:1.32}

/* Mono */
.s-job-vert .mono{font-family:ui-monospace,SFMono-Regular,Menlo,Monaco,Consolas,"Liberation Mono",monospace}

/* Right column prompt (no <pre>/<code> — natural wrapping monospace) */
.s-job-vert .PromptPanel .t{font-size:18px;line-height:1.28;white-space:normal;overflow-wrap:anywhere;word-break:break-word;margin:6px 0}
.s-job-vert .PromptPanel ul.t{font-size:18px;line-height:1.28;margin:6px 0 0 1.1em}
</style>

<div class="slide-canvas s-job-vert">
<div class="wrap">

<div class="Panel">
  <div class="label">Task Brief</div>
  <div class="sec"><div class="label">Task</div><div class="kv">Edit for clarity, tighten to 700–750 words, keep author’s voice. Return tracked changes + clean copy.</div></div>
  <div class="sec"><div class="label">Inputs</div><div class="mono kv">/notes/*.md • audience.md</div></div>
  <div class="sec"><div class="label">Rubric (Definition of Done)</div><ul><li>Turn notes into a blog post with clear narrative prose.</li><li>Output should be in markdown format suitable for Substack</li><li>Highlight potential audience questions in separate document</li></ul></div>
  <div class="sec"><div class="label">Outputs</div><div class="mono kv">blog-post.md • questions.txt</div></div>
</div>

<div class="PromptPanel mono">
  <div class="label">AI Prompt</div>
  <div class="t">Write an 800–word blog post.</div>
  <div class="t">&lt;inputs&gt;<br/>&nbsp;&nbsp;&lt;file filename="notes/essay.md"&gt;<br/>&nbsp;&nbsp;&nbsp;&nbsp;...<br/>&nbsp;&nbsp;&lt;/file&gt;<br/>&nbsp;&nbsp;&lt;file filename="audience.md"&gt;<br/>&nbsp;&nbsp;&nbsp;&nbsp;...<br/>&nbsp;&nbsp;&lt;/file&gt;<br/>&lt;/inputs&gt;</div>
  <div class="t">Rubric:</div>
  <ul class="t">
    <li>Use clear, informal narrative writing style</li>
    <li>Maximize appeal for target audience defined in audience.md</li>
    <li>Return blog text in code block suitable for copy/paste</li>
    <li>Include potential unresolved question for target audience. Place this is a separate code block</li>
  </ul>
</div>

</div>
</div>

<!--
How To Write A Brief

So, how do we already work with real life contractors on places like Upwork or Fiverr?  We write a brief.

This is a short document that explains what success at the task looks like as clearly as possible.  It makes clear that this is an input-output situation - you send in the brief because what you want back is some artifact - a document, a design, etc - not some discussion or learnings or whatever.

Suppose the task is "design a logo for my company".  To get back a good answer, you should expect to include important information - the name of your company, the vibe you want, your favorite color, etc.

In AI land, this is called "prompting" or "context engineering", but you could also just think of it as "clear business communication" 
-->

---

<style>
  /* ===== Org challenges as ROWS: wide boxes with left label + right bullets ===== */
  .s-org-rows .row{
    position:absolute; left:6%; right:6%;
    height:32%;
    background:#fff; border:2px solid #222; border-radius:14px;
    display:grid; grid-template-columns: 42% 1fr; column-gap:24px;
    align-items:center; padding:18px 22px; box-sizing:border-box;
  }
  .s-org-rows .r1{ top:16%; }
  .s-org-rows .r2{ top:56%; }

  .s-org-rows .left{
    font-size:44px; font-weight:900; letter-spacing:.2px;
    line-height:1.06;
  }
  .s-org-rows .right{
    margin:0; padding-left:1.2em;
    font-size:22px; line-height:1.35;
  }
  .s-org-rows .right li{ margin:6px 0; }
</style>

<div class="slide-canvas s-org-rows">
  <div class="row r1">
    <div class="left">Hallucinations =<br>Gig Worker<br>Mistakes</div>
    <ul class="right">
      <li>Review all external work</li>
      <li>Structure outputs for easy checking (eg citations, URLs, etc)</li>
      <li>Use AI to check work - human and AI</li>
    </ul>
  </div>

  <div class="row r2">
    <div class="left">AI Training Data =<br>Vendor Data Retention Policy</div>
    <ul class="right">
      <li>Apply policies in use for Google Drive, Slack, Sharepoint, etc</li>
      <li>Identify data not to use with external contractors or AI</li>
      <li>Review vendor data retention and opt in/out policies</li>
    </ul>
  </div>
</div>

<!--
Dealing With Organizational Challenges

This "gig worker" framework also gives us a way to approach organizational challenges that come up in deploying AI.  Instead of thinking of AI as some totally novel kind of thing that needs a whole new framework, approach it as hiring a third party contractor or SaaS application to do a service and apply the same rules.

There are many examples, but let's take a few specific ones:

Hallucinations - The case of lawyers citing made up cases in legal briefs got alot of press as a "AI hallucinates" story.  What didn't get enough coverage was the "why did the human lawyers not check it?"  If they hired a low-cost outsourced legal research firm, would they have checked it?

Data privacy - This one is easier to understand - AI is trained on data, you give data to the AI to ask it a question, what does that imply.  At the same time, it's not a novel question - you give data to Google Drive and Microsoft Sharepoint - so you need to review the vendor's Data Retention and Acceptable Use policies in the same way.  The most common answer is to a) check for paid vs free plan, and b) check for opt-in / opt-out settings.
-->

---

<style>
  .s-sec2 .LargeText { left: 50%; top: 50%; transform: translate(-50%,-50%); text-align: center; }
</style>
<div class="slide-canvas s-sec2">
  <div class="LargeText">How Do I Get Started?</div>
</div>

<!-->
Now let's shift from how to think about AI - as a pool of gig workers - to how to get started using AI with some concrete approaches.
<-->

---

<style>
  /* ===== "Inject into the slide" layout (sample LEFT, labels RIGHT) ===== */
  .s-inject{
    --t-script: 22%;
    --t-layout: 38%;
    --t-quote : 54%;
    --t-image : 70%;
    --label-h: 9%;
    --mid: 4.5%;                           /* half of label height */
    --sample-left: 6%;
    --sample-w: 58%;
    --gap: 1.2%;                            /* tiny space before the slide */
    --arrow-left: calc(var(--sample-left) + var(--sample-w) + var(--gap));
    --arrow-w: 16%;                         /* arrow length toward labels */
  }
  .s-inject .wrap{
    position:absolute; left:5%; right:5%; top:6%; bottom:6%;
  }

  /* Right-side labels: narrower, centered text, closer to slide */
  .s-inject .in-label{
    position:absolute; right:3%; width:13.5%;
    height:var(--label-h);
    display:flex; align-items:center; justify-content:center; text-align:center;
    padding: 8px 10px;
    background:#fff; border:2px solid #222; border-radius:10px;
    font-size:26px; font-weight:900; letter-spacing:.2px;
    box-sizing:border-box;
  }
  .s-inject .l-script{ top:var(--t-script); }
  .s-inject .l-layout{ top:var(--t-layout); }
  .s-inject .l-quote { top:var(--t-quote ); }
  .s-inject .l-image { top:var(--t-image ); }

  /* Left-pointing arrows: vertically centered on each label,
     arrow head stops just shy of the sample slide */
  .s-inject .arrow{
    position:absolute; left:var(--arrow-left); width:var(--arrow-w);
    height:0; border-top:4px solid #222;
  }
  .s-inject .arrow::after{
    content:""; position:absolute; left:-12px; top:-12px;
    border-style:solid; border-width:10px 12px 10px 0;     /* point left */
    border-color:transparent #222 transparent transparent;
  }
  .s-inject .a-script{ top:calc(var(--t-script) + var(--mid)); }
  .s-inject .a-layout{ top:calc(var(--t-layout) + var(--mid)); }
  .s-inject .a-quote { top:calc(var(--t-quote ) + var(--mid)); }
  .s-inject .a-image { top:calc(var(--t-image ) + var(--mid)); }

  /* Big sample slide mock on the LEFT */
  .s-inject .sample{
    position:absolute; left:var(--sample-left); top:50%; transform:translateY(-50%);
    width:var(--sample-w); height:78%;
    background:#fff; border:2px solid #222; border-radius:14px;
    box-sizing:border-box;
  }

  /* Inside the sample: title bar, quote block, layout grid box, image box */
  .s-inject .title{
    position:absolute; left:6%; right:6%; top:6%;
    height:10%;
    border:2px solid #222; border-radius:10px;
    display:flex; align-items:center; padding:0 14px; box-sizing:border-box;
    font-weight:800; font-size:24px; letter-spacing:.2px; background:#fff;
  }
  .s-inject .quote{
    position:absolute; left:6%; right:52%; top:22%;
    height:32%;
    border:2px solid #222; border-radius:12px; background:#fff;
    padding:12px 14px; box-sizing:border-box;
    font-family: Georgia, 'Times New Roman', serif; font-size:20px; line-height:1.25;
  }
  .s-inject .layout{
    position:absolute; left:6%; right:52%; top:58%; bottom:12%;
    border:2px dashed #999; border-radius:12px; background:
      repeating-linear-gradient(0deg, transparent, transparent 28px, #eee 28px, #eee 30px),
      repeating-linear-gradient(90deg, transparent, transparent 120px, #eee 120px, #eee 122px);
    display:flex; align-items:center; justify-content:center; font-size:16px; color:#666;
  }
  .s-inject .image{
    position:absolute; left:52%; right:6%; top:22%; bottom:12%;
    border:2px dashed #888; border-radius:12px; background:#f3f3f3;
    display:flex; align-items:center; justify-content:center; font-size:18px; font-weight:700; color:#666;
  }
</style>

<div class="slide-canvas s-inject">
  <!-- Big sample slide (LEFT) -->
  <div class="sample">
    <div class="title">Sample Title</div>
    <div class="quote">“A memorable, slide-ready quote lives here to illustrate the point succinctly.”</div>
    <div class="layout">layout grid / callouts</div>
    <div class="image">IMAGE</div>
  </div>

  <!-- Right column labels (centered) + leftward arrows (centered on labels) -->
  <div class="in-label l-script">Script</div>
  <div class="arrow a-script"></div>

  <div class="in-label l-layout">Layout</div>
  <div class="arrow a-layout"></div>

  <div class="in-label l-quote">Quote</div>
  <div class="arrow a-quote"></div>

  <div class="in-label l-image">Image</div>
  <div class="arrow a-image"></div>
</div>

<!--
Start With A Repeated Task You Already Hate
Let's get started.  As we've said, the real hard part is defining a task, so start with a task that a) you already do repeatedly, b) you can outsource part of, and c) you don't actually like doing - the job is to get ride of this.  For some people with more structured jobs, this may be easy.  For others - especially people who do a little of alot of different things - this may require some thinking.

I'm going to use my own writing of this talk as an example.

First, remember that the AI is the "do-er" not the "decider".  You can't hand off "make the presentation", or even really "make this slide" as a task - that still has too much high-level deciding work.

So let's break down the task of making a slide into different parts.  Some of them like "what is the message of the slide", I should do myself.  Others, like "make an image that conveys the idea", I should definitely *not* do myself.  Instead, I should define what is a slide - a layout and slide text, a quote, and an image - and what I want out of it "support - not convey - the message to the target audience".

That process of finding smaller tasks inside the bigger project is the key unlock, but it's also very particular to each person's specific work.  Let me give you 3 different ways to approach it that I think work for different work styles.
-->

---

<style>
  /* ===== Jobs slide: "Help Wanted" + newspaper clipping cards (square, not tilted) ===== */
  .s-jobs-help .titleBar{
    position:absolute; left:50%; top:10%;
    transform:translate(-50%,-50%);
    width:84%;
    background:#fff; border:2px solid #222; border-radius:12px;
    padding:14px 22px; box-sizing:border-box;
    text-align:center; font-weight:900; font-size:36px; letter-spacing:.2px;
  }

  .s-jobs-help .grid{
    position:absolute; left:8%; right:8%; top:20%; bottom:8%;
    display:grid; grid-template-columns: 1fr 1fr; grid-template-rows: 1fr 1fr;
    gap:26px;
  }

  /* Reuse QuoteCard look but make it behave like a normal block in the grid */
  .s-jobs-help .QuoteCard{
    position:relative !important;       /* override global absolute */
    max-width:unset; height:auto;
    padding:16px 18px;
  }

  .s-jobs-help .job-title{ font-size:24px; font-weight:800; margin:0 0 6px 0; }
  .s-jobs-help .job-body { font-size:18px; line-height:1.32; }
</style>

<div class="slide-canvas s-jobs-help">
  <div class="titleBar">Help Wanted</div>

  <div class="grid">
    <div class="QuoteCard">
      <div class="job-title">Graphic Designer</div>
      <div class="mono job-body">Given attached Script, create 3 slide layouts that visually emphasize the key messages</div>
    </div>
    <div class="QuoteCard">
      <div class="job-title">Research Assistant</div>
      <div class="mono job-body">For each slide in Script that mentions a quotation or a publication year, either confirm the information or provide the corrected information, and include a URL of a credible source as reference.</div>
    </div>
    <div class="QuoteCard">
      <div class="job-title">Graphic Artist</div>
      <div class="mono job-body">For each image described in Layouts, generate an image that conveys that information in a way consistent with the attached Style Guidelines</div>
    </div>
    <div class="QuoteCard">
      <div class="job-title">Editor</div>
      <div class="mono job-body">Review text from the perspective of Target Audience.  Identify the key questions they will still have after this presentation.</div>
    </div>
  </div>
</div>

<!--
Approach 1: Job Postings

If you're familiar working with contractors, that's a natural place to start.  Look at your project, and imagine you get called away, and you still need to do this task but with less of your time.  Ask yourself "who could I hire to help me finish this faster"

Describe the kind of work you want done - graphic design, editing, etc - and then the details.  The AI doesn't really care - it has all of these skills and more - but it helps you figure out what the task is clearly.
-->

---

<style>
/* ===== Triangle Relay — outward-pointing, no-seam arrows; top arrow centered ===== */
.s-triangle10 .DocCard{position:absolute;z-index:2;background:#fff;border:2px solid #222;border-radius:12px;padding:16px 18px;box-sizing:border-box}
.s-triangle10 .c-script{left:7%;top:12%;width:36%;height:28%}
.s-triangle10 .c-layout{right:7%;top:12%;width:36%;height:28%}
.s-triangle10 .c-images{left:50%;top:64%;transform:translateX(-50%);width:44%;height:30%}
.s-triangle10 .DocCard h4{margin:0 0 10px 0;font-size:28px}
.s-triangle10 .lines{display:grid;row-gap:6px}
.s-triangle10 .line{height:10px;background:#eee;border:2px solid #222;border-radius:6px}
.s-triangle10 .w92{width:92%}.s-triangle10 .w80{width:80%}.s-triangle10 .w74{width:74%}.s-triangle10 .w66{width:66%}
.s-triangle10 .grid{position:relative;height:calc(100% - 40px);margin-top:6px;border:2px dashed #999;border-radius:10px;background:repeating-linear-gradient(0deg,transparent,transparent 28px,#eee 28px,#eee 30px),repeating-linear-gradient(90deg,transparent,transparent 120px,#eee 120px,#eee 122px);display:flex;align-items:center;justify-content:center;color:#666;font-size:16px}
.s-triangle10 .thumbs{display:flex;gap:10px;height:calc(100% - 40px);margin-top:6px}
.s-triangle10 .ph{flex:1;border:2px solid #222;border-radius:10px;background:#f3f3f3;display:flex;align-items:center;justify-content:center;font-weight:700;color:#666}
.s-triangle10 .Badge.compile{position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);z-index:4;background:#111;color:#fff;border:2px solid #111;border-radius:10px;padding:6px 12px;font-weight:900}

/* ===== Double-headed arrow: heads point TOWARD boxes; heads wider than shaft; no protrusion ===== */
.s-triangle10 .arrow{
  --shaft:16px;           /* line thickness */
  --headH:10px;           /* extra height above/below shaft (total head height = shaft + 2*headH) */
  --headW:34px;           /* head length */
  --overlap:2px;          /* base overlaps shaft to eliminate any seam */
  position:absolute; z-index:3; height:var(--shaft); background:#111; border-radius:0;
}
.s-triangle10 .arrow::before,
.s-triangle10 .arrow::after{
  content:""; position:absolute; top:50%; transform:translateY(-50%);
  width:var(--headW); height:calc(var(--shaft) + 2*var(--headH)); background:#111;
}
/* LEFT head — points LEFT (toward left box) */
.s-triangle10 .arrow::before{
  left:calc(-1*(var(--headW) - var(--overlap)));
  clip-path:polygon(0 50%,100% 0,100% 100%);  /* tip at LEFT edge */
}
/* RIGHT head — points RIGHT (toward right box) */
.s-triangle10 .arrow::after{
  right:calc(-1*(var(--headW) - var(--overlap)));
  clip-path:polygon(100% 50%,0 0,0 100%);     /* tip at RIGHT edge */
}

/* Placements: top arrow centered; slanted arrows short so heads stop just outside cards */
.s-triangle10 .arr-top{left:50%;transform:translateX(-50%);top:26%;width:12%}
.s-triangle10 .arr-s2i{left:28%;top:43%;width:11%;transform:rotate(56deg);transform-origin:left center}
.s-triangle10 .arr-l2i{right:28%;top:43%;width:11%;transform:rotate(-56deg);transform-origin:right center}
</style>

<div class="slide-canvas s-triangle10">
  <div class="DocCard c-script"><h4>script.md</h4><div class="lines"><div class="line w92"></div><div class="line w80"></div><div class="line w92"></div><div class="line w74"></div><div class="line w66"></div></div></div>
  <div class="DocCard c-layout"><h4>slides.marp</h4><div class="grid">layout grid</div></div>
  <div class="DocCard c-images"><h4>images/</h4><div class="thumbs"><div class="ph">IMG</div><div class="ph">IMG</div><div class="ph">IMG</div></div></div>
  <div class="Badge compile">compile</div>
  <div class="arrow arr-top"></div>
  <div class="arrow arr-s2i"></div>
  <div class="arrow arr-l2i"></div>
</div>

<!--
Approach 2:  Turning Documents Into Other Documents

This one is more for people who are used to working with files that have some sort of process around them - coding, for example.

The thing to notice is that AI has a weird nonobvious superpower:  It can take one kind of document and turn it into another kind of document.  People mostly use this in silly ways - write this essay in the form of a Shakespearean sonnet - but thinking of AI as a translator helps to structure what it's doing.  A summary is a translation of a long document into a short document.  Instead of writing a document, the AI can translate an outline into prose.

In this model, the AI is like a kind of compiler.  You tell it what its input and output types are, and you give it an input, and - like "make" - it builds one from the other.  This view is also helpful when what really matters isn't the work, but the exact form or structure of the output.
-->

---

<style>
  /* ===== Daily Briefing (3 columns): compact event on top + larger prompt (DIV, monospace) ===== */
  .s-brief3c .wrap{position:absolute;left:5%;right:5%;top:6%;bottom:6%}
  .s-brief3c .grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:26px;height:100%}
  .s-brief3c .col{display:grid;grid-template-rows:26% 1fr;row-gap:14px;min-width:0;min-height:0}
  /* Event card */
  .s-brief3c .event{background:#f7f9ff;border:2px solid #222;border-radius:18px;padding:14px 16px;box-sizing:border-box;height:100%;display:flex;flex-direction:column;justify-content:center;overflow:hidden}
  .s-brief3c .event .title{font-weight:900;font-size:22px;line-height:1.15;margin:0 0 6px 0}
  .s-brief3c .event .time{font-size:14px;color:#555}
  .s-brief3c .event.ev-a{border-left:10px solid #1a73e8}
  .s-brief3c .event.ev-b{border-left:10px solid #fbbc05}
  .s-brief3c .event.ev-c{border-left:10px solid #34a853}
  /* Prompt box — plain DIV with monospace font and natural wrapping */
  .s-brief3c .prompt{background:#fff;border:2px solid #222;border-radius:14px;padding:18px 20px;box-sizing:border-box;height:100%;overflow:auto}
  .s-brief3c .prompt .t{font-size:16px;line-height:1.35;white-space:normal;overflow-wrap:anywhere;word-break:break-word}
</style>

<div class="slide-canvas s-brief3c">
  <div class="wrap">
    <div class="grid">
      <div class="col">
        <div class="event ev-a"><div class="title">BizDev Initial Contact</div><div class="time">10:00–10:30 • Zoom</div></div>
        <div class="prompt mono"><div class="t">Provide me a one-page brief for COMPANY, website URL that will help me understand how their product might fit ours.<br>First, describe<br>- their product/offer<br>- key features<br>- main competitors and <br>- positioning with respect to each.<br>Then, suggest three possible areas of overlap with our company<br><br>&nbsp;&nbsp;&lt;file filename="us.txt"&gt;<br/>&nbsp;&nbsp;&nbsp;&nbsp;...<br/>&nbsp;&nbsp;&lt;/file&gt;<br><br>COMPANY = ...<br>URL = ...</div></div>
      </div>
      <div class="col">
        <div class="event ev-b"><div class="title">Contract Review</div><div class="time">1:00–2:00 • Conf Rm B</div></div>
        <div class="prompt mono"><div class="t">Provide me a brief on the attached contract file to help identify possible areas of tension.<br>The brief should describe the overall intent of the contract in one paragraph.  Then it should identify 5 terms likely to be disputed by one or both sides.  For each term, describe the meaning in plain english and its likely implications, then describe potential alternatives that might resolve the conflicts.<br><br>&nbsp;&nbsp;&lt;file filename="contract.txt"&gt;<br/>&nbsp;&nbsp;&nbsp;&nbsp;...<br/>&nbsp;&nbsp;&lt;/file&gt;</div></div>
      </div>
      <div class="col">
        <div class="event ev-c"><div class="title">Product/Dev Status Call</div><div class="time">3:30–4:15 • Zoom</div></div>
        <div class="prompt mono"><div class="t">Provide me a brief on the recent updates on product development to help me identify any areas that need scrutiny.  My main goal is to ensure that the V2.0 launch is ready by Aug 1st, and that all features considered risky have been mitigated.<br>Attached is a dump of recent tickets from JIRA.<br>Look for tickets with unresolved back-and-forth discussion, items behind schedule, or uncompleted test generation tasks, and summarize them in nontechnical language.<br><br>&nbsp;&nbsp;&lt;file filename="export.csv"&gt;<br/>&nbsp;&nbsp;&nbsp;&nbsp;...<br/>&nbsp;&nbsp;&lt;/file&gt;</div></div>
      </div>
    </div>
  </div>
</div>

<!--
Approach 3: Chief of Staff and "Audience of One" Reports

This third approach will be more familiar to more senior executives.  As your management span of control increases, at some point it makes sense to have a "Chief of Staff" or executive assistant.  Their job isn't to make your decisions for you, but instead to give you the exact context you need at the moment of decision, so you make the right decision as efficiently as possible.

AI can be that - think of it as hiring a consultant to create a report just for you, right now.  Given materials for an upcoming meeting, instead of asking for a summary, ask for "what are the key open decisions and what do I need to ask?"
-->

---

<style>
  .s-sec3 .LargeText { left: 50%; top: 50%; transform: translate(-50%,-50%); text-align: center; }
</style>
<div class="slide-canvas s-sec3">
  <div class="LargeText">Closing Thoughts For The Long Haul</div>
</div>

<!--
How To Think About Your Future
(Section divider slide)

We've covered how to think of AI - as gig workers needing clear briefs - and how to get started - thinking of them as help wanted, document translation, or audience-of-one reports.

Returning to the original question - what about MY job - that answers the tactics, but not necessarily the strategy.  Everyone's job is different, though, so there isn't one answer.  Instead, I want to leave you with some more strategic thoughts on how AI will affect your job over the long term - next 5 years? - to help you start preparing for it.
-->

---

<style>
  /* ===== Two-column layout: 1/3 (left) + 2/3 (right) ===== */
  .s-spectrum-2col .wrap{
    position:absolute; left:5%; right:5%; top:6%; bottom:6%;
    display:grid; grid-template-columns: 34% 64%; column-gap:2%;
  }

  /* LEFT column: stacked phrase, centered, white text with tighter spacing */
  .s-spectrum-2col .left-col{ position:relative; }
  .s-spectrum-2col .left-stack{
    position:absolute; inset:0;
    display:flex; flex-direction:column;
    justify-content:center;          /* center block vertically */
    align-items:center; text-align:center;
    gap:10px;                         /* tighter than space-between */
    padding:4% 0;                     /* keep from touching edges */
  }
  .s-spectrum-2col .left-stack .wline{
    color:#fff; font-weight:900; font-size:60px; letter-spacing:.2px;
    line-height:1.02;
  }

  /* RIGHT column: spectrum & labels (no arrows/braces/lines) */
  .s-spectrum-2col .right-col{ position:relative; }

  .s-spectrum-2col .right-col .spectrum-strip{
    position:absolute; left:50%; top:50%;
    transform:translate(-50%,-50%);
    width:1in; height:78%;
    border:2px solid #222; border-radius:14px;
    background: linear-gradient(
      to bottom,
      #FF0000 0%,
      #FF7F00 16.6%,
      #FFFF00 33.3%,
      #00FF00 50%,
      #00FFFF 66.6%,
      #0000FF 83.3%,
      #8B00FF 100%
    );
    box-sizing:border-box;
  }

  .s-spectrum-2col .right-col .tag{
    position:absolute; background:#fff; color:#111;
    border:2px solid #222; border-radius:12px;
    padding:6px 12px; font-weight:900; letter-spacing:.2px;
    white-space:nowrap; transform:translateY(-50%);
  }

  /* Left-of-strip labels (bigger) */
  .s-spectrum-2col .right-col .l-tag{ left:8%;  font-size:44px; }
  .s-spectrum-2col .right-col .l-red    { top:18%; }
  .s-spectrum-2col .right-col .l-green  { top:50%; }
  .s-spectrum-2col .right-col .l-blue   { top:80%; }

  /* Right-of-strip labels aligned to hues (smaller) */
  .s-spectrum-2col .right-col .r-tag{ right:8%; font-size:22px; }
  .s-spectrum-2col .right-col .r-vermillion { top:16%; }
  .s-spectrum-2col .right-col .r-amber      { top:28%; }
  .s-spectrum-2col .right-col .r-chartreuse { top:38%; }
  .s-spectrum-2col .right-col .r-lime       { top:48%; }
  .s-spectrum-2col .right-col .r-turquoise  { top:58%; }
  .s-spectrum-2col .right-col .r-cyan       { top:68%; }
  .s-spectrum-2col .right-col .r-indigo     { top:82%; }  /* between blue & violet */
</style>

<div class="slide-canvas s-spectrum-2col">
  <div class="wrap">
    <!-- LEFT column: phrase -->
    <div class="left-col">
      <div class="left-stack">
        <div class="wline">learn</div>
        <div class="wline">the</div>
        <div class="wline">right</div>
        <div class="wline">word</div>
        <div class="wline">for</div>
        <div class="wline">the</div>
        <div class="wline">right</div>
        <div class="wline">job</div>
      </div>
    </div>
    <!-- RIGHT column: spectrum + labels -->
    <div class="right-col">
      <div class="spectrum-strip"></div>
      <!-- Left of strip -->
      <div class="tag l-tag l-red">red</div>
      <div class="tag l-tag l-green">green</div>
      <div class="tag l-tag l-blue">blue</div>
      <!-- Right of strip -->
      <div class="tag r-tag r-vermillion">vermillion</div>
      <div class="tag r-tag r-amber">amber</div>
      <div class="tag r-tag r-chartreuse">chartreuse</div>
      <div class="tag r-tag r-lime">lime</div>
      <div class="tag r-tag r-turquoise">turquoise</div>
      <div class="tag r-tag r-cyan">cyan</div>
      <div class="tag r-tag r-indigo">indigo</div>
    </div>
  </div>
</div>

<!--
Learn Some Expert Vocabulary

To delegate effectively, it helps to have the right words.  Even if you can't build a UI, knowing words like "modal" or "dropshadow" or "gradient" helps you describe what you want.  Even if you don't program, knowing what an API or a database is helps you describe a SaaS product.

Read blogs or listen to podcasts by experts in the fields you need - not so you do their job, but so that you can use their language in talking to the AI.  What you'll find it that it not only makes you better at describing what you want, it makes you better at noticing details you couldn't see until you had words for them.
-->

---

<style>
  /* ===== Two-rows math layout with extra spacing & refined X-out ===== */
  .s-two-rows .wrap{
    position:absolute; left:50%; top:50%;
    transform:translate(-50%,-50%);
    width:86%; max-width:1200px;
  }

  .s-two-rows .Row{
    position:relative;                          /* for absolute badges */
    background:#fff; border:2px solid #222; border-radius:18px;
    padding:40px 44px;                          /* roomy so badges/text never collide */
    box-sizing:border-box;
    margin:0 0 40px 0;                          /* MORE space between the boxes */
  }
  .s-two-rows .Row.is-big{                      /* larger bottom box */
    padding:48px 52px 40px 52px;
  }

  /* Shared grid so '=' aligns across rows */
  .s-two-rows .grid{
    display:grid;
    grid-template-columns: 1fr auto 1fr;        /* L | '=' | R */
    align-items:center; column-gap:18px;
  }
  .s-two-rows .Row.is-big .grid{ margin-bottom:28px; } /* extra gap above red line */

  .s-two-rows .lhs,
  .s-two-rows .rhs{
    font-weight:800; letter-spacing:-0.5px; line-height:1.06;
    font-size:56px;
  }
  .s-two-rows .eq{
    font-weight:900; font-size:56px; text-align:center; width:56px;
  }

  /* Badge (uses global .Badge look) */
  .s-two-rows .badge{
    position:absolute; left:16px; top:-22px;   /* floats outside the corner */
  }

  /* Red corrective line — same size as main text, right-aligned */
  .s-two-rows .subline{
    text-align:right;
    font-weight:800; letter-spacing:-0.3px; line-height:1.06;
    font-size:56px; color:#c40000;             /* Gretzky slide red */
    margin-top:24px;                           /* more space from line above */
  }

  /* Black X strike for crossed-out text — shallower angle, stays on the line */
  .s-two-rows .xout{
    position:relative; display:inline-block; padding:0 12px;
  }
  .s-two-rows .xout::before,
  .s-two-rows .xout::after{
    content:""; position:absolute; left:-10%; right:-10%; top:50%;
    border-top:8px solid #111; transform-origin:center;
  }
  .s-two-rows .xout::before{ transform:rotate(12deg); }  /* more horizontal */
  .s-two-rows .xout::after { transform:rotate(-12deg); } /* more horizontal */
</style>

<div class="slide-canvas s-two-rows">
  <div class="wrap">
    <!-- Row 1: Doing -->
    <div class="Row">
      <div class="Badge badge">Doing</div>
      <div class="grid">
        <div class="lhs">Tasks&nbsp;+&nbsp;AI</div>
        <div class="eq">=</div>
        <div class="rhs">More&nbsp;Tasks</div>
      </div>
    </div>
    <!-- Row 2: Deciding (bigger, includes two lines; “More Strategies” crossed out) -->
    <div class="Row is-big">
      <div class="Badge badge">Deciding</div>
      <div class="grid">
        <div class="lhs">Strategies&nbsp;+&nbsp;AI</div>
        <div class="eq">=</div>
        <div class="rhs"><span class="xout">More&nbsp;Strategies</span></div>
      </div>
      <div class="subline">One&nbsp;Strategy,&nbsp;More&nbsp;Implementation</div>
    </div>
  </div>
</div>

<!--
Your Path Forward: Climb the Ladder from Doer to Decider
So far, we've focused on how to use AI on the "doing" side, but what about if your role is more "deciding".  There, you can use AI to come up with strategies and frameworks and plans much faster than before.  But probably that planning was already more limited by execution than new ideas, and adding AI to plan faster will only widen that gap.  Ironically, you likely need to focus on making your plans more concrete and execution - more "doing" - instead, and use AI to do that.

You can "prototype" your ideas with AI - not just "we should change our website messaging" but "I had the AI read the pages on our current website and here are the ones that need to change".
-->

---

<style>
  .s-scale .ScrimBox { left: 50%; top: 84%; transform: translate(-50%,-50%); font-size: 36px; text-align: center; }
</style>
<div class="slide-canvas s-scale">
  <img class="bg-img" src="./images/giant-in-cottage.png" alt="Giant in cottage" />
  <div class="ScrimBox">AI succeeds by scaling<br>Find roles where you can scale with it</div>
</div>

<!--
The Long-Term Catch: AI Needs Scale to Matter

I want to end with a not so obvious consequence: using AI effectively requires your role to be able to scale. Let's say you use AI to become 3x more productive at customer support for a local toy store. The store won't sell 3x more toys; they'll just need 1/3 of the support staff. But if you work for a company whose business *is* customer support, that 3x efficiency is fuel for growth by taking market share from competitors. Increasingly, AI is going to force us all to think about scale much more than we ever have before, and that may change the kinds of organizational structures that make sense.  Instead of being the one accountant at a company, you might end up as a fractional accountant working with 5 companies instead.
-->
