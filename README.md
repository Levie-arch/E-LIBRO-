<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>COLLEGE OF ARTS AND SCIENCES OF ASIA AND THE PACIFIC E-LIBRO</title>-
<!-- Simple, self-contained styles -->
<style>
  :root{
    --primary:#0f62fe;      /* CASAP blue-ish */
    --accent:#06b6d4;       /* teal accent */
    --bg:#f4f7fb;
    --card:#ffffff;
    --muted:#6b7280;
    --glass: rgba(255,255,255,0.75);
    --shadow: 0 6px 18px rgba(43, 84, 180, 0.08);
    --radius:14px;
    font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
  }

  /* Page background with subtle pattern and gradient */
  body{
    margin:0;
    background:
      linear-gradient(180deg, rgba(15,98,254,0.06), rgba(6,182,212,0.02)),
      url('img4-head.jpg.jfif') center/cover no-repeat;
    background-attachment: fixed;
    color:#0f1724;
    min-height:100vh;
    -webkit-font-smoothing:antialiased;
    -moz-osx-font-smoothing:grayscale;
  }

  /* container */
  .wrap{
    max-width:1200px;
    margin:36px auto;
    padding:28px;
    background: linear-gradient(180deg, rgba(255,255,255,0.95), rgba(255,255,255,0.90));
    border-radius:20px;
    box-shadow:var(--shadow);
    backdrop-filter: blur(6px);
  }

  header.top {
    display:flex;
    gap:18px;
    align-items:center;
    margin-bottom:18px;
  }

  header.top img.logo{
    width:86px;
    height:86px;
    object-fit:cover;
    border-radius:14px;
    border:2px solid rgba(0,0,0,0.05);
    background:#fff;
  }

  header.top .title {
    display:flex;
    flex-direction:column;
  }

  header.top h1{
    margin:0;
    font-size:29px;
    letter-spacing:0.2px;
    color:var(--primary);
  }
  header.top p {
    margin:4px 0 0 0;
    color:var(--muted);
    font-size:14px;
  }

  /* controls */
  .controls{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
    align-items:center;
    margin:18px 0 26px 0;
  }

  .search {
    flex:1 1 360px;
    display:flex;
    gap:8px;
    align-items:center;
    background:var(--card);
    border-radius:12px;
    padding:8px 12px;
    box-shadow:0 3px 8px rgba(2,6,23,0.04);
  }
  .search input{
    border:0;
    outline:0;
    font-size:15px;
    width:100%;
    background:transparent;
    padding:10px 2px;
  }

  .filters {
    display:flex;
    gap:8px;
    align-items:center;
  }
  select, button {
    padding:10px 12px;
    border-radius:10px;
    border:1px solid rgba(15,23,42,0.06);
    background:white;
    font-size:14px;
  }
  button.primary{
    background:var(--primary);
    color:white;
    border:0;
  }

  /* subjects nav */
  .subjects {
    display:flex;
    gap:10px;
    flex-wrap:wrap;
    margin-bottom:18px;
  }
  .chip {
    padding:8px 12px;
    border-radius:999px;
    background:rgba(15,98,254,0.08);
    color:var(--primary);
    font-weight:600;
    cursor:pointer;
    user-select:none;
  }
  .chip.active {
    background:var(--primary);
    color:white;
    box-shadow:0 6px 18px rgba(15,98,254,0.14);
  }

  /* grid */
  .grid {
    display:grid;
    grid-template-columns:repeat(auto-fill,minmax(220px,1fr));
    gap:18px;
  }

  .card {
    background:var(--card);
    border-radius:12px;
    overflow:hidden;
    box-shadow:var(--shadow);
    transition:transform .14s ease, box-shadow .14s ease;
  }
  .card:hover{ transform: translateY(-6px); box-shadow: 0 12px 30px rgba(2,6,23,0.09); }

  .cover {
    height:300px;
    width:100%;
    display:block;
    object-fit:cover;
    background:#f3f4f6;
  }

  .meta {
    padding:14px;
  }
  .meta h3 {
    margin:0 0 6px 0;
    font-size:16px;
    color:#0f1724;
  }
  .meta p {
    margin:0;
    font-size:13px;
    color:var(--muted);
  }
  .meta .row {
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-top:12px;
    gap:10px;
  }
  .meta a.download{
    padding:8px 10px;
    border-radius:8px;
    background:var(--accent);
    color:white;
    text-decoration:none;
    font-weight:600;
    font-size:13px;
  }
  .meta button.info {
    padding:8px 10px;
    border-radius:8px;
    border:1px solid rgba(2,6,23,0.06);
    background:transparent;
    cursor:pointer;
  }

  /* modal */
  .modal-backdrop{
    position:fixed;
    inset:0;
    display:none;
    align-items:center;
    justify-content:center;
    background:rgba(2,6,23,0.45);
    z-index:1200;
  }
  .modal-backdrop.open{ display:flex; }
  .modal {
    width:min(760px,94%);
    background:white;
    border-radius:12px;
    padding:18px;
    box-shadow:0 18px 50px rgba(2,6,23,0.3);
    display:flex;
    gap:16px;
  }
  .modal img { width:180px; height:240px; object-fit:cover; border-radius:8px; }
  .modal .md {
    flex:1;
  }
  .modal h2 { margin:0 0 8px 0; color:var(--primary); }
  .modal p { color:var(--muted); font-size:14px; }
  .modal .actions { margin-top:12px; display:flex; gap:10px; }

  /* responsive */
  @media (max-width:720px){
    header.top { flex-direction:row; gap:12px; }
    .modal { flex-direction:column; align-items:center; text-align:center; }
    .modal img{ width:60%; height:auto; }
  }

  footer { margin-top:22px; text-align:center; color:var(--muted); font-size:13px; padding:12px 0; }
