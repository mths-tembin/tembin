<template>
  <div class="home">
    <!-- Hero Section -->
    <section id="home" class="hero">
      <div class="hero-background">
        <div class="parallax-bg" ref="parallaxBg"></div>
      </div>
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-title">
            <span class="title-line">Creative</span>
            <span class="title-line">Design</span>
            <span class="title-line">Portfolio</span>
          </h1>
          <p class="hero-subtitle">ロゴデザイン・グラフィックデザイン・WEBデザイン</p>
          <div class="hero-buttons">
            <a href="#works" class="btn btn-primary">作品を見る</a>
            <router-link to="/contact" class="btn btn-secondary">お問い合わせ</router-link>
          </div>
        </div>
      </div>
      <div class="scroll-indicator">
        <div class="scroll-arrow"></div>
      </div>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">About</h2>
          <p class="section-subtitle">デザインで価値を創造する</p>
        </div>
        <div class="about-content">
          <div class="about-text">
            <p>クリエイティブな視点で、ブランドの本質を表現するデザインを制作しています。</p>
            <p>ロゴデザインからWEBデザインまで、一貫したブランディングでお客様のビジネスをサポートします。</p>
          </div>
          <div class="about-stats">
            <div class="stat-item">
              <div class="stat-number" ref="stat1" data-target="50">0</div>
              <div class="stat-label">制作実績</div>
            </div>
            <div class="stat-item">
              <div class="stat-number" ref="stat2" data-target="30">0</div>
              <div class="stat-label">満足度</div>
            </div>
            <div class="stat-item">
              <div class="stat-number" ref="stat3" data-target="5">0</div>
              <div class="stat-label">経験年数</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Works Section -->
    <section id="works" class="works">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Works</h2>
          <p class="section-subtitle">制作実績</p>
        </div>
        <div class="works-grid">
          <div 
            v-for="work in filteredWorks" 
            :key="work.id" 
            class="work-item" 
            :data-category="work.category"
          >
            <div class="work-image">
              <div style="display: flex; align-items: center; justify-content: center; height: 100%; color: var(--text-muted); font-size: 1.2rem;">
                <div style="text-align: center;">
                  <div style="font-size: 3rem; margin-bottom: 1rem;">{{ work.emoji }}</div>
                  <div>{{ work.title }}</div>
                  <div style="font-size: 0.8rem; margin-top: 0.5rem;">画像を追加してください</div>
                </div>
              </div>
            </div>
            <div class="work-overlay">
              <h3>{{ work.name }}</h3>
              <p>{{ work.description }}</p>
              <span class="work-category">{{ work.categoryLabel }}</span>
            </div>
          </div>
        </div>
        <div class="works-filter">
          <button 
            v-for="filter in filters" 
            :key="filter.value"
            class="filter-btn" 
            :class="{ active: activeFilter === filter.value }"
            @click="setFilter(filter.value)"
          >
            {{ filter.label }}
          </button>
        </div>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="services">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Services</h2>
          <p class="section-subtitle">提供サービス</p>
        </div>
        <div class="services-grid">
          <div v-for="service in services" :key="service.id" class="service-item">
            <div class="service-icon">
              <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
                <path v-if="service.id === 1" d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/>
                <rect v-if="service.id === 2" x="3" y="3" width="18" height="18" rx="2" ry="2"/>
                <circle v-if="service.id === 2" cx="8.5" cy="8.5" r="1.5"/>
                <polyline v-if="service.id === 2" points="21,15 16,10 5,21"/>
                <rect v-if="service.id === 3" x="2" y="3" width="20" height="14" rx="2" ry="2"/>
                <line v-if="service.id === 3" x1="8" y1="21" x2="16" y2="21"/>
                <line v-if="service.id === 3" x1="12" y1="17" x2="12" y2="21"/>
              </svg>
            </div>
            <h3>{{ service.title }}</h3>
            <p>{{ service.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
      <div class="container">
        <div class="section-header">
          <h2 class="section-title">Contact</h2>
          <p class="section-subtitle">お問い合わせ</p>
        </div>
        <div class="contact-content">
          <div class="contact-info">
            <h3>プロジェクトについて相談したい</h3>
            <p>ロゴデザイン、グラフィックデザイン、WEBデザインについて、お気軽にお問い合わせください。</p>
            <div class="contact-details">
              <div class="contact-item">
                <span class="contact-label">Email:</span>
                <a href="mailto:matsuhashi@tembin.jp">matsuhashi@tembin.jp</a>
              </div>
            </div>
          </div>
          <div class="contact-form">
            <router-link to="/contact" class="btn btn-primary btn-large">お問い合わせフォーム</router-link>
            <p style="margin-top: 1rem; color: var(--text-muted); font-size: 0.9rem;">
              または直接メール: <a href="mailto:matsuhashi@tembin.jp" style="color: var(--highlight);">matsuhashi@tembin.jp</a>
            </p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      activeFilter: 'all',
      works: [
        {
          id: 1,
          title: 'ロゴデザイン作品',
          name: 'ブランドロゴデザイン',
          description: '企業のブランドアイデンティティを表現したロゴデザイン',
          category: 'logo',
          categoryLabel: 'Logo Design',
          emoji: '🎨'
        },
        {
          id: 2,
          title: 'WEBデザイン作品',
          name: 'コーポレートサイト',
          description: 'モダンで使いやすい企業サイトのデザイン',
          category: 'web',
          categoryLabel: 'Web Design',
          emoji: '💻'
        },
        {
          id: 3,
          title: 'グラフィックデザイン作品',
          name: 'パッケージデザイン',
          description: '商品の魅力を引き出すパッケージデザイン',
          category: 'graphic',
          categoryLabel: 'Graphic Design',
          emoji: '📦'
        },
        {
          id: 4,
          title: 'スタートアップロゴ',
          name: 'スタートアップロゴ',
          description: '新しいビジネスの可能性を表現したロゴ',
          category: 'logo',
          categoryLabel: 'Logo Design',
          emoji: '🚀'
        },
        {
          id: 5,
          title: 'ECサイトデザイン',
          name: 'ECサイトデザイン',
          description: '売上向上を目指したECサイトのデザイン',
          category: 'web',
          categoryLabel: 'Web Design',
          emoji: '🛒'
        },
        {
          id: 6,
          title: 'ブランディング素材',
          name: 'ブランディング素材',
          description: '統一感のあるブランディング素材の制作',
          category: 'graphic',
          categoryLabel: 'Graphic Design',
          emoji: '🎯'
        }
      ],
      filters: [
        { value: 'all', label: 'All' },
        { value: 'logo', label: 'Logo' },
        { value: 'web', label: 'Web' },
        { value: 'graphic', label: 'Graphic' }
      ],
      services: [
        {
          id: 1,
          title: 'ロゴデザイン',
          description: 'ブランドの本質を表現するオリジナルロゴデザインを制作します。'
        },
        {
          id: 2,
          title: 'グラフィックデザイン',
          description: 'パッケージ、パンフレット、ポスターなど各種グラフィックデザインを制作します。'
        },
        {
          id: 3,
          title: 'WEBデザイン',
          description: 'ユーザビリティを重視したモダンなWEBサイトデザインを制作します。'
        }
      ]
    }
  },
  computed: {
    filteredWorks() {
      if (this.activeFilter === 'all') {
        return this.works
      }
      return this.works.filter(work => work.category === this.activeFilter)
    }
  },
  mounted() {
    this.initParallax()
    this.initScrollAnimations()
    this.initStatsCounter()
  },
  methods: {
    setFilter(filter) {
      this.activeFilter = filter
    },
    initParallax() {
      window.addEventListener('scroll', () => {
        const scrolled = window.pageYOffset
        const rate = scrolled * -0.5
        if (this.$refs.parallaxBg) {
          this.$refs.parallaxBg.style.transform = `translateY(${rate}px)`
        }
      })
    },
    initScrollAnimations() {
      const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add('visible')
          }
        })
      }, { threshold: 0.1 })

      const elements = document.querySelectorAll('.section-title, .section-subtitle, .work-item, .service-item')
      elements.forEach(el => observer.observe(el))
    },
    initStatsCounter() {
      const statsObserver = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            const target = parseInt(entry.target.getAttribute('data-target'))
            const duration = 2000
            const increment = target / (duration / 16)
            let current = 0
            
            const timer = setInterval(() => {
              current += increment
              if (current >= target) {
                current = target
                clearInterval(timer)
              }
              entry.target.textContent = Math.floor(current)
            }, 16)
            
            statsObserver.unobserve(entry.target)
          }
        })
      }, { threshold: 0.5 })
      
      if (this.$refs.stat1) statsObserver.observe(this.$refs.stat1)
      if (this.$refs.stat2) statsObserver.observe(this.$refs.stat2)
      if (this.$refs.stat3) statsObserver.observe(this.$refs.stat3)
    }
  }
}
</script>
