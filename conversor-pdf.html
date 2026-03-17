<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>DocToPDF — Conversor de Documentos</title>
  <link href="https://fonts.googleapis.com/css2?family=DM+Serif+Display:ital@0;1&family=DM+Mono:wght@400;500&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet"/>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jspdf/2.5.1/jspdf.umd.min.js"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/mammoth/1.6.0/mammoth.browser.min.js"></script>
  <style>
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

    :root {
      --ink:     #0d0d0d;
      --paper:   #f5f0e8;
      --cream:   #ede8db;
      --accent:  #c84b31;
      --warm:    #e8b86d;
      --muted:   #7a7060;
      --border:  #d0c9b8;
      --white:   #ffffff;
      --shadow:  0 4px 24px rgba(13,13,13,.10);
      --radius:  14px;
    }

    html, body {
      min-height: 100vh;
      background: var(--paper);
      color: var(--ink);
      font-family: 'DM Sans', sans-serif;
      font-weight: 300;
    }

    /* ── BACKGROUND TEXTURE ── */
    body::before {
      content: '';
      position: fixed; inset: 0;
      background-image:
        repeating-linear-gradient(0deg, transparent, transparent 39px, var(--border) 39px, var(--border) 40px),
        repeating-linear-gradient(90deg, transparent, transparent 39px, var(--border) 39px, var(--border) 40px);
      opacity: .18;
      pointer-events: none;
      z-index: 0;
    }

    /* ── HEADER ── */
    header {
      position: relative; z-index: 1;
      padding: 3.5rem 2rem 2rem;
      text-align: center;
      border-bottom: 2px solid var(--ink);
    }
    .logo-badge {
      display: inline-flex; align-items: center; gap: .5rem;
      background: var(--ink); color: var(--paper);
      font-family: 'DM Mono', monospace; font-size: .72rem; letter-spacing: .12em;
      padding: .35rem .9rem; border-radius: 99px;
      margin-bottom: 1.2rem;
    }
    .logo-badge span { opacity: .55; }
    h1 {
      font-family: 'DM Serif Display', serif;
      font-size: clamp(2.8rem, 6vw, 5rem);
      line-height: 1.05;
      letter-spacing: -.02em;
    }
    h1 em { font-style: italic; color: var(--accent); }
    .sub {
      margin-top: .8rem;
      color: var(--muted);
      font-size: 1.05rem;
      font-weight: 400;
    }

    /* ── MAIN LAYOUT ── */
    main {
      position: relative; z-index: 1;
      max-width: 900px;
      margin: 0 auto;
      padding: 3rem 1.5rem 5rem;
      display: grid;
      gap: 2rem;
    }

    /* ── CARD ── */
    .card {
      background: var(--white);
      border: 1.5px solid var(--border);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      padding: 2rem 2.2rem;
    }
    .card-title {
      font-family: 'DM Serif Display', serif;
      font-size: 1.35rem;
      margin-bottom: 1.2rem;
      display: flex; align-items: center; gap: .6rem;
    }
    .card-title .dot { width: 10px; height: 10px; border-radius: 50%; background: var(--accent); }

    /* ── DROP ZONE ── */
    #dropzone {
      border: 2.5px dashed var(--border);
      border-radius: 10px;
      padding: 3.2rem 2rem;
      text-align: center;
      cursor: pointer;
      transition: border-color .2s, background .2s;
      position: relative;
    }
    #dropzone:hover, #dropzone.dragover {
      border-color: var(--accent);
      background: #fff5f3;
    }
    #dropzone input[type=file] {
      position: absolute; inset: 0; opacity: 0; cursor: pointer;
    }
    .dz-icon { font-size: 2.8rem; margin-bottom: .8rem; display: block; }
    .dz-label {
      font-size: 1.05rem; font-weight: 500;
      color: var(--ink);
    }
    .dz-sub {
      font-size: .82rem; color: var(--muted);
      margin-top: .4rem;
    }
    .dz-badge {
      display: inline-block;
      background: var(--cream); border: 1px solid var(--border);
      border-radius: 6px; padding: .2rem .55rem;
      font-family: 'DM Mono', monospace; font-size: .72rem;
      color: var(--muted); margin: .6rem .2rem 0;
    }

    /* ── FILE INFO ── */
    #file-info {
      display: none;
      align-items: center; gap: 1rem;
      margin-top: 1.2rem;
      padding: .9rem 1.1rem;
      background: #f9f6f0;
      border: 1px solid var(--border);
      border-radius: 8px;
    }
    .fi-icon { font-size: 1.8rem; }
    .fi-meta { flex: 1; }
    .fi-name { font-weight: 600; font-size: .92rem; word-break: break-all; }
    .fi-size { font-size: .78rem; color: var(--muted); margin-top: .15rem; }
    .fi-remove {
      background: none; border: none; cursor: pointer;
      color: var(--muted); font-size: 1.2rem; padding: .3rem;
      border-radius: 6px; transition: color .15s, background .15s;
    }
    .fi-remove:hover { color: var(--accent); background: #fef0ee; }

    /* ── OPTIONS ── */
    .options-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 1.1rem;
    }
    @media (max-width: 540px) { .options-grid { grid-template-columns: 1fr; } }

    .opt-group label {
      display: block;
      font-size: .8rem; font-weight: 600; letter-spacing: .05em;
      text-transform: uppercase; color: var(--muted);
      margin-bottom: .45rem;
    }
    .opt-group select, .opt-group input[type=text] {
      width: 100%;
      padding: .55rem .85rem;
      border: 1.5px solid var(--border);
      border-radius: 8px;
      background: var(--paper);
      font-family: 'DM Sans', sans-serif;
      font-size: .9rem;
      color: var(--ink);
      appearance: none;
      outline: none;
      transition: border-color .2s;
    }
    .opt-group select:focus, .opt-group input[type=text]:focus {
      border-color: var(--accent);
    }
    .select-wrap { position: relative; }
    .select-wrap::after {
      content: '▾'; position: absolute; right: .85rem; top: 50%;
      transform: translateY(-50%); pointer-events: none;
      color: var(--muted); font-size: .8rem;
    }

    .toggle-row {
      display: flex; align-items: center; justify-content: space-between;
      margin-top: 1.1rem;
    }
    .toggle-row label { font-size: .9rem; font-weight: 500; cursor: pointer; }
    .toggle {
      position: relative; width: 44px; height: 24px;
      flex-shrink: 0;
    }
    .toggle input { opacity: 0; width: 0; height: 0; }
    .toggle-slider {
      position: absolute; inset: 0;
      background: var(--border); border-radius: 99px;
      transition: background .2s; cursor: pointer;
    }
    .toggle-slider::before {
      content: ''; position: absolute;
      width: 18px; height: 18px; left: 3px; top: 3px;
      background: white; border-radius: 50%;
      transition: transform .2s;
    }
    .toggle input:checked + .toggle-slider { background: var(--accent); }
    .toggle input:checked + .toggle-slider::before { transform: translateX(20px); }

    /* ── CONVERT BUTTON ── */
    #convert-btn {
      width: 100%;
      padding: 1.1rem;
      background: var(--ink);
      color: var(--paper);
      border: none; border-radius: 10px;
      font-family: 'DM Serif Display', serif;
      font-size: 1.3rem; letter-spacing: .01em;
      cursor: pointer;
      display: flex; align-items: center; justify-content: center; gap: .7rem;
      transition: background .2s, transform .1s;
    }
    #convert-btn:hover { background: #2a2a2a; }
    #convert-btn:active { transform: scale(.99); }
    #convert-btn:disabled { opacity: .45; cursor: not-allowed; }
    #convert-btn .btn-arrow { font-size: 1.5rem; }

    /* ── PROGRESS ── */
    #progress-wrap {
      display: none;
      flex-direction: column; gap: .6rem;
    }
    .prog-label {
      display: flex; justify-content: space-between;
      font-size: .82rem; color: var(--muted);
    }
    .prog-bar {
      height: 6px; background: var(--cream); border-radius: 99px; overflow: hidden;
    }
    .prog-fill {
      height: 100%; background: var(--accent);
      border-radius: 99px;
      width: 0; transition: width .3s ease;
    }
    .prog-msg { font-size: .85rem; color: var(--muted); font-style: italic; }

    /* ── RESULT ── */
    #result-area {
      display: none;
      gap: 1rem;
    }
    .result-success {
      display: flex; align-items: center; gap: 1rem;
      padding: 1.1rem 1.3rem;
      background: #f0faf4;
      border: 1.5px solid #7ec8a0;
      border-radius: 10px;
    }
    .result-icon { font-size: 2rem; }
    .result-info .result-title { font-weight: 600; font-size: .95rem; }
    .result-info .result-sub { font-size: .82rem; color: var(--muted); margin-top: .15rem; }

    #download-btn {
      display: flex; align-items: center; justify-content: center; gap: .6rem;
      width: 100%;
      padding: .9rem;
      background: var(--accent);
      color: white;
      border: none; border-radius: 10px;
      font-family: 'DM Sans', sans-serif;
      font-weight: 600; font-size: 1rem;
      cursor: pointer; text-decoration: none;
      transition: background .2s;
    }
    #download-btn:hover { background: #b03a22; }

    #convert-again {
      width: 100%; padding: .65rem;
      background: none; border: 1.5px solid var(--border);
      border-radius: 10px;
      font-family: 'DM Sans', sans-serif; font-size: .9rem;
      color: var(--muted); cursor: pointer;
      transition: border-color .2s, color .2s;
    }
    #convert-again:hover { border-color: var(--ink); color: var(--ink); }

    /* ── ERROR ── */
    .alert-error {
      display: none;
      align-items: flex-start; gap: .8rem;
      padding: .95rem 1.2rem;
      background: #fff5f3;
      border: 1.5px solid #f5a898;
      border-radius: 10px;
      font-size: .88rem;
      color: #8b2a1a;
    }
    .alert-error .ae-icon { font-size: 1.2rem; flex-shrink: 0; }

    /* ── FORMATS TABLE ── */
    .formats-list {
      display: flex; flex-wrap: wrap; gap: .5rem;
      margin-top: .5rem;
    }
    .fmt-tag {
      padding: .3rem .75rem;
      background: var(--cream); border: 1px solid var(--border);
      border-radius: 99px;
      font-family: 'DM Mono', monospace; font-size: .78rem;
      color: var(--muted);
    }
    .fmt-tag.supported { background: #f0faf4; border-color: #7ec8a0; color: #2d7a52; }

    /* ── FOOTER ── */
    footer {
      position: relative; z-index: 1;
      text-align: center;
      padding: 1.5rem;
      font-size: .78rem; color: var(--muted);
      border-top: 1px solid var(--border);
    }
    footer strong { color: var(--ink); }

    /* ── PREVIEW ── */
    #preview-area { display: none; margin-top: 1.2rem; }
    #preview-content {
      max-height: 220px; overflow-y: auto;
      padding: 1rem 1.2rem;
      background: var(--paper);
      border: 1px solid var(--border);
      border-radius: 8px;
      font-size: .84rem; line-height: 1.65;
      color: var(--ink);
      white-space: pre-wrap; word-break: break-word;
    }
    .preview-label {
      font-size: .78rem; font-weight: 600; letter-spacing: .06em;
      text-transform: uppercase; color: var(--muted);
      margin-bottom: .5rem;
    }

    @keyframes spin { to { transform: rotate(360deg); } }
    .spinner { display: inline-block; animation: spin .8s linear infinite; }
  </style>
