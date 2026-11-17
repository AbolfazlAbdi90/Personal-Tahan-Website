<script setup lang="ts">
import { ref } from 'vue'

const isDark = ref(false)
const menuOpen = ref(false)

const navItems = [
  { label: 'Home', href: '#home' },
  { label: 'About', href: '#about' },
  { label: 'Experience', href: '#experience' },
  { label: 'Skills', href: '#skills' },
  { label: 'Contact', href: '#contact' },
]

const skills = [
  { name: 'Financial Reporting', level: 95 },
  { name: 'Financial Analysis', level: 90 },
  { name: 'Tax Preparation', level: 85 },
  { name: 'Bookkeeping', level: 95 },
  { name: 'Microsoft Excel', level: 90 },
  { name: 'Accounting Software', level: 85 },
]

const experiences = [
  {
    role: 'Senior Accountant',
    company: 'Company Name',
    date: '2024 — Present',
    description:
      'Managing financial records, preparing financial statements, analyzing financial data and ensuring accurate accounting operations.',
  },
  {
    role: 'Junior Accountant',
    company: 'Previous Company',
    date: '2022 — 2024',
    description:
      'Assisted with bookkeeping, invoice processing, account reconciliation and monthly financial reporting.',
  },
]

const education = [
  {
    degree: "Bachelor's Degree in Accounting",
    institution: 'University Name',
    date: '2018 — 2022',
  },
]

function toggleTheme() {
  isDark.value = !isDark.value
}

function closeMenu() {
  menuOpen.value = false
}
</script>

