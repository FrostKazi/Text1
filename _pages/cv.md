---
layout: page
title: CV
permalink: /cv/
nav: true
nav_order: 3
---

<style>
  .cv-wrap { max-width: 860px; margin: 0 auto; }
  .cv-actions { display:flex; align-items:center; gap:1rem; margin-bottom:1.25rem; flex-wrap:wrap; }
  .cv-btn {
    display:inline-flex; align-items:center; gap:0.4rem;
    padding:8px 20px; border-radius:6px; font-size:0.85rem;
    text-decoration:none; font-weight:500; transition:opacity 0.15s;
  }
  .cv-btn:hover { opacity:0.85; }
  .cv-btn-primary { background:#1e3a5f; color:#fff !important; }
  .cv-btn-secondary {
    background:transparent; color:inherit;
    border:1px solid currentColor; opacity:0.65;
  }
  .cv-btn-secondary:hover { opacity:1; }
  #cv-frame {
    width:100%; height:82vh; min-height:600px;
    border:none; border-radius:6px;
    box-shadow:0 4px 24px rgba(0,0,0,0.12);
    display:block;
  }
  .cv-fallback {
    padding:2.5rem; text-align:center;
    border:1px solid rgba(128,128,128,0.2); border-radius:6px;
    display:none;
  }
</style>

<div class="cv-wrap">
  <div class="cv-actions">
    <a class="cv-btn cv-btn-primary"
       href="{{ '/assets/pdf/resume.pdf' | relative_url }}" download>
      <i class="fas fa-download"></i> Download PDF
    </a>
    <a class="cv-btn cv-btn-secondary"
       href="{{ '/assets/pdf/resume.pdf' | relative_url }}" target="_blank">
      <i class="fas fa-external-link-alt"></i> Open in new tab
    </a>
  </div>

  <iframe id="cv-frame"
    src="{{ '/assets/pdf/resume.pdf' | relative_url }}"
    title="Kazi Abdul Baset CV">
  </iframe>

  <div class="cv-fallback" id="cv-fallback">
    <p style="font-size:0.9rem; opacity:0.7; margin-bottom:1rem;">
      Your browser doesn't support inline PDF preview.
    </p>
    <a class="cv-btn cv-btn-primary"
       href="{{ '/assets/pdf/resume.pdf' | relative_url }}" download>
      <i class="fas fa-download"></i> Download CV
    </a>
  </div>
</div>

<script>
  (function(){
    var frame = document.getElementById('cv-frame');
    var fallback = document.getElementById('cv-fallback');
    // Show fallback if iframe fails (mobile Safari etc)
    frame.onerror = function(){
      frame.style.display = 'none';
      fallback.style.display = 'block';
    };
    // Extra check: if frame is very short after load, assume it failed
    frame.onload = function(){
      if(frame.contentDocument && frame.contentDocument.body &&
         frame.contentDocument.body.innerHTML.indexOf('404') !== -1){
        frame.style.display = 'none';
        fallback.style.display = 'block';
      }
    };
  })();
</script>