</head>
<body>

<header>
  <div class="logo-badge">✦ <span>DocToPDF</span> v1.0</div>
  <h1>Convierte a <em>PDF</em><br>al instante</h1>
  <p class="sub">TXT · DOCX · HTML · Markdown → PDF — todo en tu navegador</p>
</header>

<main>

  <!-- UPLOAD CARD -->
  <div class="card">
    <div class="card-title"><span class="dot"></span> Selecciona tu documento</div>

    <div id="dropzone">
      <input type="file" id="file-input" accept=".txt,.docx,.html,.htm,.md,.markdown"/>
      <span class="dz-icon">📄</span>
      <div class="dz-label">Arrastra aquí o haz clic para seleccionar</div>
      <div class="dz-sub">Formatos soportados:</div>
      <span class="dz-badge">.txt</span>
      <span class="dz-badge">.docx</span>
      <span class="dz-badge">.html</span>
      <span class="dz-badge">.md</span>
    </div>

    <div id="file-info">
      <span class="fi-icon" id="fi-icon">📄</span>
      <div class="fi-meta">
        <div class="fi-name" id="fi-name">—</div>
        <div class="fi-size" id="fi-size">—</div>
      </div>
      <button class="fi-remove" id="fi-remove" title="Quitar archivo">✕</button>
    </div>

    <div id="preview-area">
      <div class="preview-label">Vista previa del contenido</div>
      <div id="preview-content"></div>
    </div>

    <div id="error-msg" class="alert-error" style="margin-top:1rem">
      <span class="ae-icon">⚠️</span>
      <span id="error-text">Error al procesar el archivo.</span>
    </div>
  </div>

  <!-- OPTIONS CARD -->
  <div class="card">
    <div class="card-title"><span class="dot"></span> Opciones del PDF</div>

    <div class="options-grid">
      <div class="opt-group">
        <label>Tamaño de página</label>
        <div class="select-wrap">
          <select id="opt-size">
            <option value="a4" selected>A4 (210 × 297 mm)</option>
            <option value="letter">Carta (215.9 × 279.4 mm)</option>
            <option value="legal">Legal (215.9 × 355.6 mm)</option>
          </select>
        </div>
      </div>
      <div class="opt-group">
        <label>Orientación</label>
        <div class="select-wrap">
          <select id="opt-orient">
            <option value="portrait" selected>Vertical (Portrait)</option>
            <option value="landscape">Horizontal (Landscape)</option>
          </select>
        </div>
      </div>
      <div class="opt-group">
        <label>Tamaño de fuente</label>
        <div class="select-wrap">
          <select id="opt-font">
            <option value="10">10 pt</option>
            <option value="11" selected>11 pt</option>
            <option value="12">12 pt</option>
            <option value="14">14 pt</option>
          </select>
        </div>
      </div>
      <div class="opt-group">
        <label>Nombre del archivo</label>
        <input type="text" id="opt-name" placeholder="mi-documento" />
      </div>
    </div>

    <div class="toggle-row">
      <label for="tog-nums">Incluir número de páginas</label>
      <label class="toggle">
        <input type="checkbox" id="tog-nums" checked/>
        <span class="toggle-slider"></span>
      </label>
    </div>
    <div class="toggle-row">
      <label for="tog-header">Mostrar nombre de archivo como encabezado</label>
      <label class="toggle">
        <input type="checkbox" id="tog-header"/>
        <span class="toggle-slider"></span>
      </label>
    </div>
  </div>

  <!-- CONVERT CARD -->
  <div class="card">
    <div id="progress-wrap">
      <div class="prog-label">
        <span class="prog-msg" id="prog-msg">Procesando...</span>
        <span id="prog-pct">0%</span>
      </div>
      <div class="prog-bar"><div class="prog-fill" id="prog-fill"></div></div>
    </div>

    <div id="result-area">
      <div class="result-success">
        <span class="result-icon">✅</span>
        <div class="result-info">
          <div class="result-title">¡PDF generado con éxito!</div>
          <div class="result-sub" id="result-sub">Listo para descargar.</div>
        </div>
      </div>
      <a id="download-btn" href="#" download>
        ⬇️ Descargar PDF
      </a>
      <button id="convert-again">↺ Convertir otro archivo</button>
    </div>

    <button id="convert-btn" disabled>
      <span id="btn-text">Selecciona un archivo primero</span>
      <span class="btn-arrow">→</span>
    </button>
  </div>