<template>
  <div
    :class="[
      'portfolio-shell min-h-screen overflow-hidden transition-colors duration-500',
      isDark ? 'dark' : 'light',
    ]"
  >
    <!-- BACKGROUND DECORATION -->
    <div class="pointer-events-none fixed inset-0 overflow-hidden">
      <div class="glow glow-one"></div>
      <div class="glow glow-two"></div>
    </div>

    <!-- HEADER -->
    <header class="relative z-50 mx-auto max-w-7xl px-5 pt-6 sm:px-8">
      <nav
        class="nav-surface flex items-center justify-between rounded-2xl border px-5 py-4 shadow-sm backdrop-blur-xl"
      >
        <!-- LOGO -->
        <a href="#home" class="flex items-center gap-3" @click="closeMenu">
          <div
            class="flex h-10 w-10 items-center justify-center rounded-xl logo-gradient text-white"
          >
            <span class="text-lg font-bold">NT</span>
          </div>

          <div>
            <p class="text-sm font-bold tracking-wide main-text">Narges Tahan</p>
            <p class="text-[10px] tracking-[0.2em] muted-text">ACCOUNTANT</p>
          </div>
        </a>

        <!-- DESKTOP NAV -->
        <div class="hidden items-center gap-8 md:flex">
          <a
            v-for="item in navItems"
            :key="item.label"
            :href="item.href"
            class="nav-link text-sm font-medium transition"
          >
            {{ item.label }}
          </a>
        </div>

        <!-- ACTIONS -->
        <div class="flex items-center gap-3">
          <button
            @click="toggleTheme"
            aria-label="Toggle theme"
            class="theme-button flex h-10 w-10 items-center justify-center rounded-xl border transition hover:scale-105"
          >
            <svg
              v-if="!isDark"
              xmlns="http://www.w3.org/2000/svg"
              width="19"
              height="19"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              stroke-linecap="round"
            >
              <path
                d="M12 3v2m0 14v2M5.64 5.64l1.42 1.42m9.88 9.88 1.42 1.42M3 12h2m14 0h2M5.64 18.36l1.42-1.42m9.88-9.88 1.42-1.42"
              />
              <circle cx="12" cy="12" r="4" />
            </svg>

            <svg
              v-else
              xmlns="http://www.w3.org/2000/svg"
              width="19"
              height="19"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="1.8"
              stroke-linecap="round"
              stroke-linejoin="round"
            >
              <path d="M20.9 13A9 9 0 0 1 11 3.1 9 9 0 1 0 20.9 13Z" />
            </svg>
          </button>

          <a
            href="#contact"
            class="hidden rounded-xl accent-button px-5 py-3 text-xs font-bold transition hover:-translate-y-0.5 sm:block"
          >
            Let's Talk
          </a>

          <!-- MOBILE MENU -->
          <button
            @click="menuOpen = !menuOpen"
            class="theme-button flex h-10 w-10 items-center justify-center rounded-xl border md:hidden"
            aria-label="Toggle navigation"
          >
            <svg
              v-if="!menuOpen"
              width="21"
              height="21"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
            >
              <path d="M4 7h16M4 12h16M4 17h16" />
            </svg>
            <svg
              v-else
              width="21"
              height="21"
              viewBox="0 0 24 24"
              fill="none"
              stroke="currentColor"
              stroke-width="2"
              stroke-linecap="round"
            >
              <path d="m18 6-12 12M6 6l12 12" />
            </svg>
          </button>
        </div>
      </nav>

      <!-- MOBILE NAV -->
      <div v-if="menuOpen" class="nav-surface mt-3 rounded-2xl border p-4 shadow-xl md:hidden">
        <a
          v-for="item in navItems"
          :key="item.label"
          :href="item.href"
          @click="closeMenu"
          class="nav-link block rounded-xl px-4 py-3 text-sm font-medium"
        >
          {{ item.label }}
        </a>
      </div>
    </header>

    <main class="relative z-10 mx-auto max-w-7xl px-5 sm:px-8">
      <!-- HERO -->
      <section
        id="home"
        class="grid min-h-[680px] items-center gap-14 py-24 lg:grid-cols-2 lg:py-28"
      >
        <!-- HERO CONTENT -->
        <div>
          <div
            class="mb-7 inline-flex items-center gap-2 rounded-full border badge-surface px-4 py-2"
          >
            <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
            <span class="text-xs font-medium muted-text"> Available for opportunities </span>
          </div>

          <p class="mb-5 text-sm font-semibold tracking-[0.25em] accent-text">
            HELLO, I'M Narges Tahan
          </p>

          <h1
            class="max-w-2xl text-5xl font-bold leading-[1.2] tracking-tight main-text sm:text-6xl xl:text-7xl"
          >
            Turning Numbers Into
            <span class="gradient-text">Meaningful</span>
            Insights.
          </h1>

          <p class="mt-7 max-w-xl text-base leading-8 muted-text sm:text-lg">
            Dedicated Accountant specializing in financial management, reporting and analysis.
            Helping businesses make smarter financial decisions through accuracy and insight.
          </p>

          <div class="mt-9 flex flex-wrap items-center gap-4">
            <a
              href="#contact"
              class="accent-button inline-flex items-center gap-3 rounded-xl px-7 py-4 text-sm font-bold transition hover:-translate-y-1"
            >
              Get In Touch
              <span>↗</span>
            </a>

            <a
              href="#experience"
              class="secondary-button rounded-xl border px-7 py-4 text-sm font-semibold transition hover:-translate-y-1"
            >
              Explore My Work
            </a>
          </div>

          <!-- SOCIAL LINKS -->
          <div class="mt-12 flex items-center gap-5">
            <span class="text-xs muted-text">FOLLOW ME</span>

            <a href="#" class="social-link">LinkedIn ↗</a>
            <a href="#" class="social-link">Email ↗</a>
          </div>
        </div>

        <!-- HERO/ VISUAL -->

        <div class="relative mx-auto w-full max-w-[440px] px-3 sm:px-0">
          <div
            class="hero-card group relative overflow-hidden rounded-[2rem] border p-3 shadow-2xl transition-all duration-500 hover:-translate-y-2 sm:rounded-[2.5rem] sm:p-4"
          >
            <!-- IMAGE CONTAINER -->
            <div
              class="relative aspect-[4/5] w-full overflow-hidden rounded-[1.5rem] bg-[#ead9ed] sm:rounded-[2rem]"
            >
              <!-- PROFILE IMAGE -->
              <img
                src="/image/Narges.jpg"
                alt="Narges Tahan - Professional Accountant"
                class="absolute inset-0 h-full w-full object-cover object-center transition-transform duration-700 group-hover:scale-105"
              />

              <!-- IMAGE OVERLAY -->
              <div
                class="absolute inset-0 bg-gradient-to-t from-[#21172d]/95 via-[#21172d]/20 to-transparent"
              ></div>

              <!-- TOP BADGE -->
              <div
                class="absolute left-4 top-4 flex items-center gap-2 rounded-full border border-white/30 bg-white/20 px-3 py-2 backdrop-blur-xl sm:left-5 sm:top-5"
              >
                <span class="h-2 w-2 rounded-full bg-emerald-400"></span>
              </div>

              <!-- BOTTOM CONTENT -->
              <div class="absolute inset-x-0 bottom-0 p-5 sm:p-7">
                <div class="mt-5 flex items-center justify-between border-t border-white/20 pt-4">
                  <span class="text-xs text-white/70"> Precision · Trust · Excellence </span>

                  <span
                    class="flex h-9 w-9 items-center justify-center rounded-full border border-white/30 bg-white/10 text-white backdrop-blur-md"
                  >
                    ↗
                  </span>
                </div>
              </div>
            </div>
          </div>

          <!-- DECORATIVE ELEMENT -->
          <div
            class="pointer-events-none absolute -right-3 -top-4 -z-10 h-28 w-28 rounded-full bg-[#d9c5f2]/40 blur-3xl"
          ></div>

          <div
            class="pointer-events-none absolute -bottom-5 -left-4 -z-10 h-32 w-32 rounded-full bg-[#f5c8df]/50 blur-3xl"
          ></div>
        </div>
      </section>

      <!-- STATS -->
      <section class="grid grid-cols-2 gap-4 pb-24 md:grid-cols-4">
        <div
          v-for="stat in [
            { value: '04+', label: 'Years Experience' },
            { value: '25+', label: 'Projects Completed' },
            { value: '15+', label: 'Happy Clients' },
            { value: '06+', label: 'Core Skills' },
          ]"
          :key="stat.label"
          class="stat-card rounded-2xl border p-6 text-center transition hover:-translate-y-1"
        >
          <h3 class="text-3xl font-bold gradient-text">
            {{ stat.value }}
          </h3>
          <p class="mt-2 text-xs muted-text sm:text-sm">
            {{ stat.label }}
          </p>
        </div>
      </section>

      <!-- ABOUT -->
      <section id="about" class="section-spacing">
        <div class="section-heading">
          <span class="section-label">ABOUT ME</span>
          <h2 class="section-title">
            More Than Just
            <span class="gradient-text">Numbers.</span>
          </h2>
          <p class="section-description">
            A little introduction to my professional journey and what drives me.
          </p>
        </div>

        <div class="grid items-center gap-10 lg:grid-cols-2">
          <div class="about-card rounded-3xl border p-7 sm:p-10">
            <div
              class="mb-7 flex h-14 w-14 items-center justify-center rounded-2xl icon-purple text-2xl"
            >
              NT
            </div>

            <h3 class="mb-5 text-2xl font-bold main-text">Passionate About Financial Excellence</h3>

            <p class="text-sm leading-8 muted-text">
              I am a detail-oriented accounting professional with a strong passion for financial
              accuracy, analytical thinking and continuous learning.
            </p>

            <p class="mt-5 text-sm leading-8 muted-text">
              My goal is to transform complex financial information into clear insights that support
              better business decisions. I believe that great accounting is not just about numbers,
              but about creating trust and value.
            </p>

            <div class="mt-8 flex flex-wrap gap-3">
              <span class="tag">Analytical Thinking</span>
              <span class="tag">Problem Solving</span>
              <span class="tag">Attention to Detail</span>
            </div>
          </div>

          <div class="grid gap-4 sm:grid-cols-2">
            <div class="feature-card rounded-3xl border p-7">
              <span class="text-3xl">📈</span>
              <h3 class="mt-5 font-bold main-text">Financial Analysis</h3>
              <p class="mt-3 text-sm leading-7 muted-text">
                Understanding financial performance and identifying opportunities for growth.
              </p>
            </div>

            <div class="feature-card rounded-3xl border p-7">
              <span class="text-3xl">📋</span>
              <h3 class="mt-5 font-bold main-text">Reporting</h3>
              <p class="mt-3 text-sm leading-7 muted-text">
                Preparing accurate reports for effective decision-making.
              </p>
            </div>

            <div class="feature-card rounded-3xl border p-7">
              <span class="text-3xl">💼</span>
              <h3 class="mt-5 font-bold main-text">Management</h3>
              <p class="mt-3 text-sm leading-7 muted-text">
                Organizing financial operations with precision and care.
              </p>
            </div>

            <div class="feature-card rounded-3xl border p-7">
              <span class="text-3xl">🎯</span>
              <h3 class="mt-5 font-bold main-text">Accuracy</h3>
              <p class="mt-3 text-sm leading-7 muted-text">
                Maintaining reliable financial records and documentation.
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- EXPERIENCE -->
      <section id="experience" class="section-spacing">
        <div class="section-heading">
          <span class="section-label">MY JOURNEY</span>
          <h2 class="section-title">
            Professional
            <span class="gradient-text">Experience.</span>
          </h2>
          <p class="section-description">
            My career path and the experience I've gained along the way.
          </p>
        </div>

        <div class="timeline relative mx-auto max-w-4xl">
          <div
            v-for="(experience, index) in experiences"
            :key="experience.role"
            class="timeline-item relative pb-12 pl-10 sm:pl-14"
          >
            <div class="timeline-dot"></div>

            <div class="experience-card rounded-3xl border p-6 sm:p-8">
              <div class="flex flex-col justify-between gap-4 sm:flex-row sm:items-center">
                <div>
                  <span class="section-label">
                    {{ index === 0 ? 'CURRENT POSITION' : 'PREVIOUS POSITION' }}
                  </span>
                  <h3 class="mt-3 text-xl font-bold main-text">
                    {{ experience.role }}
                  </h3>
                  <p class="mt-2 text-sm accent-text font-semibold">
                    {{ experience.company }}
                  </p>
                </div>

                <span class="date-tag self-start">
                  {{ experience.date }}
                </span>
              </div>

              <p class="mt-6 text-sm leading-8 muted-text">
                {{ experience.description }}
              </p>
            </div>
          </div>
        </div>
      </section>

      <!-- EDUCATION -->
      <section id="education" class="section-spacing">
        <!-- SECTION HEADER -->
        <div class="section-heading">
          <span class="section-label">EDUCATION</span>

          <h2 class="section-title">
            Academic
            <span class="gradient-text">Background.</span>
          </h2>

          <p class="section-description">
            My academic journey and educational background in accounting.
          </p>
        </div>

        <!-- EDUCATION CARD -->
        <div class="mx-auto max-w-4xl">
          <div
            class="education-card group relative overflow-hidden rounded-3xl border p-6 transition-all duration-500 hover:-translate-y-1 hover:shadow-xl sm:p-9"
          >
            <!-- BACKGROUND DECORATION -->
            <div
              class="pointer-events-none absolute -right-16 -top-16 h-48 w-48 rounded-full bg-[#dfc9f4]/20 blur-3xl transition duration-500 group-hover:bg-[#dfc9f4]/40"
            ></div>

            <div class="relative flex flex-col gap-7 sm:flex-row sm:items-center">
              <!-- UNIVERSITY ICON -->
              <div
                class="flex h-16 w-16 shrink-0 items-center justify-center rounded-2xl bg-gradient-to-br from-[#f3cce2] to-[#d5c1f2] shadow-lg shadow-purple-200/20 sm:h-20 sm:w-20"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="34"
                  height="34"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="#664879"
                  stroke-width="1.6"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                >
                  <path d="m2 10 10-6 10 6-10 6-10-6Z" />
                  <path d="M6 12v5c3.5 3 8.5 3 12 0v-5" />
                  <path d="M22 10v6" />
                </svg>
              </div>

              <!-- EDUCATION INFORMATION -->
              <div class="min-w-0 flex-1">
                <div class="flex flex-wrap items-center gap-3">
                  <span class="section-label"> UNIVERSITY EDUCATION </span>

                  <span
                    class="rounded-full border border-emerald-400/20 bg-emerald-400/10 px-3 py-1 text-[10px] font-bold text-emerald-500"
                  >
                    CURRENTLY STUDYING
                  </span>
                </div>

                <h3 class="mt-4 text-xl font-bold leading-relaxed main-text sm:text-2xl">
                  Bachelor's Student in Accounting
                </h3>

                <p class="mt-3 text-sm font-semibold accent-text sm:text-base">
                  Islamic Azad University
                </p>

                <p class="mt-2 text-xs leading-6 muted-text sm:text-sm">
                  Science and Research Branch
                </p>

                <!-- DATE -->
                <div class="mt-6 flex flex-wrap items-center gap-3">
                  <div
                    class="flex items-center gap-2 rounded-xl bg-[var(--surface-soft)] px-4 py-3"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      width="16"
                      height="16"
                      viewBox="0 0 24 24"
                      fill="none"
                      stroke="currentColor"
                      stroke-width="1.8"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                      class="accent-text"
                    >
                      <rect x="3" y="4" width="18" height="18" rx="2" />
                      <path d="M16 2v4M8 2v4M3 10h18" />
                    </svg>

                    <span class="text-xs font-semibold main-text"> 2025 — Present </span>
                  </div>

                  <span class="text-xs muted-text"> Undergraduate Program </span>
                </div>
              </div>

              <!-- DECORATIVE NUMBER -->
              <div
                class="hidden select-none text-7xl font-black tracking-tighter text-[var(--surface-soft)] lg:block"
              >
                01
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- SKILLS -->
      <section id="skills" class="section-spacing">
        <div class="section-heading">
          <span class="section-label">MY EXPERTISE</span>
          <h2 class="section-title">
            Professional
            <span class="gradient-text">Skills.</span>
          </h2>
          <p class="section-description">
            The tools and abilities I use to deliver accurate financial results.
          </p>
        </div>

        <div class="skills-card grid gap-10 rounded-3xl border p-7 sm:p-10 lg:grid-cols-2">
          <div v-for="skill in skills" :key="skill.name">
            <div class="mb-3 flex items-center justify-between">
              <span class="text-sm font-semibold main-text">
                {{ skill.name }}
              </span>
              <span class="text-sm font-bold accent-text"> {{ skill.level }}% </span>
            </div>

            <div class="skill-track h-2.5 overflow-hidden rounded-full">
              <div
                class="skill-progress h-full rounded-full transition-all duration-1000"
                :style="{ width: skill.level + '%' }"
              ></div>
            </div>
          </div>
        </div>
      </section>

      <!-- CONTACT -->
      <section id="contact" class="section-spacing pb-28">
        <div
          class="contact-card relative overflow-hidden rounded-[2rem] border p-8 text-center sm:p-16"
        >
          <div class="contact-decoration"></div>

          <div class="relative z-10">
            <span class="section-label">GET IN TOUCH</span>

            <h2 class="mx-auto mt-6 max-w-2xl text-4xl font-bold main-text sm:text-5xl">
              Let's Create Something
              <span class="gradient-text">Meaningful.</span>
            </h2>

            <p class="mx-auto mt-6 max-w-xl text-sm leading-8 muted-text">
              Have an opportunity, a question or just want to connect? I'd love to hear from you.
            </p>

            <div class="mt-9 flex flex-wrap justify-center gap-4">
              <a
                href="mailto:hello@example.com"
                class="accent-button rounded-xl px-8 py-4 text-sm font-bold transition hover:-translate-y-1"
              >
                Send Me an Email ↗
              </a>

              <a
                href="#home"
                class="secondary-button rounded-xl border px-8 py-4 text-sm font-semibold transition hover:-translate-y-1"
              >
                Back to Top ↑
              </a>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- FOOTER -->
    <footer class="footer-surface relative z-10 border-t">
      <div
        class="mx-auto flex max-w-7xl flex-col items-center justify-between gap-5 px-5 py-8 sm:flex-row sm:px-8"
      >
        <p class="text-sm font-bold main-text">Narges Tahan.</p>

        <p class="text-xs muted-text">
          © {{ new Date().getFullYear() }} Narges Tahan. All rights reserved.
        </p>
      </div>
    </footer>
  </div>
