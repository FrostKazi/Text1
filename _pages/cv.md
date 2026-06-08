---
layout: page
title: CV
permalink: /cv/
nav: true
nav_order: 3
---

<style>
  #pdf-container { width:100%; max-width:900px; margin:0 auto; }
  #pdf-canvas { width:100%; height:auto; display:block; box-shadow:0 4px 24px rgba(0,0,0,0.18); border-radius:4px; }
  .pdf-controls { display:flex; align-items:center; justify-content:center; gap:1rem; margin:1rem 0; font-size:0.88rem; flex-wrap:wrap; }
  .pdf-controls button { padding:5px 16px; border:1px solid currentColor; border-radius:4px; background:transparent; cursor:pointer; opacity:0.7; }
  .pdf-controls button:hover { opacity:1; }
  .pdf-download-btn { display:inline-flex; align-items:center; gap:0.4rem; margin-bottom:1rem; padding:7px 18px; background:#24292e; color:#fff !important; border-radius:5px; text-decoration:none !important; font-size:0.85rem; }
  .pdf-download-btn:hover { background:#444; }
  #pdf-error { color:#c0392b; padding:1rem; border:1px solid #c0392b; border-radius:4px; display:none; margin-top:1rem; }
</style>

<div id="pdf-container">
  <a class="pdf-download-btn" href="{{ '/assets/pdf/resume.pdf' | relative_url }}" download>
    <i class="fas fa-download"></i> Download PDF
  </a>

  <div class="pdf-controls">
    <button id="pdf-prev">&#8592; Prev</button>
    <span>Page <span id="pdf-page-num">1</span> of <span id="pdf-page-count">&mdash;</span></span>
    <button id="pdf-next">Next &#8594;</button>
  </div>

  <canvas id="pdf-canvas"></canvas>

  <div id="pdf-error">
    PDF not found. Upload your resume to <code>assets/pdf/resume.pdf</code> and commit.
  </div>
</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.min.js"
  integrity="sha512-q+4lAudCFBdaLcVHkMkVhBQBXJuVnMH0JnPWxjHCJQwWIrLn0A8T5S3cbBMm9EhEPmMHPtUIjwRFVOYwq5NQ=="
  crossorigin="anonymous" referrerpolicy="no-referrer"></script>

<script>
(function(){
  pdfjsLib.GlobalWorkerOptions.workerSrc =
    'https://cdnjs.cloudflare.com/ajax/libs/pdf.js/3.11.174/pdf.worker.min.js';

  const pdfUrl      = '{{ "/assets/pdf/resume.pdf" | relative_url }}';
  const canvas      = document.getElementById('pdf-canvas');
  const ctx         = canvas.getContext('2d');
  const pageNumEl   = document.getElementById('pdf-page-num');
  const pageCountEl = document.getElementById('pdf-page-count');
  const errEl       = document.getElementById('pdf-error');

  let pdfDoc = null, currentPage = 1;

  function renderPage(num) {
    pdfDoc.getPage(num).then(function(page){
      var containerW = canvas.parentElement.clientWidth || 800;
      var vp0 = page.getViewport({ scale: 1 });
      var scale = containerW / vp0.width;
      var vp = page.getViewport({ scale: scale });
      canvas.height = vp.height;
      canvas.width  = vp.width;
      page.render({ canvasContext: ctx, viewport: vp });
      pageNumEl.textContent = num;
    });
  }

  pdfjsLib.getDocument(pdfUrl).promise.then(function(pdf){
    pdfDoc = pdf;
    pageCountEl.textContent = pdf.numPages;
    renderPage(1);
  }).catch(function(){
    errEl.style.display = 'block';
    canvas.style.display = 'none';
  });

  document.getElementById('pdf-prev').addEventListener('click', function(){
    if(currentPage > 1){ currentPage--; renderPage(currentPage); }
  });
  document.getElementById('pdf-next').addEventListener('click', function(){
    if(pdfDoc && currentPage < pdfDoc.numPages){ currentPage++; renderPage(currentPage); }
  });

  var resizeT;
  window.addEventListener('resize', function(){
    clearTimeout(resizeT);
    resizeT = setTimeout(function(){ if(pdfDoc) renderPage(currentPage); }, 200);
  });
}());
</script>
