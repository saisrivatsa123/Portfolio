---
layout: default
title: Welcome
---

<style>
  /* [ALL YOUR ORIGINAL STYLES + ENHANCED AI PANEL] */
  * { box-sizing: border-box; }
  
  .projects-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 60px 30px;
    text-align: center;
  }
  
  .project-card {
    background: linear-gradient(145deg, #ffffff, #f8f9fa);
    border-radius: 20px;
    padding: 50px 30px;
    margin: 50px 0;
    box-shadow: 0 10px 40px rgba(0,0,0,0.15);
    border: 1px solid rgba(255,255,255,0.3);
    transition: all 0.4s ease;
    max-width: 800px;
    margin-left: auto;
    margin-right: auto;
    display: block;
  }
  
  .project-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 20px 60px rgba(0,0,0,0.25);
    border-color: rgba(0,115,177,0.3);
  }
  
  .project-title {
    font-size: 32px;
    font-weight: bold;
    color: #111121;
    margin-bottom: 20px;
    font-family: 'Arial Black', Gadget, sans-serif;
    line-height: 1.2;
  }
  
  .project-desc {
    font-size: 20px;
    color: #333;
    margin-bottom: 30px;
    font-weight: 500;
    line-height: 1.5;
    padding: 0 20px;
  }
  
  .project-image {
    max-width: 500px;
    max-height: 320px;
    width: 90%;
    height: auto;
    border-radius: 15px;
    margin-top: 25px;
    box-shadow: 0 8px 25px rgba(0,0,0,0.2);
    border: 3px solid #e9ecef;
  }
  
  .github-badge {
    background: linear-gradient(45deg, #24292e, #4078c0);
    color: white !important;
    padding: 12px 24px;
    border-radius: 30px;
    text-decoration: none;
    font-weight: 600;
    font-size: 16px;
    display: inline-block;
    margin: 20px 0;
    transition: all 0.3s ease;
    box-shadow: 0 4px 15px rgba(0,0,0,0.2);
  }
  
  .github-badge:hover {
    background: linear-gradient(45deg, #4078c0, #24292e);
    transform: scale(1.08) translateY(-2px);
    color: white !important;
    box-shadow: 0 8px 25px rgba(0,0,0,0.3);
  }
  
  /* ENHANCED AI PANEL WITH UPLOAD */
  .ai-search-fixed {
    position: fixed;
    bottom: 30px;
    right: 30px;
    width: 400px;
    z-index: 1000;
    background: linear-gradient(145deg, #ffffff, #f8f9fa);
    border-radius: 25px;
    padding: 25px;
    box-shadow: 0 25px 70px rgba(0,0,0,0.3);
    border: 3px solid #0073b1;
    backdrop-filter: blur(15px);
    transition: all 0.3s ease;
  }
  
  .ai-search-fixed:hover {
    box-shadow: 0 30px 80px rgba(0,0,0,0.35);
    border-color: #005a8b;
  }
  
  .ai-upload-btn {
    width: 100%;
    padding: 10px;
    background: linear-gradient(45deg, #28a745, #20c997);
    color: white;
    border: none;
    border-radius: 18px;
    font-size: 13px;
    font-weight: 600;
    cursor: pointer;
    transition: all 0.3s ease;
    margin-bottom: 12px;
  }
  
  .ai-upload-btn:hover {
    background: linear-gradient(45deg, #20c997, #28a745);
    transform: translateY(-2px);
    box-shadow: 0 8px 25px rgba(40,167,69,0.4);
  }
  
  .ai-search-label {
    font-size: 15px;
    color: #333;
    margin-bottom: 12px;
    font-weight: 600;
    display: block;
  }
  
  .ai-search-input {
    width: 100%;
    padding: 14px 18px;
    font-size: 15px;
    border: 2px solid #e0e0e0;
    border-radius: 20px;
    outline: none;
    background: white;
    transition: all 0.3s ease;
    box-sizing: border-box;
  }
  
  .ai-search-input:focus {
    border-color: #0073b1;
    box-shadow: 0 0 20px rgba(0,115,177,0.3);
  }
  
  .ai-search-input::placeholder {
    color: #888;
    font-weight: 400;
  }
  
  .ai-answer {
    margin-top: 12px;
    padding: 15px;
    background: linear-gradient(145deg, #e8f5ff, #f0f8ff);
    border-radius: 18px;
    border-left: 5px solid #0073b1;
    font-size: 14px;
    line-height: 1.6;
    max-height: 140px;
    overflow-y: auto;
    display: none;
    box-shadow: inset 0 2px 10px rgba(0,115,177,0.1);
  }
  
  .ai-loading { color: #0073b1; font-style: italic; }
  .ai-error { color: #dc3545; background: #fff5f5 !important; border-left-color: #dc3545 !important; }
  .ai-success { color: #28a745; }
  
  .upload-status {
    font-size: 12px;
    margin-top: 8px;
    padding: 6px 10px;
    border-radius: 12px;
    text-align: center;
    font-weight: 500;
  }
  
  @media (max-width: 768px) {
    .ai-search-fixed { display: none; }
    .projects-container { padding: 40px 20px; }
    .project-card { padding: 40px 25px; margin: 40px 10px; border-radius: 15px; }
    .project-title { font-size: 26px; }
    .project-desc { font-size: 18px; }
    .project-image { max-width: 400px; max-height: 260px; }
  }
</style>

<!-- FIXED BOTTOM-RIGHT AI PANEL -->
<div class="ai-search-fixed">
  <!-- RESUME UPLOAD -->
  <input type="file" id="resume-upload" accept=".pdf,.docx,.txt" style="display: none;">
  <button class="ai-upload-btn" onclick="document.getElementById('resume-upload').click()">
    📄 Upload Resume First
  </button>
  <div id="auto-load-status" class="upload-status" style="display: none;"></div>
  <div id="upload-status" class="upload-status" style="display: none;"></div>
  
  <!-- Q&A -->
  <div class="ai-search-label">🤖 Ask about my profile:</div>
  <input type="text" class="ai-search-input" id="profile-search" 
         placeholder="Skills? Fabric experience? Certifications?" />
  <div id="ai-answer" class="ai-answer"></div>
</div>

<!-- YOUR PROJECTS [UNCHANGED] -->
<div class="projects-container">
  <div class="project-card">
    <div class="project-title">Fine-tuned Sentiment Analysis using Distilled BERT</div>
    <div class="project-desc">Advanced NLP model fine-tuning with Distilled BERT for sentiment classification tasks</div>
    <a href="https://github.com/saisrivatsa123/BERT" class="github-badge">📂 View on GitHub</a>
    <img src="assets/img/BERT.png" alt="BERT Sentiment Analysis" class="project-image">
  </div>

  <div class="project-card">
    <div class="project-title">Denoising Autoencoders</div>
    <div class="project-desc">Deep learning model for image denoising and reconstruction using autoencoder architecture</div>
    <a href="https://github.com/saisrivatsa123/Denoising-Auto_encoders" class="github-badge">📂 View on GitHub</a>
    <img src="assets/img/denoise.png" alt="Denoising Autoencoder" class="project-image">
  </div>

  <div class="project-card">
    <div class="project-title">LendingClub Case Study</div>
    <div class="project-desc">Financial risk analysis and loan default prediction using machine learning techniques</div>
    <a href="https://github.com/saisrivatsa123/LendingClubCaseStudy" class="github-badge">📂 View on GitHub</a>
    <img src="assets/img/Loan_image.png" alt="LendingClub Analysis" class="project-image">
  </div>

  <div class="project-card">
    <div class="project-title">Long Short-Term Memory (LSTM)</div>
    <div class="project-desc">Recurrent neural network implementation for time series forecasting and sequence modeling</div>
    <a href="https://github.com/saisrivatsa123/LSTM" class="github-badge">📂 View on GitHub</a>
    <img src="assets/img/LSTM.png" alt="LSTM Model" class="project-image">
  </div>
</div>

<script>
const API_BASE = "/";
const searchInput = document.getElementById('profile-search');
const answerDiv = document.getElementById('ai-answer');
const uploadStatus = document.getElementById('upload-status');
const autoLoadStatus = document.getElementById('auto-load-status');
const resumeUpload = document.getElementById('resume-upload');

// 🎯 AUTO-LOAD YOUR RESUME FROM DIRECTORY
const RESUME_PATH = "blob/My_resume.pdf";  // ← CHANGE THIS TO YOUR EXACT PATH!

async function autoLoadResume() {
    try {
        // Fetch your resume file
        const response = await fetch(RESUME_PATH);
        if (!response.ok) {
            console.log('Resume file not found, manual upload available');
            return;
        }
        
        const blob = await response.blob();
        const formData = new FormData();
        formData.append('file', blob, 'resume.pdf');
        
        // Show loading
        autoLoadStatus.style.display = 'block';
        autoLoadStatus.textContent = '🔄 Auto-loading resume...';
        
        // Upload to API
        const apiResponse = await fetch(`${API_BASE}upload-resume`, {
            method: 'POST',
            body: formData
        });
        
        const data = await apiResponse.json();
        
        if (data.status === 'success') {
            autoLoadStatus.innerHTML = `✅ <strong>${data.filename}</strong> auto-loaded!`;
            autoLoadStatus.style.color = '#28a745';
            uploadStatus.style.display = 'none';  // Hide manual status
        } else {
            autoLoadStatus.textContent = '❌ Auto-load failed';
            autoLoadStatus.style.color = '#dc3545';
        }
    } catch (error) {
        console.log('Auto-load error:', error);
        autoLoadStatus.style.display = 'none';
    }
}

// 🚀 AUTO-LOAD ON PAGE START
window.addEventListener('load', autoLoadResume);

// 📤 MANUAL UPLOAD
resumeUpload.addEventListener('change', async function(e) {
    const file = e.target.files[0];
    if (!file) return;
    
    uploadStatus.style.display = 'block';
    uploadStatus.textContent = '📤 Uploading...';
    uploadStatus.className = 'upload-status';
    
    const formData = new FormData();
    formData.append('file', file);
    
    try {
        const response = await fetch(`${API_BASE}/upload-resume`, {
            method: 'POST',
            body: formData
        });
        const data = await response.json();
        
        if (data.error) {
            uploadStatus.textContent = `❌ ${data.error}`;
            uploadStatus.style.color = '#dc3545';
        } else {
            uploadStatus.innerHTML = `✅ <strong>${data.filename}</strong> loaded!`;
            uploadStatus.style.color = '#28a745';
            uploadStatus.classList.add('ai-success');
            answerDiv.style.display = 'none';
            autoLoadStatus.style.display = 'none';  // Hide auto-load
        }
    } catch (error) {
        uploadStatus.textContent = '❌ Upload failed - check API';
        uploadStatus.style.color = '#dc3545';
    }
});

// 🤖 Q&A FUNCTIONALITY
let timeout;
searchInput.addEventListener('input', function() {
    clearTimeout(timeout);
    timeout = setTimeout(() => {
        if (this.value.trim().length > 2) {
            askProfile(this.value);
        } else {
            answerDiv.style.display = 'none';
        }
    }, 800);
});

searchInput.addEventListener('keypress', function(e) {
    if (e.key === 'Enter') {
        askProfile(this.value);
    }
});

async function askProfile(question) {
    if (!question || question.trim().length < 3) return;
    
    answerDiv.innerHTML = '<div class="ai-loading">🔍 Searching resume...</div>';
    answerDiv.style.display = 'block';
    answerDiv.className = 'ai-answer';
    
    try {
        const response = await fetch(`${API_BASE}ask`, {
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({ question: question.trim() })
        });
        
        const data = await response.json();
        
        if (data.error) {
            answerDiv.innerHTML = `<div class="ai-error">❌ ${data.error}</div>`;
        } else {
            answerDiv.innerHTML = `<div><strong>💡</strong> ${data.answer}</div>`;
        }
    } catch (error) {
        answerDiv.innerHTML = `
            <div class="ai-error">
                ❌ API not connected<br>
                <small>1. Deploy backend first<br>2. Check console (F12)</small>
            </div>
        `;
    }
}

// 🎯 Auto-suggest on focus
searchInput.addEventListener('focus', function() {
    if (!this.value) {
        this.placeholder = "Try: 'Fabric experience', 'Databricks cert', 'skills list'...";
    }
});
</script>