</template>

<style>
/* THEME VARIABLES */

.portfolio-shell {
  --page: #fff9fc;
  --surface: #ffffff;
  --surface-soft: #fff0f7;
  --surface-card: rgba(255, 255, 255, 0.78);
  --border: #f0e1ec;
  --main: #493653;
  --muted: #82748a;
  --accent: #b57bc9;
  --pink: #f5c9df;
  --purple: #d9c8f4;
  --shadow: rgba(107, 67, 112, 0.08);

  background: var(--page);
  color: var(--main);
}

.portfolio-shell.dark {
  --page: #17131f;
  --surface: #211a2b;
  --surface-soft: #302439;
  --surface-card: rgba(37, 29, 48, 0.9);
  --border: #40334d;
  --main: #f8eff9;
  --muted: #b8aabd;
  --accent: #d2b0ec;
  --pink: #e7b8d5;
  --purple: #c9b0f0;
  --shadow: rgba(0, 0, 0, 0.2);
}

/* GENERAL */

.portfolio-shell {
  scroll-behavior: smooth;
}

.main-text {
  color: var(--main);
}

.muted-text {
  color: var(--muted);
}

.accent-text {
  color: var(--accent);
}

.nav-surface,
.theme-button,
.floating-card {
  background: var(--surface-card);
  border-color: var(--border);
}

