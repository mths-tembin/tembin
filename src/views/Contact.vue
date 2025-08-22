<template>
  <div class="contact-page">
    <div class="container">
      <div class="contact-header">
        <h1>お問い合わせ</h1>
        <p>プロジェクトについてご相談ください</p>
      </div>
      
      <div class="contact-content">
        <div class="contact-info">
          <h2>Contact Information</h2>
          <div class="contact-details">
            <div class="contact-item">
              <span class="contact-label">Email:</span>
              <a href="mailto:matsuhashi@tembin.jp">matsuhashi@tembin.jp</a>
            </div>
            <div class="contact-item">
              <span class="contact-label">Website:</span>
              <a href="https://tembin.jp" target="_blank">tembin.jp</a>
            </div>
          </div>
          
          <div class="contact-description">
            <h3>サービス内容</h3>
            <ul>
              <li>ロゴデザイン</li>
              <li>グラフィックデザイン</li>
              <li>WEBデザイン</li>
              <li>ブランディング</li>
            </ul>
          </div>
        </div>
        
        <div class="contact-form-container">
          <h2>お問い合わせフォーム</h2>
          <p>以下のフォームからお気軽にお問い合わせください。</p>
          
          <div class="form-actions">
            <a href="/contact/branding-contact.html" class="btn btn-primary btn-large">
              お問い合わせフォームを開く
            </a>
            <p class="form-note">
              または直接メール: <a href="mailto:matsuhashi@tembin.jp">matsuhashi@tembin.jp</a>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Contact'
}
</script>

<style scoped>
.contact-page {
  padding-top: 100px;
  min-height: 100vh;
  background-color: var(--bg-main);
}

.contact-header {
  text-align: center;
  margin-bottom: 4rem;
}

.contact-header h1 {
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 1rem;
  color: var(--text-light);
}

.contact-header p {
  font-size: 1.2rem;
  color: var(--text-muted);
}

.contact-content {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 4rem;
  align-items: start;
}

.contact-info {
  background: var(--bg-panel);
  padding: 2rem;
  border-radius: 8px;
}

.contact-info h2 {
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
  color: var(--text-light);
}

.contact-details {
  margin-bottom: 2rem;
}

.contact-item {
  display: flex;
  align-items: center;
  margin-bottom: 1rem;
}

.contact-label {
  font-weight: 600;
  margin-right: 1rem;
  min-width: 80px;
  color: var(--text-light);
}

.contact-item a {
  color: var(--highlight);
  text-decoration: none;
  transition: var(--transition);
}

.contact-item a:hover {
  color: var(--text-light);
}

.contact-description h3 {
  font-size: 1.2rem;
  margin-bottom: 1rem;
  color: var(--text-light);
}

.contact-description ul {
  list-style: none;
  padding: 0;
}

.contact-description li {
  padding: 0.5rem 0;
  color: var(--text-muted);
  position: relative;
  padding-left: 1.5rem;
}

.contact-description li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: var(--highlight);
  font-weight: bold;
}

.contact-form-container {
  background: var(--bg-panel);
  padding: 2rem;
  border-radius: 8px;
  text-align: center;
}

.contact-form-container h2 {
  font-size: 1.5rem;
  margin-bottom: 1rem;
  color: var(--text-light);
}

.contact-form-container p {
  color: var(--text-muted);
  margin-bottom: 2rem;
}

.form-actions {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 1rem;
}

.form-note {
  font-size: 0.9rem;
  color: var(--text-muted);
}

.form-note a {
  color: var(--highlight);
  text-decoration: none;
}

.form-note a:hover {
  color: var(--text-light);
}

@media (max-width: 768px) {
  .contact-content {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .contact-header h1 {
    font-size: 2.5rem;
  }
  
  .contact-page {
    padding-top: 80px;
  }
}
</style>
