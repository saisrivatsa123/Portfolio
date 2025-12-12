---
layout: default
title: Welcome
---

<style>
  /* CENTER ALL PROJECTS AND CONTENT */
  * { box-sizing: border-box; }
  
  .projects-container {
    max-width: 1000px; /* Reasonable max width */
    margin: 0 auto; /* Perfect center */
    padding: 40px 20px;
    text-align: center;
  }
  
  .project-card {
    background: #f8f9fa;
    border-radius: 12px;
    padding: 30px 20px;
    margin: 30px 0;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  
  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 25px rgba(0,0,0,0.15);
  }
  
  .project-title {
    font-size: 24px;
    font-weight: bold;
    color: #1a1a1a;
    margin-bottom: 15px;
    font-family: 'Arial Black', sans-serif;
  }
  
  .project-desc {
    font-size: 16px;
    color: #333;
    margin-bottom: 20px;
    font-weight: 500;
  }
  
  .project-image {
    max-width: 400px;
    max-height: 250px;
    width: 100%;
    height: auto;
    border-radius: 8px;
    margin-top: 20px;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
  }
  
  .github-badge {
    background: linear-gradient(45deg, #24292e, #4078c0);
    color: white !important;
    padding: 8px 16px;
    border-radius: 25px;
    text-decoration: none;
    font-weight: 600;
    font-size: 14px;
    display: inline-block;
    margin: 10px 0;
    transition: all 0.3s ease;
  }
  
  .github-badge:hover {
    background: linear-gradient(45deg, #4078c0, #24292e);
    transform: scale(1.05);
    color: white !important;
  }
  
  @media (max-width: 768px) {
    .projects-container { padding: 20px 15px; }
    .project-card { padding: 20px 15px; margin: 20px 0; }
    .project-title { font-size: 20px; }
  }
</style>

<div class="projects-container">
  
  <!-- Project 1 -->
  <div class="project-card">
    <div class="project-title">Fine-tuned Sentiment Analysis using Distilled BERT</div>
    <div class="project-desc">**Advanced NLP model fine-tuning with Distilled BERT for sentiment classification**</div>
    <a href="https://github.com/saisrivatsa123/BERT" class="github-badge">
      📂 View on GitHub
    </a>
    <img src="assets/img/BERT.png" alt="BERT Sentiment Analysis" class="project-image">
  </div>

  <!-- Project 2 -->
  <div class="project-card">
    <div class="project-title">Denoising Autoencoders</div>
    <div class="project-desc">**Deep learning model for image denoising and reconstruction**</div>
    <a href="https://github.com/saisrivatsa123/Denoising-Auto_encoders" class="github-badge">
      📂 View on GitHub
    </a>
    <img src="assets/img/denoise.png" alt="Denoising Autoencoder" class="project-image">
  </div>

  <!-- Project 3 -->
  <div class="project-card">
    <div class="project-title">LendingClub Case Study</div>
    <div class="project-desc">**Financial risk analysis and loan default prediction**</div>
    <a href="https://github.com/saisrivatsa123/LendingClubCaseStudy" class="github-badge">
      📂 View on GitHub
    </a>
    <img src="assets/img/Loan_image.png" alt="LendingClub Analysis" class="project-image">
  </div>

  <!-- Project 4 -->
  <div class="project-card">
    <div class="project-title">Long Short-Term Memory (LSTM)</div>
    <div class="project-desc">**Recurrent neural network for time series forecasting**</div>
    <a href="https://github.com/saisrivatsa123/LSTM" class="github-badge">
      📂 View on GitHub
    </a>
    <img src="assets/img/LSTM.png" alt="LSTM Model" class="project-image">
  </div>

</div>
