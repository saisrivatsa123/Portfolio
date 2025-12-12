<script>
const searchInput = document.getElementById('profile-search');
const answerDiv = document.getElementById('ai-answer');
const uploadStatus = document.getElementById('upload-status');
const autoLoadStatus = document.getElementById('auto-load-status');
const resumeUpload = document.getElementById('resume-upload');

// TEST BACKEND FIRST - Skip auto-load for now
async function testBackend() {
    try {
        const response = await fetch('/health');
        const data = await response.json();
        console.log('Backend:', data);
        if (data.status === 'healthy') {
            answerDiv.innerHTML = '<div style="color: green;">✅ Backend connected!</div>';
            answerDiv.style.display = 'block';
        }
    } catch (e) {
        answerDiv.innerHTML = '<div style="color: red;">❌ Backend not responding</div>';
        answerDiv.style.display = 'block';
    }
}

// MANUAL UPLOAD (WORKS WITH YOUR BACKEND)
resumeUpload.addEventListener('change', async function(e) {
    const file = e.target.files[0];
    if (!file) return;
    
    uploadStatus.style.display = 'block';
    uploadStatus.textContent = '📤 Uploading...';
    
    const formData = new FormData();
    formData.append('file', file);
    
    try {
        const response = await fetch('/upload-resume', {  // Backend endpoint
            method: 'POST',
            body: formData
        });
        const data = await response.json();
        
        if (data.status === 'success' || !data.error) {
            uploadStatus.innerHTML = `✅ <strong>${data.filename || 'Resume'}</strong> loaded!`;
            uploadStatus.style.color = '#28a745';
            answerDiv.style.display = 'none';
        } else {
            uploadStatus.innerHTML = `❌ ${data.error}`;
            uploadStatus.style.color = '#dc3545';
        }
    } catch (error) {
        uploadStatus.innerHTML = '❌ Upload failed';
        uploadStatus.style.color = '#dc3545';
        console.error('Upload error:', error);
    }
});

// Q&A (WORKS WITH YOUR LangChain BACKEND)
let timeout;
searchInput.addEventListener('input', function() {
    clearTimeout(timeout);
    timeout = setTimeout(() => {
        if (this.value.trim().length > 2) askProfile(this.value);
        else answerDiv.style.display = 'none';
    }, 800);
});

searchInput.addEventListener('keypress', function(e) {
    if (e.key === 'Enter') askProfile(this.value);
});

async function askProfile(question) {
    if (!question || question.trim().length < 3) return;
    
    answerDiv.innerHTML = '<div class="ai-loading">🔍 Searching resume...</div>';
    answerDiv.style.display = 'block';
    
    try {
        const response = await fetch('/ask', {  // Backend endpoint
            method: 'POST',
            headers: { 'Content-Type': 'application/json' },
            body: JSON.stringify({ question: question.trim() })
        });
        
        const data = await response.json();
        console.log('Q&A Response:', data);  // DEBUG
        
        if (data.error) {
            answerDiv.innerHTML = `<div class="ai-error">❌ ${data.error}</div>`;
        } else if (data.answer) {
            answerDiv.innerHTML = `<div><strong>💡</strong> ${data.answer}</div>`;
        } else {
            answerDiv.innerHTML = `<div class="ai-error">❌ Unexpected response format</div>`;
        }
    } catch (error) {
        answerDiv.innerHTML = `<div class="ai-error">❌ Network error: ${error.message}</div>`;
        console.error('Q&A error:', error);
    }
}

// TEST ON LOAD
window.addEventListener('load', testBackend);

searchInput.addEventListener('focus', function() {
    if (!this.value) this.placeholder = "Try: 'Fabric experience', 'skills', 'certification'";
});
</script>