</main>

<footer>
  Procesamiento 100% local · <strong>DocToPDF</strong> — ningún archivo sale de tu dispositivo
</footer>

<script>
const { jsPDF } = window.jspdf;

let currentFile = null;
let extractedText = '';
let pdfBlob = null;

const dropzone   = document.getElementById('dropzone');
const fileInput  = document.getElementById('file-input');
const fileInfo   = document.getElementById('file-info');
const fiIcon     = document.getElementById('fi-icon');
const fiName     = document.getElementById('fi-name');
const fiSize     = document.getElementById('fi-size');
const fiRemove   = document.getElementById('fi-remove');
const previewArea = document.getElementById('preview-area');
const previewContent = document.getElementById('preview-content');
const errorMsg   = document.getElementById('error-msg');
const errorText  = document.getElementById('error-text');
const convertBtn = document.getElementById('convert-btn');
const btnText    = document.getElementById('btn-text');
const progressWrap = document.getElementById('progress-wrap');
const progMsg    = document.getElementById('prog-msg');
const progPct    = document.getElementById('prog-pct');
const progFill   = document.getElementById('prog-fill');
const resultArea = document.getElementById('result-area');
const downloadBtn = document.getElementById('download-btn');
const resultSub  = document.getElementById('result-sub');
const convertAgain = document.getElementById('convert-again');

