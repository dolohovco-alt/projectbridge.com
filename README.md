# projectbridge.com
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Project Bridge</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Inter:ital,wght@0,400;0,500;0,600;0,700;0,800;1,500&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#FFFDFB;
    --bg-soft:#FFF7F7;
    --ink:#2B2727;
    --ink-soft:#7A7676;
    --line:#F4E3E3;
    --accent:#F46B6B;
    --accent-deep:#DE4F4F;
    --lavender:#DCCEF9;
    --lavender-deep:#8B6FD1;
    --sage:#CFE7D3;
    --sage-deep:#4F9B6A;
    --shadow: 0 4px 16px rgba(244,107,107,0.08);
    --shadow-lift: 0 14px 32px rgba(244,107,107,0.16);
    --ring: 0 0 0 3px rgba(244,107,107,0.3);
  }

  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:var(--bg);
    color:var(--ink);
    font-family:'Inter', sans-serif;
    line-height:1.6;
    min-height:100vh;
    -webkit-font-smoothing:antialiased;
  }
  h1,h2,h3,.display{
    font-family:'Inter', sans-serif;
    color:var(--ink);
    margin:0;
  }
  a{color:var(--accent);}
  button{font-family:inherit;cursor:pointer;}
  :focus-visible{outline:none; box-shadow:var(--ring); border-radius:8px;}

  @media (prefers-reduced-motion: reduce){
    *{animation:none !important; transition:none !important;}
  }

  .wrap{max-width:1140px; margin:0 auto; padding:0 28px;}

  /* ---------- header ---------- */
  header.site{
    border-bottom:1px solid var(--line);
    background:var(--bg);
    position:sticky; top:0; z-index:40;
  }
  header.site .wrap{
    padding:20px 28px;
    display:flex;
    align-items:center;
    justify-content:space-between;
  }
  .logo{display:flex; align-items:center; gap:10px;}
  .logo svg{width:24px;height:24px;flex-shrink:0;}
  .logo span{font-size:18px; font-weight:800; letter-spacing:-0.01em; color:var(--ink);}
  .logo .tag{
    font-size:10.5px;
    font-weight:600;
    color:var(--ink-soft);
    letter-spacing:.1em;
    text-transform:uppercase;
    margin-left:10px;
    padding-left:10px;
    border-left:1px solid var(--line);
  }
  .admin-toggle{
    background:transparent;
    border:1.5px solid var(--accent);
    color:var(--accent);
    font-weight:700;
    padding:9px 20px;
    border-radius:999px;
    font-size:13px;
    letter-spacing:.01em;
    transition:background .15s ease, color .15s ease;
  }
  .admin-toggle:hover{background:var(--accent); color:#fff;}
  .admin-toggle.active{
    background:var(--accent);
    color:white;
  }

  /* ---------- hero ---------- */
  .hero{
    background:var(--bg-soft);
    text-align:center;
    padding:72px 0 56px;
    border-bottom:1px solid var(--line);
  }
  .eyebrow{
    font-size:12.5px;
    font-weight:700;
    letter-spacing:.14em;
    text-transform:uppercase;
    color:var(--sage-deep);
    margin-bottom:18px;
  }
  .hero h1{
    font-size:44px;
    line-height:1.18;
    font-weight:800;
    letter-spacing:-0.01em;
    max-width:760px;
    margin:0 auto;
  }
  .hero p.sub{
    color:var(--ink-soft);
    font-size:17px;
    margin:20px auto 30px;
    max-width:540px;
  }
  .search-row{
    display:flex;
    max-width:480px;
    margin:0 auto;
    border-radius:999px;
    box-shadow:var(--shadow);
    background:var(--bg);
    border:1px solid var(--line);
    overflow:hidden;
  }
  .search-row input{
    flex:1;
    padding:15px 22px;
    border:none;
    background:transparent;
    font-size:14.5px;
    font-family:inherit;
    color:var(--ink);
  }
  .search-row input::placeholder{color:var(--ink-soft);}
  .stats{
    display:flex;
    justify-content:center;
    gap:56px;
    margin-top:46px;
    flex-wrap:wrap;
  }
  .stat b{display:block; font-size:32px; font-weight:800; color:var(--accent);}
  .stat span{font-size:12.5px; color:var(--ink-soft); letter-spacing:.04em; text-transform:uppercase; font-weight:600;}

  /* ---------- filter pills ---------- */
  .filters{
    display:flex;
    justify-content:center;
    gap:10px;
    flex-wrap:wrap;
    padding:36px 0 30px;
  }
  .pill{
    border:1.5px solid var(--line);
    background:var(--bg);
    color:var(--ink-soft);
    font-weight:700;
    font-size:13px;
    padding:9px 17px;
    border-radius:999px;
    transition:all .15s ease;
  }
  .pill:hover{border-color:var(--accent); color:var(--accent);}
  .pill.active{
    background:var(--accent);
    color:white;
    border-color:var(--accent);
  }
  .pill .dot{
    display:inline-block;
    width:7px;height:7px;
    border-radius:50%;
    margin-right:7px;
    vertical-align:middle;
  }

  /* ---------- toolbar ---------- */
  .toolbar{
    display:flex; justify-content:space-between; align-items:center;
    padding-bottom:22px;
    margin-bottom:6px;
  }
  .count-label{font-size:13px; color:var(--ink-soft); font-weight:600;}
  .add-btn{
    background:var(--accent);
    color:white;
    font-weight:700;
    font-size:13.5px;
    padding:11px 22px;
    border-radius:999px;
    border:none;
    box-shadow:var(--shadow);
    display:flex; align-items:center; gap:6px;
    transition:background .15s ease;
  }
  .add-btn:hover{background:var(--accent-deep);}

  /* ---------- grid ---------- */
  .grid{
    display:grid;
    grid-template-columns:repeat(3, 1fr);
    gap:22px;
    margin-bottom:80px;
  }
  .card{
    background:var(--bg-soft);
    border:1px solid var(--line);
    border-radius:16px;
    padding:26px;
    box-shadow:var(--shadow);
    display:flex;
    flex-direction:column;
    gap:11px;
    transition:box-shadow .18s ease, transform .18s ease;
  }
  .card:hover{box-shadow:var(--shadow-lift); transform:translateY(-3px);}
  .tag{
    align-self:flex-start;
    font-size:11px;
    font-weight:700;
    text-transform:uppercase;
    letter-spacing:.06em;
    display:flex;
    align-items:center;
    gap:7px;
  }
  .tag .dot{width:7px;height:7px;border-radius:50%; flex-shrink:0;}
  .card h3{font-size:18.5px; line-height:1.3; font-weight:700;}
  .card .org{font-size:13px; color:var(--ink-soft); font-weight:600; margin-top:-7px;}
  .card .desc{font-size:14px; color:var(--ink-soft); flex:1; line-height:1.58;}
  .card .meta{
    font-size:12px;
    color:var(--ink-soft);
    font-weight:700;
    letter-spacing:.02em;
    padding-top:11px;
    border-top:1px solid var(--line);
    text-transform:uppercase;
  }
  .card-actions{
    display:flex; gap:8px; margin-top:4px; flex-wrap:wrap;
  }
  .card-actions a, .card-actions button{
    font-size:12.5px;
    font-weight:700;
    border-radius:999px;
    padding:9px 16px;
    text-decoration:none;
    border:1.5px solid var(--accent);
    text-align:center;
    background:transparent;
    color:var(--accent);
    transition:background .15s ease, color .15s ease;
  }
  .btn-link{background:var(--accent); color:white; flex:1;}
  .btn-link:hover{background:var(--accent-deep);}
  .btn-edit:hover{background:var(--accent); color:white;}
  .btn-delete{border-color:#C75D6E; color:#C75D6E;}
  .btn-delete:hover{background:#C75D6E; color:white;}

  .empty-state{
    grid-column:1/-1;
    text-align:center;
    padding:70px 20px;
    color:var(--ink-soft);
    background:var(--bg-soft);
    border-radius:16px;
  }
  .empty-state h3{margin-bottom:6px; color:var(--ink); font-size:18px;}

  /* ---------- modal ---------- */
  .overlay{
    position:fixed; inset:0;
    background:rgba(43,39,39,0.45);
    display:none;
    align-items:center; justify-content:center;
    padding:20px;
    z-index:50;
  }
  .overlay.show{display:flex;}
  .modal{
    background:var(--bg);
    border-radius:18px;
    padding:34px;
    max-width:480px;
    width:100%;
    max-height:88vh;
    overflow-y:auto;
    box-shadow:var(--shadow-lift);
  }
  .modal h2{font-size:21px; margin-bottom:4px; font-weight:800;}
  .modal-note{font-size:13px; color:var(--ink-soft); margin:0 0 18px;}
  .field{margin-bottom:16px;}
  .field label{
    display:block;
    font-size:12px;
    font-weight:700;
    text-transform:uppercase;
    letter-spacing:.04em;
    color:var(--ink-soft);
    margin-bottom:7px;
  }
  .field input, .field select, .field textarea{
    width:100%;
    padding:11px 14px;
    border-radius:10px;
    border:1.5px solid var(--line);
    font-family:inherit;
    font-size:14px;
    color:var(--ink);
    background:white;
  }
  .field textarea{resize:vertical; min-height:70px;}
  .modal-actions{display:flex; gap:10px; margin-top:20px;}
  .modal-actions button{
    flex:1;
    padding:13px;
    border-radius:999px;
    font-weight:700;
    font-size:14px;
    border:1.5px solid var(--accent);
  }
  .btn-save{background:var(--accent); color:white;}
  .btn-save:hover{background:var(--accent-deep);}
  .btn-cancel{background:transparent; color:var(--accent);}
  .btn-cancel:hover{background:var(--accent); color:white;}

  .passcode-box{
    display:flex; gap:8px; margin-top:10px;
  }
  .passcode-box input{
    flex:1;
    padding:11px 14px;
    border-radius:10px;
    border:1.5px solid var(--line);
    font-size:14px;
  }
  .passcode-box button{
    background:var(--accent); color:white; border:1.5px solid var(--accent);
    border-radius:999px; padding:11px 18px; font-weight:700; font-size:13px;
  }

  footer{
    text-align:center;
    padding:36px 20px 56px;
    color:var(--ink-soft);
    font-size:12.5px;
    border-top:1px solid var(--line);
    letter-spacing:.01em;
  }

  .toast{
    position:fixed;
    bottom:24px; left:50%;
    transform:translateX(-50%) translateY(20px);
    background:var(--ink);
    color:white;
    padding:13px 24px;
    border-radius:999px;
    font-size:13.5px;
    font-weight:600;
    opacity:0;
    pointer-events:none;
    transition:all .25s ease;
    z-index:100;
  }
  .toast.show{opacity:1; transform:translateX(-50%) translateY(0);}

  @media (max-width: 880px){
    .grid{grid-template-columns:repeat(2,1fr);}
    .hero h1{font-size:34px;}
    .stats{gap:34px;}
  }
  @media (max-width: 600px){
    .grid{grid-template-columns:1fr;}
    .hero h1{font-size:28px;}
    header.site .wrap{flex-direction:column; gap:14px; align-items:flex-start;}
    .stats{gap:24px;}
  }
</style>
</head>
<body>

<header class="site">
  <div class="wrap">
    <div class="logo">
      <svg viewBox="0 0 48 48" fill="none">
        <path d="M4 32 C4 18, 14 9, 24 9 C34 9, 44 18, 44 32" stroke="#F46B6B" stroke-width="2.6" stroke-linecap="round"/>
        <line x1="4" y1="32" x2="4" y2="38" stroke="#2B2727" stroke-width="2.4" stroke-linecap="round"/>
        <line x1="44" y1="32" x2="44" y2="38" stroke="#2B2727" stroke-width="2.4" stroke-linecap="round"/>
        <circle cx="24" cy="9" r="2.8" fill="#CFE7D3" stroke="#4F9B6A" stroke-width="1.2"/>
      </svg>
      <span>PROJECT BRIDGE</span>
      <span class="tag">Opportunity Index</span>
    </div>
    <button class="admin-toggle" id="adminToggleBtn">Admin Mode</button>
  </div>
</header>

<section class="hero">
  <div class="wrap">
    <div class="eyebrow">A Student-Built Resource</div>
    <h1>Connecting every student to <span style="color:var(--accent);">the opportunity they deserve</span></h1>
    <p class="sub">A single, growing database of scholarships, summer programs, competitions, and fellowships — built so that access never depends on privilege.</p>
    <div class="search-row">
      <input type="text" id="searchInput" placeholder="Search by name, subject, or keyword...">
    </div>
    <div class="stats">
      <div class="stat"><b id="statTotal">0</b><span>Opportunities Listed</span></div>
      <div class="stat"><b id="statCats">0</b><span>Categories</span></div>
      <div class="stat"><b>$0</b><span>Cost to Use</span></div>
    </div>
  </div>
</section>

<div class="wrap">

  <section class="filters" id="filterRow">
    <!-- filled by JS -->
  </section>

  <div class="toolbar">
    <span class="count-label" id="countLabel">Showing 0 opportunities</span>
    <button class="add-btn" id="addBtn" style="display:none;">+ Add Opportunity</button>
  </div>

  <section class="grid" id="grid">
    <!-- filled by JS -->
  </section>

</div>

<footer>Project Bridge — a student-made database of opportunities, open to everyone.</footer>

<!-- Add / Edit modal -->
<div class="overlay" id="formOverlay">
  <div class="modal">
    <h2 id="formTitle">Add an Opportunity</h2>
    <p class="modal-note">Fields marked with the link will be clickable on the card.</p>
    <form id="oppForm">
      <div class="field">
        <label for="f_title">Title</label>
        <input type="text" id="f_title" required placeholder="e.g. Coca-Cola Scholars Program">
      </div>
      <div class="field">
        <label for="f_org">Organization</label>
        <input type="text" id="f_org" required placeholder="Who runs it?">
      </div>
      <div class="field">
        <label for="f_category">Category</label>
        <select id="f_category">
          <option>Scholarships</option>
          <option>Summer Programs</option>
          <option>Competitions</option>
          <option>Fellowships</option>
          <option>Internships</option>
          <option>Grants</option>
        </select>
      </div>
      <div class="field">
        <label for="f_deadline">Deadline</label>
        <input type="text" id="f_deadline" placeholder="e.g. March 1, 2027 or Rolling">
      </div>
      <div class="field">
        <label for="f_desc">Short Description</label>
        <textarea id="f_desc" placeholder="Who is it for, and what does it offer?"></textarea>
      </div>
      <div class="field">
        <label for="f_link">Link to Apply</label>
        <input type="text" id="f_link" placeholder="https://...">
      </div>
      <div class="modal-actions">
        <button type="button" class="btn-cancel" id="cancelBtn">Cancel</button>
        <button type="submit" class="btn-save" id="saveBtn">Save</button>
      </div>
    </form>
  </div>
</div>

<!-- Admin passcode modal -->
<div class="overlay" id="passOverlay">
  <div class="modal" style="max-width:360px;">
    <h2>Enter Admin Passcode</h2>
    <p class="modal-note">This unlocks add, edit, and delete. Set your own passcode by editing <code>ADMIN_PASSCODE</code> in the file.</p>
    <div class="passcode-box">
      <input type="password" id="passInput" placeholder="Passcode">
      <button id="passSubmit">Unlock</button>
    </div>
    <div class="modal-actions">
      <button type="button" class="btn-cancel" id="passCancel">Cancel</button>
    </div>
  </div>
</div>

<div class="toast" id="toast"></div>

<script>
const ADMIN_PASSCODE = "bridge2026"; // change this to your own passcode
const STORAGE_KEY = "opportunities-list";

const CATEGORY_COLORS = {
  "Scholarships":   { fg:"#F46B6B" },
  "Summer Programs":{ fg:"#4F9B6A" },
  "Competitions":   { fg:"#D9534F" },
  "Fellowships":    { fg:"#8B6FD1" },
  "Internships":    { fg:"#C76B8A" },
  "Grants":         { fg:"#C98A5C" }
};
const CATEGORIES = Object.keys(CATEGORY_COLORS);

let opportunities = [];
let activeCategory = "All";
let searchTerm = "";
let isAdmin = false;
let editingId = null;

const grid = document.getElementById("grid");
const filterRow = document.getElementById("filterRow");
const countLabel = document.getElementById("countLabel");
const statTotal = document.getElementById("statTotal");
const statCats = document.getElementById("statCats");
const toast = document.getElementById("toast");

function showToast(msg){
  toast.textContent = msg;
  toast.classList.add("show");
  setTimeout(()=> toast.classList.remove("show"), 2200);
}

function seedData(){
  return [
    {id:"1", title:"Sample Scholarship", org:"Example Foundation", category:"Scholarships", deadline:"Edit this date", description:"This is placeholder content. Click Edit (in admin mode) to replace it with a real scholarship: who can apply, what it covers, and the deadline.", link:""},
    {id:"2", title:"Sample Summer Program", org:"Example University", category:"Summer Programs", deadline:"Edit this date", description:"Placeholder card — swap in a real summer program with its subject area, cost, and application window.", link:""},
    {id:"3", title:"Sample Competition", org:"Example Society", category:"Competitions", deadline:"Edit this date", description:"Placeholder card — replace with a real competition, including eligibility and prizes.", link:""},
    {id:"4", title:"Sample Fellowship", org:"Example Institute", category:"Fellowships", deadline:"Edit this date", description:"Placeholder card — replace with a real fellowship and who it's meant for.", link:""},
    {id:"5", title:"Sample Internship", org:"Example Company", category:"Internships", deadline:"Edit this date", description:"Placeholder card — replace with a real internship listing.", link:""},
    {id:"6", title:"Sample Grant", org:"Example Trust", category:"Grants", deadline:"Edit this date", description:"Placeholder card — replace with a real grant opportunity.", link:""}
  ];
}

async function loadData(){
  try{
    const result = await window.storage.get(STORAGE_KEY, true);
    opportunities = result ? JSON.parse(result.value) : seedData();
    if(!result){
      await window.storage.set(STORAGE_KEY, JSON.stringify(opportunities), true);
    }
  }catch(e){
    opportunities = seedData();
    try{ await window.storage.set(STORAGE_KEY, JSON.stringify(opportunities), true); }catch(e2){}
  }
  renderFilters();
  renderGrid();
}

async function persist(){
  try{
    await window.storage.set(STORAGE_KEY, JSON.stringify(opportunities), true);
  }catch(e){
    showToast("Couldn't save — try again");
  }
}

function renderFilters(){
  let html = `<button class="pill ${activeCategory==='All' ? 'active':''}" data-cat="All">All</button>`;
  CATEGORIES.forEach(cat=>{
    const c = CATEGORY_COLORS[cat];
    html += `<button class="pill ${activeCategory===cat ? 'active':''}" data-cat="${cat}"><span class="dot" style="background:${c.fg}"></span>${cat}</button>`;
  });
  filterRow.innerHTML = html;
  filterRow.querySelectorAll(".pill").forEach(btn=>{
    btn.addEventListener("click", ()=>{
      activeCategory = btn.dataset.cat;
      renderFilters();
      renderGrid();
    });
  });
}

function getFiltered(){
  return opportunities.filter(o=>{
    const matchesCat = activeCategory === "All" || o.category === activeCategory;
    const term = searchTerm.toLowerCase();
    const matchesSearch = !term ||
      o.title.toLowerCase().includes(term) ||
      o.org.toLowerCase().includes(term) ||
      (o.description||"").toLowerCase().includes(term);
    return matchesCat && matchesSearch;
  });
}

function escapeHtml(str){
  const div = document.createElement("div");
  div.textContent = str || "";
  return div.innerHTML;
}

function renderGrid(){
  const filtered = getFiltered();
  statTotal.textContent = opportunities.length;
  statCats.textContent = new Set(opportunities.map(o=>o.category)).size;
  countLabel.textContent = `Showing ${filtered.length} opportunit${filtered.length===1?'y':'ies'}`;

  if(filtered.length === 0){
    grid.innerHTML = `<div class="empty-state">
      <h3>No matches yet</h3>
      <p>Try a different search term or category${isAdmin ? ', or add a new opportunity.' : '.'}</p>
    </div>`;
    return;
  }

  grid.innerHTML = filtered.map(o=>{
    const c = CATEGORY_COLORS[o.category] || CATEGORY_COLORS["Scholarships"];
    const linkHtml = o.link
      ? `<a class="btn-link" href="${escapeHtml(o.link)}" target="_blank" rel="noopener">View &amp; Apply</a>`
      : `<span class="btn-link" style="opacity:.4; cursor:default;">No Link Yet</span>`;
    const adminButtons = isAdmin ? `
      <button class="btn-edit" data-action="edit" data-id="${o.id}">Edit</button>
      <button class="btn-delete" data-action="delete" data-id="${o.id}">Delete</button>` : "";
    return `<div class="card">
      <span class="tag" style="color:${c.fg};"><span class="dot" style="background:${c.fg}"></span>${escapeHtml(o.category)}</span>
      <h3>${escapeHtml(o.title)}</h3>
      <div class="org">${escapeHtml(o.org)}</div>
      <div class="desc">${escapeHtml(o.description)}</div>
      <div class="meta">Deadline — ${escapeHtml(o.deadline || "Not listed")}</div>
      <div class="card-actions">
        ${linkHtml}
        ${adminButtons}
      </div>
    </div>`;
  }).join("");

  grid.querySelectorAll('[data-action="edit"]').forEach(btn=>{
    btn.addEventListener("click", ()=> openForm(btn.dataset.id));
  });
  grid.querySelectorAll('[data-action="delete"]').forEach(btn=>{
    btn.addEventListener("click", ()=> deleteOpp(btn.dataset.id));
  });
}

/* ---------- search ---------- */
document.getElementById("searchInput").addEventListener("input", (e)=>{
  searchTerm = e.target.value;
  renderGrid();
});

/* ---------- admin toggle ---------- */
const adminToggleBtn = document.getElementById("adminToggleBtn");
const passOverlay = document.getElementById("passOverlay");
const passInput = document.getElementById("passInput");

adminToggleBtn.addEventListener("click", ()=>{
  if(isAdmin){
    isAdmin = false;
    adminToggleBtn.classList.remove("active");
    adminToggleBtn.textContent = "Admin Mode";
    document.getElementById("addBtn").style.display = "none";
    renderGrid();
  }else{
    passInput.value = "";
    passOverlay.classList.add("show");
    passInput.focus();
  }
});

document.getElementById("passCancel").addEventListener("click", ()=>{
  passOverlay.classList.remove("show");
});
document.getElementById("passSubmit").addEventListener("click", submitPasscode);
passInput.addEventListener("keydown", (e)=>{ if(e.key==="Enter") submitPasscode(); });

function submitPasscode(){
  if(passInput.value === ADMIN_PASSCODE){
    isAdmin = true;
    adminToggleBtn.classList.add("active");
    adminToggleBtn.textContent = "Admin Mode: On";
    document.getElementById("addBtn").style.display = "flex";
    passOverlay.classList.remove("show");
    showToast("Admin mode unlocked");
    renderGrid();
  }else{
    showToast("Wrong passcode");
  }
}

/* ---------- add / edit form ---------- */
const formOverlay = document.getElementById("formOverlay");
const oppForm = document.getElementById("oppForm");
const formTitle = document.getElementById("formTitle");

document.getElementById("addBtn").addEventListener("click", ()=> openForm(null));
document.getElementById("cancelBtn").addEventListener("click", closeForm);

function openForm(id){
  editingId = id;
  if(id){
    const o = opportunities.find(x=>x.id===id);
    formTitle.textContent = "Edit Opportunity";
    document.getElementById("f_title").value = o.title;
    document.getElementById("f_org").value = o.org;
    document.getElementById("f_category").value = o.category;
    document.getElementById("f_deadline").value = o.deadline;
    document.getElementById("f_desc").value = o.description;
    document.getElementById("f_link").value = o.link;
  }else{
    formTitle.textContent = "Add an Opportunity";
    oppForm.reset();
  }
  formOverlay.classList.add("show");
}

function closeForm(){
  formOverlay.classList.remove("show");
  editingId = null;
}

oppForm.addEventListener("submit", async (e)=>{
  e.preventDefault();
  const data = {
    title: document.getElementById("f_title").value.trim(),
    org: document.getElementById("f_org").value.trim(),
    category: document.getElementById("f_category").value,
    deadline: document.getElementById("f_deadline").value.trim(),
    description: document.getElementById("f_desc").value.trim(),
    link: document.getElementById("f_link").value.trim()
  };
  if(editingId){
    const idx = opportunities.findIndex(x=>x.id===editingId);
    opportunities[idx] = { ...opportunities[idx], ...data };
    showToast("Opportunity updated");
  }else{
    data.id = Date.now().toString();
    opportunities.unshift(data);
    showToast("Opportunity added");
  }
  await persist();
  closeForm();
  renderFilters();
  renderGrid();
});

async function deleteOpp(id){
  if(!confirm("Delete this opportunity? This can't be undone.")) return;
  opportunities = opportunities.filter(o=>o.id!==id);
  await persist();
  showToast("Opportunity deleted");
  renderFilters();
  renderGrid();
}

loadData();
</script>

</body>
</html>