.nav-link {
  color: var(--muted);
}

.nav-link:hover,
.social-link:hover {
  color: var(--accent);
}

.logo-gradient {
  background: linear-gradient(135deg, #dca5ce, #a88bd8);
}

.gradient-text {
  background: linear-gradient(120deg, #d58ab8, #a58bdc);
  background-clip: text;
  -webkit-background-clip: text;
  color: transparent;
}

.accent-button {
  background: linear-gradient(120deg, #c68fc6, #a78bd8);
  color: white;
  box-shadow: 0 8px 24px rgba(180, 130, 196, 0.22);
}

.secondary-button {
  color: var(--main);
  border-color: var(--border);
  background: var(--surface-card);
}

.badge-surface {
  background: var(--surface-card);
  border-color: var(--border);
}

.social-link {
  color: var(--main);
  font-size: 12px;
  font-weight: 600;
  transition: color 0.2s;
}

/* BACKGROUND */

.glow {
  position: absolute;
  width: 420px;
  height: 420px;
  border-radius: 50%;
  filter: blur(110px);
  opacity: 0.22;
}

.glow-one {
  top: 100px;
  left: -180px;
  background: #e8b4db;
}

.glow-two {
  top: 650px;
  right: -200px;
  background: #c5b0f2;
}

.dark .glow {
  opacity: 0.12;
}

/* HERO */

.hero-card {
  background: var(--surface-card);
  border-color: var(--border);
  box-shadow: 0 30px 80px var(--shadow);
}

.hero-image {
  background: linear-gradient(145deg, #e5b8d8, #b8a2e7);
}

.hero-gradient {
  background:
    radial-gradient(circle at 20% 20%, rgba(255, 255, 255, 0.4), transparent 35%),
    linear-gradient(145deg, rgba(230, 180, 216, 0.4), rgba(153, 126, 208, 0.55));
}

.floating-card {
  box-shadow: 0 15px 40px var(--shadow);
}

.icon-pink {
  background: rgba(229, 179, 213, 0.25);
}

.icon-purple {
  background: rgba(190, 167, 235, 0.24);
}

/* CARDS */

.stat-card,
.about-card,
.feature-card,
.experience-card,
.education-card,
.skills-card,
.contact-card {
  background: var(--surface-card);
  border-color: var(--border);
  box-shadow: 0 15px 40px var(--shadow);
}

.feature-card {
  transition:
    transform 0.3s,
    border-color 0.3s;
}

.feature-card:hover {
  transform: translateY(-5px);
  border-color: var(--accent);
}

.tag,
.date-tag {
  display: inline-block;
  border-radius: 999px;
  padding: 8px 13px;
  font-size: 11px;
  font-weight: 600;
  background: var(--surface-soft);
  color: var(--accent);
}

/* SECTION HEADINGS */

.section-spacing {
  padding-top: 90px;
}

.section-heading {
  margin-bottom: 45px;
}

.section-label {
  display: inline-block;
  color: var(--accent);
  font-size: 11px;
  font-weight: 800;
  letter-spacing: 0.22em;
}

.section-title {
  margin-top: 16px;
  color: var(--main);
  font-size: clamp(32px, 5vw, 46px);
  font-weight: 800;
  letter-spacing: -0.04em;
}

.section-description {
  margin-top: 15px;
  color: var(--muted);
  font-size: 14px;
  line-height: 1.8;
}

/* EXPERIENCE TIMELINE */

.timeline::before {
  position: absolute;
  top: 0;
  bottom: 45px;
  left: 10px;
  width: 1px;
  content: '';
  background: var(--border);
}

.timeline-dot {
  position: absolute;
  top: 25px;
  left: 4px;
  width: 13px;
  height: 13px;
  border: 3px solid var(--page);
  border-radius: 50%;
  background: var(--accent);
  box-shadow: 0 0 0 3px var(--purple);
}

/* SKILLS */

.skill-track {
  background: var(--surface-soft);
}

.skill-progress {
  background: linear-gradient(90deg, #e2a9d0, #ad94df);
}

/* CONTACT */

.contact-card {
  background:
    radial-gradient(circle at 10% 10%, rgba(222, 193, 239, 0.18), transparent 35%),
    var(--surface-card);
}

.contact-decoration {
  position: absolute;
  top: -180px;
  right: -100px;
  width: 350px;
  height: 350px;
  border: 1px solid var(--border);
  border-radius: 50%;
  pointer-events: none;
  box-shadow:
    0 0 0 40px var(--shadow),
    0 0 0 80px var(--shadow);
}

.footer-surface {
  border-color: var(--border);
  background: var(--surface-card);
}

/* RESPONSIVE */

@media (max-width: 640px) {
  .section-spacing {
    padding-top: 65px;
  }

  .section-heading {
    margin-bottom: 30px;
  }

  .hero-card {
    margin: 20px;
  }

  .floating-card {
    left: -15px;
  }
}

@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    scroll-behavior: auto !important;
    transition-duration: 0.01ms !important;
  }
}
</style>