</style>
</head>

<body>
  <div class="wrap" role="main">
    <header class="top" aria-label="CASAP E-LIBRO header">
      <!-- swap the placeholder logo with your real logo: images/casap-logo.png -->
      <img class="logo" src="img-casap.jpg" width: 50px; height: 50px; alt="CASAP Logo">
      <div class="title">
        <h1>CASAP E-LIBRO</h1>
        <p>Center for Academic Support and Program — Student Resources</p>
      </div>
    </header>

    <!-- Controls: search + filters -->
    <div class="controls" role="region" aria-label="Search and filters">
      <div class="search" title="Search books by title or author">
        <svg width="18" height="18" viewBox="0 0 24 24" fill="none" style="opacity:.6">
          <path d="M21 21l-4.35-4.35" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M11 19a8 8 0 1 1 0-16 8 8 0 0 1 0 16z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <input id="search" type="search" placeholder="Search by title or author..." aria-label="Search books">
      </div>

      <div class="filters">
        <select id="subjectFilter" aria-label="Filter by subject">
          <option value="all">All subjects</option>
          <option value="English">English</option>
          <option value="Mathematics">Mathematics</option>
          <option value="Science">Science</option>
          <option value="ICT">ICT / Computer</option>
          <option value="History">History</option>
          <option value="Filipino">Filipino</option>
        </select>

        <button id="resetBtn" title="Reset filters">Reset</button>
      </div>
    </div>

    <!-- Subjects quick chips -->
    <nav class="subjects" aria-label="Subjects">
      <div class="chip active" data-subject="all">All</div>
      <div class="chip" data-subject="English">English</div>
      <div class="chip" data-subject="Mathematics">Mathematics</div>
      <div class="chip" data-subject="Science">Science</div>
      <div class="chip" data-subject="ICT">ICT</div>
      <div class="chip" data-subject="History">History</div>
      <div class="chip" data-subject="Filipino">Filipino</div>
    </nav>

    <!-- Book grid -->
    <section class="grid" id="grid" aria-label="Book list">
      <!-- Sample cards. Replace hrefs with your PDFs at books/<filename>.pdf and covers in images/ -->
      <!-- Card 1 -->
      <article class="card" data-title="Englsh Grammar Basics" data-author="John Adams" data-subject="English" tabindex="0">
        <img class="cover" src="img2-jpg.webp" alt="English Grammar Basics cover">
        <div class="meta">
          <h3>English Grammar Basics</h3>
          <p>John Adams · English</p>
          <div class="row">
            <button class="info" data-file="English-grammar.pdf" data-cover="img2-jpg.webp" data-title="English Grammar Basics" data-author="John Adams" data-desc="A concise guide to English grammar for learners.">Info</button>
            <a class="download" href="English-grammar.pdf" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 2 -->
      <article class="card" data-title="Literature Classics" data-author="Emily Rose" data-subject="English" tabindex="0">
        <img class="cover" src="img-3.jpg" alt="Literature Classics cover">
        <div class="meta">
          <h3>Literature Classics</h3>
          <p>Emily Rose · English</p>
          <div class="row">
            <button class="info" data-file="Literature.pdf" data-cover="img-3.jpg" data-title="Literature Classics" data-author="Emily Rose" data-desc="Selected classic literature pieces for study.">Info</button>
            <a class="download" href="Literature.pdf" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 3 -->
      <article class="card" data-title="General Mathematics" data-author="Dr. Smith" data-subject="Mathematics" tabindex="0">
        <img class="cover" src="gen-math.jpg" alt="General Mathematics cover">
        <div class="meta">
          <h3>General Mathematics</h3>
          <p>Dr. Smith · Mathematics</p>
          <div class="row">
            <button class="info" data-file="intro-math.pdf" data-cover="gen-math.jpg" data-title="General Mathematics" data-author="Dr. Smith" data-desc="Complete guide covering basic to intermediate math topics.">Info</button>
            <a class="download" href="intro-math.pdf" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 4 -->
      <article class="card" data-title="Algebra & Geometry" data-author="R. Gomez" data-subject="Mathematics" tabindex="0">
        <img class="cover" src="img-algebra-geo.jpg" alt="Algebra & Geometry cover">
        <div class="meta">
          <h3>Algebra & Geometry</h3>
          <p>R. Gomez · Mathematics</p>
          <div class="row">
            <button class="info" data-file="algebra_and_geometry.pdf" data-cover="img-algebra-geo.jpg" data-title="Algebra & Geometry" data-author="R. Gomez" data-desc="Practice problems and theory for algebra and geometry.">Info</button>
            <a class="download" href="algebra_and_geometry.pdf" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 5 -->
      <article class="card" data-title="Earth Science" data-author="L. Martin" data-subject="Science" tabindex="0">
        <img class="cover" src="earth-science.jpg" alt="Earth Science cover">
        <div class="meta">
          <h3>Earth Science</h3>
          <p>L. Martin · Science</p>
          <div class="row">
            <button class="info" data-file="Earth-Science.pdf" data-cover="earth-science.jpg" data-title="Earth Science" data-author="L. Martin" data-desc="Introductory earth science textbook with diagrams and exercises.">Info</button>
            <a class="download" href="Earth-Science.pdf" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 6 -->
      <article class="card" data-title="Biology Essentials" data-author="Dr. Carlos" data-subject="Science" tabindex="0">
        <img class="cover" src="bio-essential.jpg" alt="Biology Essentials cover">
        <div class="meta">
          <h3>Biology Essentials</h3>
          <p>Dr. Carlos · Science</p>
          <div class="row">
            <button class="info" data-file="biology-student-textbook-grade-9_part-1.pdf" data-cover="https://via.placeholder.com/640x960.png?text=Biology+Essentials" data-title="Biology Essentials" data-author="Dr. Carlos" data-desc="Core biology topics for senior high students.">Info</button>
            <a class="download" href="biology-student-textbook-grade-9_part-1.pdf" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 7 -->
      <article class="card" data-title="Intro to Computing" data-author="E. Santos" data-subject="ICT" tabindex="0">
        <img class="cover" src="computing.jpg" alt="Intro to Computing cover">
        <div class="meta">
          <h3>Intro to Computing</h3>
          <p>E. Santos · ICT</p>
          <div class="row">
            <button class="info" data-file="An_Introduction_to_Computing.PDF" data-cover="computing.jpg" data-title="Intro to Computing" data-author="E. Santos" data-desc="Fundamentals of computing and digital literacy.">Info</button>
            <a class="download" href="An_Introduction_to_Computing.PDF" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 8 -->
      <article class="card" data-title="Web Development Basics" data-author="A. Torres" data-subject="ICT" tabindex="0">
        <img class="cover" src="web-develop.jpg" alt="Web Development cover">
        <div class="meta">
          <h3>Web Development Basics</h3>
          <p>A. Torres · ICT</p>
          <div class="row">
            <button class="info" data-file="WebDevelopmentBasics.pdf" data-cover="web-develop.jpg" data-title="Web Development Basics" data-author="A. Torres" data-desc="HTML, CSS, and simple JavaScript projects for beginners.">Info</button>
            <a class="download" href="WebDevelopmentBasics.pdf" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 9 -->
      <article class="card" data-title="Philippine History" data-author="M. Santos" data-subject="History" tabindex="0">
        <img class="cover" src="history-phil.jpg" alt="Philippine History cover">
        <div class="meta">
          <h3>Philippine History</h3>
          <p>M. Santos · History</p>
          <div class="row">
            <button class="info" data-file="Philippine-History.pdf" data-cover="history-phil.jpg" data-title="Philippine History" data-author="M. Santos" data-desc="Overview of major events in Philippine history.">Info</button>
            <a class="download" href="Philippine-History.pdf" download>Download</a>
          </div>
        </div>
      </article>

      <!-- Card 10 -->
      <article class="card" data-title="Araling Panlipunan" data-author="R. dela Cruz" data-subject="Filipino" tabindex="0">
        <img class="cover" src="araling-panlipunan.jpg" alt="Araling Panlipunan cover">
        <div class="meta">
          <h3>Araling Panlipunan</h3>
          <p>R. dela Cruz · Filipino</p>
          <div class="row">
            <button class="info" data-file="Araling_Panlipunan_Social_Studies_in_the_Philippines.pdf" data-cover="araling-panlipunan.jpg" data-title="Araling Panlipunan" data-author="R. dela Cruz" data-desc="Social studies material for junior high.">Info</button>
            <a class="download" href="Araling_Panlipunan_Social_Studies_in_the_Philippines.pdf" download>Download</a>
          </div>
        </div>
      </article>

    </section>
    <footer>
      &copy; 2025 CASAP E-LIBRO. All rights reserved.
    </footer>
  </div>

  <!-- modal -->
  <div id="modalBackdrop" class="modal-backdrop" role="dialog" aria-modal="true" aria-hidden="true">
    <div class="modal" role="document">
      <img id="mdCover" src="img-casap.jpg" alt="Cover">
      <div class="md">
        <h2 id="mdTitle">Title</h2>
        <p id="mdAuthor">Author</p>
        <p id="mdDesc">Description</p>
        <div class="actions">
          <a id="mdDownload" class="download" href="#" download>Download PDF</a>
          <button id="mdClose" class="info">Close</button>
        </div>
      </div>
    </div>
  </div>