const fileIcons = { txt:'📄', docx:'📝', html:'🌐', htm:'🌐', md:'✍️', markdown:'✍️' };

function formatBytes(b) {
  if (b < 1024) return b + ' B';
  if (b < 1048576) return (b/1024).toFixed(1) + ' KB';
  return (b/1048576).toFixed(1) + ' MB';
}

function showError(msg) {
  errorText.textContent = msg;
  errorMsg.style.display = 'flex';
}
function hideError() { errorMsg.style.display = 'none'; }

function setProgress(pct, msg) {
  progFill.style.width = pct + '%';
  progPct.textContent = pct + '%';
  if (msg) progMsg.textContent = msg;
}

async function handleFile(file) {
  hideError();
  previewArea.style.display = 'none';
  extractedText = '';
  pdfBlob = null;

  const ext = file.name.split('.').pop().toLowerCase();
  if (!['txt','docx','html','htm','md','markdown'].includes(ext)) {
    showError('Formato no soportado. Usa: .txt, .docx, .html o .md');
    return;
  }

  currentFile = file;
  fiIcon.textContent = fileIcons[ext] || '📄';
  fiName.textContent = file.name;
  fiSize.textContent = formatBytes(file.size);
  fileInfo.style.display = 'flex';
  dropzone.style.display = 'none';

  // Set default filename
  const nameWithoutExt = file.name.replace(/\.[^/.]+$/, '');
  document.getElementById('opt-name').placeholder = nameWithoutExt;
  if (!document.getElementById('opt-name').value)
    document.getElementById('opt-name').value = nameWithoutExt;

  try {
    if (ext === 'docx') {
      const arrayBuffer = await file.arrayBuffer();
      const result = await mammoth.extractRawText({ arrayBuffer });
      extractedText = result.value;
    } else if (ext === 'html' || ext === 'htm') {
      const text = await file.text();
      const div = document.createElement('div');
      div.innerHTML = text;
      extractedText = div.innerText || div.textContent;
    } else {
      extractedText = await file.text();
    }

    // Show preview
    const preview = extractedText.slice(0, 600);
    previewContent.textContent = preview + (extractedText.length > 600 ? '\n…' : '');
    previewArea.style.display = 'block';

    convertBtn.disabled = false;
    btnText.textContent = 'Convertir a PDF';
  } catch(e) {
    showError('No se pudo leer el archivo: ' + e.message);
    resetUpload();
  }
}

