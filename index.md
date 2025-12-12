---
layout: default
title: Welcome
---

<style>
  /* CENTER ALL PROJECTS + FIXED SEARCH BAR */
  * { box-sizing: border-box; }
  
  .projects-container {
    max-width: 1200px; /* WIDER container */
    margin: 0 auto; /* Perfect center */
    padding: 60px 30px; /* MORE padding */
    text-align: center;
  }
  
  .project-card {
    background: linear-gradient(145deg, #ffffff, #f8f9fa);
    border-radius: 20px; /* BIGGER radius */
    padding: 50px 30px; /* BIGGER padding */
    margin: 50px 0; /* BIGGER spacing */
    box-shadow: 0 10px 40px rgba(0,0,0,0.15); /* DEEPER shadow */
    border: 1px solid rgba(255,255,255,0.3);
    transition: all 0.4s ease;
    max-width: 800px; /* BIGGER card width */
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
    font-size: 32px; /* BIGGER title */
    font-weight: bold;
    color: #111121;
    margin-bottom: 20px;
    font-family: 'Arial Black', Gadget, sans-serif;
    line-height: 1.2;
  }
  
  .project-desc {
    font-size: 20px; /* BIGGER desc */
    color: #333;
    margin-bottom: 30px;
    font-weight: 500;
    line-height: 1.5;
    padding: 0 20px;
  }
  
  .project-image {
    max-width: 500px; /* BIGGER images */
    max-height: 320px;
    width: 90%; /* Responsive */
    height: auto;
    border-radius: 15px;
    margin-top: 25px;
    box-shadow: 0 8px 25px rgba(0,0,0,0.2);
    border: 3px solid #e9ecef;
  }
  
  .github-badge {
    background: linear-gradient(45deg, #24292e, #4078c0);
    color: white !important;
    padding: 12px 24px; /* BIGGER badge */
    border-radius: 30px;
    text-decoration: none;
    font-weight: 600;
    font-size: 16px; /* BIGGER text */
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
  
  /* FIXED SEARCH BAR - BOTTOM RIGHT */
  .ai-search-fixed {
    position: fixed;
    bottom: 30px;
    right: 30px;
    width: 350px;
    z-index: 1000;
    background: linear-gradient(145deg, #ffffff, #f8f9fa);
    border-radius: 25px;
    padding: 20px;
    box-shadow: 0 20px 60px rgba(0,0,0,0.25);
    border: 2px solid #0073b1;
    backdrop-filter: blur(10px);
  }
  
  .ai-search-label {
    font-size: 14px;
    color: #333;
    margin-bottom: 10px;
    font-weight: 600;
    display: block;
  }
  
  .ai-search-input {
    width: 100%;
    padding: 12px 16px;
    font-size: 14px;
    border: 2px solid #e0e0e0;
    border-radius: 20px;
    outline: none;
    background: white;
    transition: all 0.3s ease;
  }
  
  .ai-search-input:focus {
    border-color: #0073b1;
    box-shadow: 0 0 20px rgba(0,115,177,0.3);
  }
  
  .ai-search-input::placeholder {
    color: #888;
    font-weight: 400;
  }
  
  /* Hide search on mobile - too cramped */
  @media (max-width: 768px) {
    .ai-search-fixed {
      display: none;
    }
    .projects-container { padding: 40px 20px; }
    .project-card { 
      padding: 40px 25px; 
      margin: 40px 10px; 
      border-radius: 15px;
    }
    .project-title { font-size: 26px; }
    .project-desc { font-size: 18px; }
    .project-image { max-width: 400px; max-height: 260px; }
  }
</style>

<!-- FIXED BOTTOM-RIGHT AI SEARCH BAR -->
<div class="ai-search-fixed">
  <div class="ai-search-label">🤖 Ask about my profile:</div>
  <input type="text" class="ai-search-input" id="profile-search" 
         placeholder="Skills? Projects? Experience?" />
</div>

<!-- YOUR PROJECTS -->
<div class="projects-container">
  
  <!-- Project 1 -->
  <div class="project-card">
    <div class="project-title">Fine-tuned Sentiment Analysis using Distilled BERT</div>
    <div class="project-desc">Advanced NLP model fine-tuning with Distilled BERT for sentiment classification tasks</div>
    <a href="https://github.com/saisrivatsa123/BERT" class="github-badge">
      📂 View on GitHub
    </a>
    <img src="assets/img/BERT.png" alt="BERT Sentiment Analysis" class="project-image">
  </div>

  <!-- Project 2 -->
  <div class="project-card">
    <div class="project-title">Denoising Autoencoders</div>
    <div class="project-desc">Deep learning model for image denoising and reconstruction using autoencoder architecture</div>
    <a href="https://github.com/saisrivatsa123/Denoising-Auto_encoders" class="github-badge">
      📂 View on GitHub
    </a>
    <img src="assets/img/denoise.png" alt="Denoising Autoencoder" class="project-image">
  </div>

  <!-- Project 3 -->
  <div class="project-card">
    <div class="project-title">LendingClub Case Study</div>
    <div class="project-desc">Financial risk analysis and loan default prediction using machine learning techniques</div>
    <a href="https://github.com/saisrivatsa123/LendingClubCaseStudy" class="github-badge">
      📂 View on GitHub
    </a>
    <img src="assets/img/Loan_image.png" alt="LendingClub Analysis" class="project-image">
  </div>

  <!-- Project 4 -->
  <div class="project-card">
    <div class="project-title">Long Short-Term Memory (LSTM)</div>
    <div class="project-desc">Recurrent neural network implementation for time series forecasting and sequence modeling</div>
    <a href="https://github.com/saisrivatsa123/LSTM" class="github-badge">
      📂 View on GitHub
    </a>
    <img src="assets/img/LSTM.png" alt="LSTM Model" class="project-image">
  </div>

</div>