<!-- JavaScript: filter, search, modal -->
<script>
  // Elements
  const search = document.getElementById('search');
  const subjectFilter = document.getElementById('subjectFilter');
  const resetBtn = document.getElementById('resetBtn');
  const chips = document.querySelectorAll('.chip');
  const cards = Array.from(document.querySelectorAll('.card'));
  const grid = document.getElementById('grid');

  // Modal elements
  const backdrop = document.getElementById('modalBackdrop');
  const mdCover = document.getElementById('mdCover');
  const mdTitle = document.getElementById('mdTitle');
  const mdAuthor = document.getElementById('mdAuthor');
  const mdDesc = document.getElementById('mdDesc');
  const mdDownload = document.getElementById('mdDownload');
  const mdClose = document.getElementById('mdClose');

  function normalizeText(s){
    return (s||'').toString().toLowerCase().trim();
  }

  // Filter and search function
  function refreshGrid(){
    const q = normalizeText(search.value);
    const subj = subjectFilter.value;

    let anyVisible = false;
    cards.forEach(card=>{
      const title = normalizeText(card.dataset.title);
      const author = normalizeText(card.dataset.author);
      const subject = normalizeText(card.dataset.subject);

      const matchesQuery = q === '' || title.includes(q) || author.includes(q);
      const matchesSubject = subj === 'all' || subject === subj.toLowerCase();

      if(matchesQuery && matchesSubject){
        card.style.display = '';
        anyVisible = true;
      } else {
        card.style.display = 'none';
      }
    });

    // If nothing matches, show a helpful message
    if(!anyVisible){
      if(!document.getElementById('noResults')){
        const el = document.createElement('div');
        el.id = 'noResults';
        el.style.gridColumn = '1/-1';
        el.style.textAlign = 'center';
        el.style.color = '#374151';
        el.style.padding = '30px 10px';
        el.textContent = 'No books found. Try a different search or subject.';
        grid.appendChild(el);
      }
    } else {
      const existing = document.getElementById('noResults');
      if(existing) existing.remove();
    }
  }

  // Event listeners
  search.addEventListener('input', refreshGrid);
  subjectFilter.addEventListener('change', e=>{
    // Also update chips visual state
    chips.forEach(c=> c.classList.toggle('active', c.dataset.subject.toLowerCase() === e.target.value.toLowerCase()));
    refreshGrid();
  });

  resetBtn.addEventListener('click', ()=>{
    search.value = '';
    subjectFilter.value = 'all';
    chips.forEach(c=> c.classList.toggle('active', c.dataset.subject === 'all'));
    refreshGrid();
  });

  // chips click -> set subject filter
  chips.forEach(chip=>{
    chip.addEventListener('click', ()=>{
      chips.forEach(c=>c.classList.remove('active'));
      chip.classList.add('active');
      const subj = chip.dataset.subject;
      subjectFilter.value = subj === 'all' ? 'all' : subj;
      refreshGrid();
    });
  });

  // Info modal show
  document.querySelectorAll('.info').forEach(btn=>{
    btn.addEventListener('click', (e)=>{
      const file = btn.dataset.file;
      const cover = btn.dataset.cover;
      const title = btn.dataset.title;
      const author = btn.dataset.author;
      const desc = btn.dataset.desc || '';
      mdCover.src = cover;
      mdCover.alt = title + ' cover';
      mdTitle.textContent = title;
      mdAuthor.textContent = author;
      mdDesc.textContent = desc;
      mdDownload.href = file;
      backdrop.classList.add('open');
      backdrop.setAttribute('aria-hidden','false');
      mdClose.focus();
    });
  });

  // Close modal
  mdClose.addEventListener('click', ()=> {
    backdrop.classList.remove('open');
    backdrop.setAttribute('aria-hidden','true');
  });
  backdrop.addEventListener('click', (e)=>{
    if(e.target === backdrop) { backdrop.classList.remove('open'); backdrop.setAttribute('aria-hidden','true'); }
  });

  // Keyboard escape to close
  document.addEventListener('keydown', (e)=>{
    if(e.key === 'Escape' && backdrop.classList.contains('open')) {
      backdrop.classList.remove('open');
      backdrop.setAttribute('aria-hidden','true');
    }
  });

  // Make cards keyboard accessible (Enter opens info modal)
  cards.forEach(c=>{
    c.addEventListener('keydown', (e)=>{
      if(e.key === 'Enter'){
        const btn = c.querySelector('.info');
        if(btn) btn.click();
      }
    });
  });

  // initialize
  refreshGrid();
</script>
</body>
</html>