dropzone.addEventListener('dragover', e => { e.preventDefault(); dropzone.classList.add('dragover'); });
dropzone.addEventListener('dragleave', () => dropzone.classList.remove('dragover'));
dropzone.addEventListener('drop', e => {
  e.preventDefault(); dropzone.classList.remove('dragover');
  if (e.dataTransfer.files[0]) handleFile(e.dataTransfer.files[0]);
});
fileInput.addEventListener('change', () => { if (fileInput.files[0]) handleFile(fileInput.files[0]); });

fiRemove.addEventListener('click', resetUpload);

function resetUpload() {
  currentFile = null; extractedText = ''; pdfBlob = null;
  fileInfo.style.display = 'none';
  dropzone.style.display = 'block';
  previewArea.style.display = 'none';
  resultArea.style.display = 'none';
  progressWrap.style.display = 'none';
  convertBtn.style.display = 'flex';
  convertBtn.disabled = true;
  btnText.textContent = 'Selecciona un archivo primero';
  fileInput.value = '';
  hideError();
  document.getElementById('opt-name').value = '';
}

convertAgain.addEventListener('click', resetUpload);

convertBtn.addEventListener('click', async () => {
  if (!extractedText) return;

  convertBtn.style.display = 'none';
  resultArea.style.display = 'none';
  progressWrap.style.display = 'flex';
  setProgress(5, 'Iniciando conversión…');

  await sleep(100);
  setProgress(20, 'Preparando documento…');
  await sleep(150);

  try {
    const size   = document.getElementById('opt-size').value;
    const orient = document.getElementById('opt-orient').value;
    const fontSize = parseInt(document.getElementById('opt-font').value);
    const pageNums = document.getElementById('tog-nums').checked;
    const showHeader = document.getElementById('tog-header').checked;
    let outName = document.getElementById('opt-name').value.trim() || (currentFile.name.replace(/\.[^/.]+$/,''));
    if (!outName.endsWith('.pdf')) outName += '.pdf';

    setProgress(40, 'Generando páginas PDF…');
    await sleep(150);

    const doc = new jsPDF({ orientation: orient, unit: 'mm', format: size });
    const pageW = doc.internal.pageSize.getWidth();
    const pageH = doc.internal.pageSize.getHeight();
    const margin = 18;
    const usableW = pageW - margin * 2;
    const lineH = fontSize * 0.42;

    doc.setFont('helvetica', 'normal');
    doc.setFontSize(fontSize);

    let curY = margin + (showHeader ? 12 : 0);

    if (showHeader) {
      doc.setFontSize(9);
      doc.setTextColor(150, 140, 120);
      doc.text(currentFile.name, margin, margin + 5);
      doc.setLineWidth(0.3);
      doc.setDrawColor(200, 190, 175);
      doc.line(margin, margin + 8, pageW - margin, margin + 8);
      doc.setFontSize(fontSize);
      doc.setTextColor(20, 20, 20);
    }

    const rawLines = extractedText.split('\n');
    const totalLines = rawLines.length;
    let processed = 0;

    for (const rawLine of rawLines) {
      const wrapped = doc.splitTextToSize(rawLine || ' ', usableW);
      for (const wl of wrapped) {
        if (curY + lineH > pageH - margin - (pageNums ? 8 : 0)) {
          doc.addPage();
          curY = margin + (showHeader ? 12 : 0);
          if (showHeader) {
            doc.setFontSize(9);
            doc.setTextColor(150,140,120);
            doc.text(currentFile.name, margin, margin + 5);
            doc.line(margin, margin + 8, pageW - margin, margin + 8);
            doc.setFontSize(fontSize);
            doc.setTextColor(20,20,20);
          }
        }
        doc.text(wl, margin, curY);
        curY += lineH;
      }
      processed++;
    }

    if (pageNums) {
      const total = doc.internal.getNumberOfPages();
      for (let i = 1; i <= total; i++) {
        doc.setPage(i);
        doc.setFontSize(8.5);
        doc.setTextColor(160,150,130);
        doc.text(`Página ${i} de ${total}`, pageW / 2, pageH - 9, { align: 'center' });
      }
    }

    setProgress(80, 'Finalizando PDF…');
    await sleep(200);

    const pdfData = doc.output('datauristring');
    downloadBtn.href = pdfData;
    downloadBtn.download = outName;

    const byteLen = doc.output('arraybuffer').byteLength;
    resultSub.textContent = `${doc.internal.getNumberOfPages()} página(s) · ${formatBytes(byteLen)}`;

    setProgress(100, '¡Conversión completada!');
    await sleep(300);

    progressWrap.style.display = 'none';
    resultArea.style.display = 'grid';
    resultArea.style.gap = '0.8rem';

  } catch(e) {
    progressWrap.style.display = 'none';
    convertBtn.style.display = 'flex';
    showError('Error al generar PDF: ' + e.message);
    convertBtn.disabled = false;
    btnText.textContent = 'Intentar de nuevo';
  }
});

function sleep(ms) { return new Promise(r => setTimeout(r, ms)); }
</script>
</body>
</html>
