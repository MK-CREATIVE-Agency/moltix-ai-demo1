<!DOCTYPE html>
<html lang="en" dir="ltr" id="htmlRoot">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Moltix AI — Custom AI Systems & Workflow Automation</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700;800&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            voidbg: '#05050A',
            cardbg: '#0C0D18',
            neonblue: '#00D2FF',
            neonpurple: '#7B2CBF',
            softpurple: '#A855F7'
          },
          fontFamily: {
            sans: ['"Plus Jakarta Sans"', '"Cairo"', 'sans-serif'],
            arabic: ['"Cairo"', '"Plus Jakarta Sans"', 'sans-serif']
          }
        }
      }
    }
  </script>
  <style>
    body {
      background-color: #05050A;
      color: #F8FAFC;
      overflow-x: hidden;
    }
    .ambient-glow {
      background: radial-gradient(circle at 18% 12%, rgba(0, 210, 255, 0.14), transparent 45%),
                  radial-gradient(circle at 82% 22%, rgba(123, 44, 191, 0.18), transparent 50%),
                  radial-gradient(circle at 50% 88%, rgba(0, 210, 255, 0.08), transparent 55%);
    }
    .glass-card {
      background: rgba(12, 13, 24, 0.88);
      backdrop-filter: blur(14px);
      border: 1px solid rgba(255, 255, 255, 0.09);
    }
    .glass-card:hover {
      border-color: rgba(0, 210, 255, 0.35);
    }
    .brand-gradient-text {
      background: linear-gradient(90deg, #00D2FF 0%, #A855F7 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .brand-btn {
      background: linear-gradient(135deg, #00D2FF 0%, #7B2CBF 100%);
      transition: transform 0.18s ease, box-shadow 0.18s ease, filter 0.18s ease;
    }
    .brand-btn:hover {
      transform: translateY(-1px);
      box-shadow: 0 10px 28px -8px rgba(0, 210, 255, 0.45);
      filter: brightness(1.07);
    }
    .brand-btn:active {
      transform: scale(0.98);
    }
    .chat-scroll::-webkit-scrollbar {
      width: 5px;
    }
    .chat-scroll::-webkit-scrollbar-thumb {
      background: rgba(255, 255, 255, 0.14);
      border-radius: 9999px;
    }
  </style>
</head>
<body class="min-h-screen relative selection:bg-neonblue/30 selection:text-white">
  <div class="fixed inset-0 ambient-glow pointer-events-none z-0"></div>

  <!-- Navbar -->
  <header class="relative z-20 border-b border-white/10 bg-voidbg/85 backdrop-blur-md sticky top-0">
    <div class="max-w-6xl mx-auto px-4 sm:px-6 h-16 flex items-center justify-between">
      <a href="#" class="flex items-center gap-3">
        <!-- Geometric Crystal Emblem (No animals, no text, no background threads/grids) -->
        <svg class="w-9 h-9 shrink-0" viewBox="0 0 64 64" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <defs>
            <linearGradient id="cryst1" x1="8" y1="6" x2="56" y2="58" gradientUnits="userSpaceOnUse">
              <stop offset="0%" stop-color="#00D2FF" />
              <stop offset="100%" stop-color="#7B2CBF" />
            </linearGradient>
            <linearGradient id="cryst2" x1="52" y1="10" x2="14" y2="54" gradientUnits="userSpaceOnUse">
              <stop offset="0%" stop-color="#A855F7" />
              <stop offset="100%" stop-color="#00D2FF" />
            </linearGradient>
          </defs>
          <polygon points="32,4 54,18 54,46 32,60 10,46 10,18" stroke="url(#cryst1)" stroke-width="2.5" fill="rgba(0,210,255,0.06)" />
          <polygon points="32,12 46,24 38,50 26,50 18,24" stroke="url(#cryst2)" stroke-width="2" fill="rgba(123,44,191,0.14)" />
          <polygon points="32,18 40,32 32,46 24,32" fill="url(#cryst1)" />
        </svg>
        <div class="leading-tight">
          <div class="font-extrabold text-lg tracking-tight text-white">Moltix <span class="brand-gradient-text">AI</span></div>
          <div class="text-[11px] text-slate-400" data-i18n="groupLabel">MK CREATIVE International Group</div>
        </div>
      </a>

      <div class="flex items-center gap-2 sm:gap-3">
        <a href="#live-demo" class="hidden sm:inline-block px-3 py-1.5 rounded-lg text-xs font-semibold text-slate-300 hover:text-white transition" data-i18n="navTryBot">
          Try Live AI
        </a>
        <button
          type="button"
          id="langToggle"
          class="px-3 py-1.5 rounded-lg text-xs font-semibold border border-white/15 bg-white/5 hover:bg-white/10 text-slate-200 transition cursor-pointer"
        >
          العربية
        </button>
        <a
          href="#demo-form"
          class="brand-btn px-3.5 py-1.5 rounded-lg text-xs sm:text-sm font-bold text-white"
          data-i18n="navCta"
        >
          Get $5 Demo
        </a>
      </div>
    </div>
  </header>

  <main class="relative z-10">
    <!-- Hero Section -->
    <section class="max-w-5xl mx-auto px-4 sm:px-6 pt-12 pb-10 text-center">
      <div class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-white/5 border border-neonblue/30 text-xs font-medium text-neonblue mb-6">
        <span class="w-2 h-2 rounded-full bg-neonblue animate-pulse"></span>
        <span data-i18n="heroBadge">Custom IT Software • AI Agents • Workflow Automation</span>
      </div>

      <h1 class="text-3xl sm:text-5xl font-extrabold tracking-tight leading-tight mb-5" data-i18n="heroTitle">
        Test a Custom AI Prototype Built for Your Workflow for <span class="brand-gradient-text">$5</span>
      </h1>

      <p class="max-w-2xl mx-auto text-slate-300 text-base sm:text-lg leading-relaxed mb-8" data-i18n="heroSubtitle">
        Moltix AI builds practical AI assistants, automated operational pipelines, and tailored software tools. Test our live AI assistant below or request a working prototype built around your business for $5.
      </p>

      <div class="flex flex-col sm:flex-row items-center justify-center gap-3.5">
        <a
          href="#demo-form"
          class="w-full sm:w-auto brand-btn px-6 py-3.5 rounded-xl text-sm sm:text-base font-bold text-white text-center"
          data-i18n="heroPrimaryBtn"
        >
          Request Your $5 Demo
        </a>
        <a
          href="#live-demo"
          class="w-full sm:w-auto px-6 py-3.5 rounded-xl text-sm sm:text-base font-semibold border border-neonblue/35 bg-neonblue/10 hover:bg-neonblue/15 text-neonblue transition text-center"
          data-i18n="heroSecondaryBtn"
        >
          Test Live AI Assistant
        </a>
      </div>
    </section>

    <!-- Services Section -->
    <section id="services" class="max-w-6xl mx-auto px-4 sm:px-6 py-8">
      <div class="text-center mb-8">
        <h2 class="text-2xl sm:text-3xl font-bold mb-2" data-i18n="servicesTitle">Core Capabilities</h2>
        <p class="text-slate-400 text-sm sm:text-base" data-i18n="servicesSubtitle">
          Practical systems engineered to cut manual work and speed up daily operations.
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-5">
        <div class="glass-card rounded-2xl p-6 transition flex flex-col justify-between">
          <div>
            <div class="w-10 h-10 rounded-xl bg-neonblue/10 border border-neonblue/30 flex items-center justify-center text-neonblue font-bold text-sm mb-4">01</div>
            <h3 class="text-lg font-bold text-white mb-2" data-i18n="s1Title">AI Assistants & Smart Chatbots</h3>
            <p class="text-slate-300 text-sm leading-relaxed mb-4" data-i18n="s1Desc">
              Context-aware assistants trained on your business info to answer inquiries, qualify leads, and route requests smoothly.
            </p>
          </div>
          <div class="text-xs font-semibold text-neonblue/90 pt-3 border-t border-white/10" data-i18n="s1Tag">
            Demo Starter: 24/7 Support & Lead Bot
          </div>
        </div>

        <div class="glass-card rounded-2xl p-6 transition flex flex-col justify-between">
          <div>
            <div class="w-10 h-10 rounded-xl bg-softpurple/15 border border-softpurple/35 flex items-center justify-center text-softpurple font-bold text-sm mb-4">02</div>
            <h3 class="text-lg font-bold text-white mb-2" data-i18n="s2Title">Workflow & Process Automation</h3>
            <p class="text-slate-300 text-sm leading-relaxed mb-4" data-i18n="s2Desc">
              Automated pipelines connecting forms, sheets, CRMs, and alerts so repetitive tasks run reliably without manual entry.
            </p>
          </div>
          <div class="text-xs font-semibold text-softpurple pt-3 border-t border-white/10" data-i18n="s2Tag">
            Demo Starter: Core Ops Automation Flow
          </div>
        </div>

        <div class="glass-card rounded-2xl p-6 transition flex flex-col justify-between">
          <div>
            <div class="w-10 h-10 rounded-xl bg-neonblue/10 border border-neonblue/30 flex items-center justify-center text-neonblue font-bold text-sm mb-4">03</div>
            <h3 class="text-lg font-bold text-white mb-2" data-i18n="s3Title">Custom AI Micro-Tools</h3>
            <p class="text-slate-300 text-sm leading-relaxed mb-4" data-i18n="s3Desc">
              Focused internal tools for extracting data from documents, summarizing reports, or streamlining specific IT tasks.
            </p>
          </div>
          <div class="text-xs font-semibold text-neonblue/90 pt-3 border-t border-white/10" data-i18n="s3Tag">
            Demo Starter: Smart Data / Doc Extractor
          </div>
        </div>
      </div>
    </section>

    <!-- Interactive Live AI Assistant Demo Section (Connected to Cloudflare Worker + Formspree) -->
    <section id="live-demo" class="max-w-3xl mx-auto px-4 sm:px-6 py-10">
      <div class="text-center mb-6">
        <span class="inline-block px-3 py-1 rounded-full text-xs font-bold bg-softpurple/15 text-softpurple border border-softpurple/30 mb-2" data-i18n="chatBadge">
          INTERACTIVE SANDBOX
        </span>
        <h2 class="text-2xl sm:text-3xl font-extrabold text-white mb-2" data-i18n="chatTitle">
          Test Moltix AI Live Assistant
        </h2>
        <p class="text-slate-400 text-sm" data-i18n="chatSubtitle">
          Ask about Moltix AI services, the $5 prototype workflow, or leave your contact directly inside the chat.
        </p>
      </div>

      <div class="glass-card rounded-3xl flex flex-col overflow-hidden shadow-2xl h-[470px]">
        <!-- Status Bar -->
        <div class="px-4 py-3 border-b border-white/10 bg-white/[0.02] flex items-center justify-between text-xs">
          <div class="flex items-center gap-2 text-slate-300">
            <span class="w-2 h-2 rounded-full bg-emerald-400 animate-pulse"></span>
            <span data-i18n="chatStatus">Moltix AI Concierge • Connected</span>
          </div>
          <div class="flex items-center gap-2">
            <span id="leadBadge" class="hidden px-2 py-0.5 rounded-md bg-emerald-500/15 text-emerald-300 border border-emerald-400/30 font-semibold">
              Sent ✓
            </span>
            <button type="button" id="resetChatBtn" class="px-2.5 py-1 rounded-lg border border-white/15 bg-white/5 hover:bg-white/10 text-slate-300 transition cursor-pointer" data-i18n="chatReset">
              Reset
            </button>
          </div>
        </div>

        <!-- Messages -->
        <div id="chatMessages" class="chat-scroll flex-1 p-4 sm:p-5 space-y-3.5 overflow-y-auto"></div>

        <!-- Quick Chips -->
        <div id="quickChips" class="px-4 pt-2 pb-2 flex flex-wrap gap-2 border-t border-white/5 bg-voidbg/40"></div>

        <!-- Input -->
        <form id="chatForm" class="p-3 sm:p-4 border-t border-white/10 bg-voidbg/85 flex items-center gap-2.5">
          <input
            type="text"
            id="chatInput"
            autocomplete="off"
            placeholder="Ask Moltix AI a question..."
            class="flex-1 rounded-xl bg-cardbg border border-white/15 px-4 py-3 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-neonblue transition"
          />
          <button type="submit" id="chatSendBtn" class="brand-btn px-5 py-3 rounded-xl text-sm font-bold text-white shrink-0 cursor-pointer" data-i18n="chatSend">
            Send
          </button>
        </form>
      </div>
    </section>

    <!-- $5 Custom Prototype Request Form Section (Connected to Formspree) -->
    <section id="demo-form" class="max-w-3xl mx-auto px-4 sm:px-6 py-10">
      <div class="glass-card rounded-3xl p-6 sm:p-10 border border-white/10 shadow-2xl">
        <div class="flex flex-wrap items-center justify-between gap-2 mb-6">
          <div>
            <span class="inline-block px-3 py-1 rounded-full text-xs font-bold bg-neonblue/15 text-neonblue border border-neonblue/30 mb-2" data-i18n="formBadge">
              $5 CUSTOM PROTOTYPE
            </span>
            <h2 class="text-2xl sm:text-3xl font-extrabold text-white" data-i18n="formTitle">
              Request Your Demo Prototype
            </h2>
          </div>
          <div class="text-right">
            <div class="text-2xl font-extrabold brand-gradient-text">$5</div>
            <div class="text-[11px] text-slate-400" data-i18n="formPriceNote">Demo trial fee</div>
          </div>
        </div>

        <p class="text-slate-300 text-sm mb-6 leading-relaxed" data-i18n="formDesc">
          Share a quick overview of what you want to test. Your request goes directly to Moltix AI, and we will follow up with confirmation and next steps to start building your demo.
        </p>

        <form id="moltixForm" action="https://formspree.io/f/xdegjjyy" method="POST" class="space-y-4">
          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div>
              <label for="fullName" class="block text-xs font-semibold text-slate-300 mb-1.5" data-i18n="labelName">Full Name *</label>
              <input
                type="text"
                id="fullName"
                name="name"
                required
                placeholder="Alex Morgan"
                class="w-full rounded-xl bg-voidbg/90 border border-white/15 px-4 py-3 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-neonblue transition"
              />
            </div>

            <div>
              <label for="email" class="block text-xs font-semibold text-slate-300 mb-1.5" data-i18n="labelEmail">Email Address *</label>
              <input
                type="email"
                id="email"
                name="email"
                required
                placeholder="name@company.com"
                class="w-full rounded-xl bg-voidbg/90 border border-white/15 px-4 py-3 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-neonblue transition"
              />
            </div>
          </div>

          <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
            <div>
              <label for="phone" class="block text-xs font-semibold text-slate-300 mb-1.5" data-i18n="labelPhone">WhatsApp / Phone Number *</label>
              <input
                type="tel"
                id="phone"
                name="phone"
                required
                placeholder="+20 100 000 0000"
                class="w-full rounded-xl bg-voidbg/90 border border-white/15 px-4 py-3 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-neonblue transition"
              />
            </div>

            <div>
              <label for="serviceType" class="block text-xs font-semibold text-slate-300 mb-1.5" data-i18n="labelService">Demo Type *</label>
              <select
                id="serviceType"
                name="service_type"
                required
                class="w-full rounded-xl bg-voidbg/90 border border-white/15 px-4 py-3 text-sm text-white focus:outline-none focus:border-neonblue transition"
              >
                <option value="AI Assistant / Chatbot" data-i18n="opt1">AI Assistant / Smart Chatbot</option>
                <option value="Workflow Automation" data-i18n="opt2">Workflow & Process Automation</option>
                <option value="Custom AI Micro-Tool" data-i18n="opt3">Custom AI Micro-Tool</option>
              </select>
            </div>
          </div>

          <div>
            <label for="company" class="block text-xs font-semibold text-slate-300 mb-1.5" data-i18n="labelCompany">Company / Project Name</label>
            <input
              type="text"
              id="company"
              name="company"
              placeholder="Company or brand name"
              class="w-full rounded-xl bg-voidbg/90 border border-white/15 px-4 py-3 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-neonblue transition"
            />
          </div>

          <div>
            <label for="details" class="block text-xs font-semibold text-slate-300 mb-1.5" data-i18n="labelDetails">What should the $5 demo do? *</label>
            <textarea
              id="details"
              name="details"
              rows="4"
              required
              placeholder="Describe the workflow, bot scenario, or tool you want to see in action..."
              class="w-full rounded-xl bg-voidbg/90 border border-white/15 px-4 py-3 text-sm text-white placeholder-slate-500 focus:outline-none focus:border-neonblue transition"
            ></textarea>
          </div>

          <input type="hidden" name="offer_tier" value="$5 Custom Demo" />
          <input type="hidden" name="brand" value="Moltix AI" />

          <button
            type="submit"
            id="submitBtn"
            class="w-full brand-btn py-3.5 px-6 rounded-xl text-sm sm:text-base font-bold text-white cursor-pointer"
            data-i18n="submitBtn"
          >
            Submit $5 Demo Request
          </button>
        </form>

        <div id="successBox" class="hidden mt-6 rounded-2xl border border-emerald-400/30 bg-emerald-500/10 p-5 text-emerald-200">
          <div class="font-bold text-base mb-1" data-i18n="successTitle">Request Received</div>
          <p class="text-sm leading-relaxed" data-i18n="successBody">
            Your $5 demo request has been sent to Moltix AI. We will reach out shortly via your email or WhatsApp with confirmation and next steps to start your prototype.
          </p>
        </div>

        <div id="errorBox" class="hidden mt-6 rounded-2xl border border-rose-400/30 bg-rose-500/10 p-5 text-rose-200">
          <div class="font-bold text-base mb-1" data-i18n="errorTitle">Submission Issue</div>
          <p class="text-sm leading-relaxed" data-i18n="errorBody">
            Something went wrong while sending your request. Please check your connection and try again.
          </p>
        </div>
      </div>
    </section>
  </main>

  <!-- Footer -->
  <footer class="relative z-10 border-t border-white/10 py-7 px-4 sm:px-6 text-center text-xs text-slate-400">
    <div class="max-w-5xl mx-auto flex flex-col sm:flex-row items-center justify-between gap-3">
      <div data-i18n="footerBrand">Moltix AI — Subsidiary of MK CREATIVE International Group</div>
      <div data-i18n="footerNote">Custom IT Software • AI Assistants • Workflow Automation</div>
    </div>
  </footer>

  <script>
    // =========================================================================
    // CONFIGURATION (Connected to your Formspree & Cloudflare Worker)
    // =========================================================================
    const CONFIG = {
      formspreeEndpoint: "https://formspree.io/f/xdegjjyy",
      workerProxyUrl: "https://moltix-ai-proxy.moamedantar8.workers.dev",
      clientNameEn: "Moltix AI",
      clientNameAr: "Moltix AI",
      knowledgeBaseEn: `
        Brand: Moltix AI (Independent subsidiary of MK CREATIVE International Group, distinct from MK CREATIVE and Lynx Studio).
        Core Services:
        1. AI Assistants & Smart Chatbots (24/7 customer support, FAQ handling, and lead capture).
        2. Workflow & Process Automation (connecting forms, Google Sheets, CRMs, and instant alerts).
        3. Custom AI Micro-Tools (document/data extractors, report summarizers, and tailored IT utilities).
        Demo Offer: Customers can test a custom working prototype tailored to their workflow for $5 before committing to a full build.
        How to Order: Fill out the $5 Custom Prototype form on this page or leave contact details right here in chat.
      `,
      knowledgeBaseAr: `
        العلامة التجارية: Moltix AI (شركة تابعة مستقلة لمجموعة MK CREATIVE الدولية، ومستقلة عن MK CREATIVE و Lynx Studio).
        الخدمات الأساسية:
        1. المساعدون الذكيون وروبوتات المحادثة (دعم عملاء 24/7، الرد على الاستفسارات، وجمع بيانات العملاء).
        2. أتمتة سير العمل وربط الأنظمة (ربط النماذج وجداول البيانات والأنظمة والتنبيهات الفورية).
        3. أدوات الذكاء الاصطناعي المخصصة (استخراج البيانات من المستندات، تلخيص التقارير، وأدوات تقنية مصغرة).
        عرض التجربة: يمكن للعميل طلب نموذج تجريبي عملي مصمم لعمله مقابل 5 دولار فقط قبل التعاقد الكامل.
        طريقة الطلب: تعبئة نموذج الطلب في الصفحة أو ترك بيانات التواصل مباشرة في المحادثة.
      `,
      faqEn: [
        {
          keywords: ["price", "pricing", "cost", "$5", "5 dollar", "demo", "prototype"],
          answer: "You can test a custom working AI or automation prototype tailored to your workflow for just $5 before committing to a full build. Want to leave your details here so we can get started?"
        },
        {
          keywords: ["service", "services", "offer", "build", "do you do"],
          answer: "Moltix AI builds three core solutions: 1) AI Assistants & Smart Chatbots, 2) Workflow & Process Automation, and 3) Custom AI Micro-Tools. Which one fits your current workflow?"
        },
        {
          keywords: ["how", "work", "process", "steps"],
          answer: "Share your workflow bottleneck, we build a tailored working prototype for $5 so you can test it live, and once approved we scale it into a full production system."
        }
      ],
      faqAr: [
        {
          keywords: ["سعر", "اسعار", "أسعار", "5", "دولار", "تجريبي", "ديمو", "بكام"],
          answer: "تقدر تجرب نموذج ذكاء اصطناعي أو أتمتة مصمم لشغلك مخصوص مقابل 5 دولار فقط قبل التعاقد الكامل. تحب تسجل بياناتك هنا عشان نبدأ؟"
        },
        {
          keywords: ["خدمات", "خدمة", "بتعملوا", "تقدموا", "مجال"],
          answer: "نقدم في Moltix AI ثلاث خدمات رئيسية: 1) المساعدون الذكيون والشات بوت، 2) أتمتة سير العمل وربط التطبيقات، 3) أدوات ذكاء اصطناعي مخصصة. أي خدمة تهمك؟"
        },
        {
          keywords: ["ازاي", "إزاي", "طريقة", "خطوات"],
          answer: "تشاركنا المشكلة أو المهمة اللي عاوز تؤتمتها، ونبني لك نموذجاً تجريبياً عملياً بـ 5 دولار تجربه بنفسك قبل تطوير النسخة الكاملة."
        }
      ]
    };

    // =========================================================================
    // TRANSLATIONS & PAGE LOGIC
    // =========================================================================
    const translations = {
      en: {
        dir: "ltr",
        langAttr: "en",
        toggleLabel: "العربية",
        groupLabel: "MK CREATIVE International Group",
        navTryBot: "Try Live AI",
        navCta: "Get $5 Demo",
        heroBadge: "Custom IT Software • AI Agents • Workflow Automation",
        heroTitle: 'Test a Custom AI Prototype Built for Your Workflow for <span class="brand-gradient-text">$5</span>',
        heroSubtitle: "Moltix AI builds practical AI assistants, automated operational pipelines, and tailored software tools. Test our live AI assistant below or request a working prototype built around your business for $5.",
        heroPrimaryBtn: "Request Your $5 Demo",
        heroSecondaryBtn: "Test Live AI Assistant",
        servicesTitle: "Core Capabilities",
        servicesSubtitle: "Practical systems engineered to cut manual work and speed up daily operations.",
        s1Title: "AI Assistants & Smart Chatbots",
        s1Desc: "Context-aware assistants trained on your business info to answer inquiries, qualify leads, and route requests smoothly.",
        s1Tag: "Demo Starter: 24/7 Support & Lead Bot",
        s2Title: "Workflow & Process Automation",
        s2Desc: "Automated pipelines connecting forms, sheets, CRMs, and alerts so repetitive tasks run reliably without manual entry.",
        s2Tag: "Demo Starter: Core Ops Automation Flow",
        s3Title: "Custom AI Micro-Tools",
        s3Desc: "Focused internal tools for extracting data from documents, summarizing reports, or streamlining specific IT tasks.",
        s3Tag: "Demo Starter: Smart Data / Doc Extractor",
        chatBadge: "INTERACTIVE SANDBOX",
        chatTitle: "Test Moltix AI Live Assistant",
        chatSubtitle: "Ask about Moltix AI services, the $5 prototype workflow, or leave your contact directly inside the chat.",
        chatStatus: "Moltix AI Concierge • Connected",
        chatReset: "Reset",
        chatPlaceholder: "Ask Moltix AI a question...",
        chatSend: "Send",
        chatWelcome: "Welcome to Moltix AI! 👋 Ask me about our AI assistants, workflow automation, or how our $5 custom prototype works—or click 'Request $5 Demo' below to leave your details.",
        chatChips: ["What services do you build?", "How does the $5 demo work?", "Automate my workflow", "Request $5 Demo"],
        askName: "Let's set up your $5 prototype! First, what is your full name?",
        askContact: "Thanks, {name}! What is your WhatsApp number or email address so we can reach you?",
        askNeed: "Got it. Briefly, what should your $5 demo do?",
        submitting: "Sending your details to Moltix AI...",
        submitted: "✅ Thank you, {name}! Your $5 prototype request has been sent to Moltix AI. We will reach out shortly via email or WhatsApp.",
        submitError: "⚠️ Could not send right now. Please use the form below or try again.",
        thinking: "Thinking...",
        fallback: "We build custom AI assistants, workflow automations, and tailored micro-tools. Would you like to leave your contact details to test a $5 prototype?",
        formBadge: "$5 CUSTOM PROTOTYPE",
        formTitle: "Request Your Demo Prototype",
        formPriceNote: "Demo trial fee",
        formDesc: "Share a quick overview of what you want to test. Your request goes directly to Moltix AI, and we will follow up with confirmation and next steps to start building your demo.",
        labelName: "Full Name *",
        labelEmail: "Email Address *",
        labelPhone: "WhatsApp / Phone Number *",
        labelService: "Demo Type *",
        opt1: "AI Assistant / Smart Chatbot",
        opt2: "Workflow & Process Automation",
        opt3: "Custom AI Micro-Tool",
        labelCompany: "Company / Project Name",
        labelDetails: "What should the $5 demo do? *",
        submitBtn: "Submit $5 Demo Request",
        submittingBtn: "Sending Request...",
        successTitle: "Request Received",
        successBody: "Your $5 demo request has been sent to Moltix AI. We will reach out shortly via your email or WhatsApp with confirmation and next steps to start your prototype.",
        errorTitle: "Submission Issue",
        errorBody: "Something went wrong while sending your request. Please check your connection and try again.",
        footerBrand: "Moltix AI — Subsidiary of MK CREATIVE International Group",
        footerNote: "Custom IT Software • AI Assistants • Workflow Automation"
      },
      ar: {
        dir: "rtl",
        langAttr: "ar",
        toggleLabel: "English",
        groupLabel: "مجموعة MK CREATIVE الدولية",
        navTryBot: "جرّب المساعد الذكي",
        navCta: "اطلب ديمو بـ $5",
        heroBadge: "برمجيات مخصصة • مساعدون ذكيون • أتمتة سير العمل",
        heroTitle: 'جرّب نموذج ذكاء اصطناعي عملي مصمم لشغلك مقابل <span class="brand-gradient-text">$5</span>',
        heroSubtitle: "تطوّر Moltix AI مساعدين ذكيين ومسارات أتمتة وأدوات برمجية مخصصة لتقليل العمل اليدوي. جرّب المساعد الذكي مباشرة بالأسفل أو اطلب نموذجاً تجريبياً لشركتك مقابل $5.",
        heroPrimaryBtn: "اطلب النموذج التجريبي بـ $5",
        heroSecondaryBtn: "جرّب المساعد الذكي الآن",
        servicesTitle: "الخدمات الأساسية",
        servicesSubtitle: "أنظمة عملية مبنية لتقليل الجهد اليدوي ورفع كفاءة التشغيل اليومي.",
        s1Title: "المساعدون الذكيون وروبوتات المحادثة",
        s1Desc: "مساعدون يفهمون بيانات نشاطك للرد على الاستفسارات، وتأهيل العملاء المحتملين، وتوجيه الطلبات بسلاسة.",
        s1Tag: "باقة التجربة: بوت دعم وجمع عملاء 24/7",
        s2Title: "أتمتة سير العمل وربط الأنظمة",
        s2Desc: "مسارات أتمتة تربط النماذج والجداول والأنظمة والتنبيهات لتنفيذ المهام المتكررة تلقائياً بدقة.",
        s2Tag: "باقة التجربة: أتمتة مسار تشغيلي أساسي",
        s3Title: "أدوات ذكاء اصطناعي مخصصة",
        s3Desc: "أدوات داخلية مركزة لاستخراج البيانات من المستندات، وتلخيص التقارير، وتسريع المهام التقنية المحددة.",
        s3Tag: "باقة التجربة: أداة استخراج ومعالجة بيانات",
        chatBadge: "تجربة حية مباشرة",
        chatTitle: "جرّب مساعد Moltix AI الذكي",
        chatSubtitle: "اسأله عن خدمات Moltix AI أو طريقة عمل النموذج التجريبي بـ $5، أو سجل طلبك مباشرة داخل المحادثة.",
        chatStatus: "مساعد Moltix AI • متصل",
        chatReset: "إعادة ضبط",
        chatPlaceholder: "اكتب سؤالك لمساعد Moltix AI...",
        chatSend: "إرسال",
        chatWelcome: "أهلاً بك في Moltix AI! 👋 اسألني عن خدمات المساعدين الذكيين أو أتمتة سير العمل أو عرض النموذج التجريبي بـ 5 دولار—أو اضغط 'اطلب ديمو بـ $5' لتسجيل بياناتك.",
        chatChips: ["ما هي خدماتكم؟", "كيف يعمل عرض الـ $5؟", "أتمتة سير العمل", "اطلب ديمو بـ $5"],
        askName: "ممتاز! لنبدأ بتجهيز طلب الديمو بـ $5. ما هو اسمك الكامل؟",
        askContact: "أهلاً بك يا {name}! ما هو رقم الواتساب أو البريد الإلكتروني للتواصل معك؟",
        askNeed: "تمام. ما هي الفكرة أو المهمة التي تريد تنفيذها في الديمو مقابل $5؟",
        submitting: "جاري إرسال بياناتك إلى Moltix AI...",
        submitted: "✅ شكراً لك يا {name}! تم إرسال طلب النموذج التجريبي ($5) إلى Moltix AI، وسنتواصل معك قريباً عبر البريد أو واتساب.",
        submitError: "⚠️ تعذر الإرسال حالياً. يمكنك استخدام النموذج بالأسفل أو المحاولة مرة أخرى.",
        thinking: "جاري التفكير...",
        fallback: "نطور مساعدين ذكيين ومسارات أتمتة وأدوات مخصصة للشركات. هل ترغب في ترك بياناتك لتجربة نموذج مخصص مقابل 5 دولار؟",
        formBadge: "نموذج تجريبي مخصص بـ $5",
        formTitle: "اطلب النموذج التجريبي",
        formPriceNote: "رسوم تجربة مبدئية",
        formDesc: "اكتب ملخصاً سريعاً للفكرة التي تريد تجربتها. يصل طلبك مباشرة إلى Moltix AI وسنتواصل معك عبر البريد أو واتساب لتأكيد التفاصيل وبدء التنفيذ.",
        labelName: "الاسم الكامل *",
        labelEmail: "البريد الإلكتروني *",
        labelPhone: "رقم واتساب / الهاتف *",
        labelService: "نوع النموذج التجريبي *",
        opt1: "مساعد ذكي / شات بوت",
        opt2: "أتمتة سير العمل والعمليات",
        opt3: "أداة ذكاء اصطناعي مخصصة",
        labelCompany: "اسم الشركة أو المشروع",
        labelDetails: "ماذا تريد أن ينفذ النموذج التجريبي مقابل $5؟ *",
        submitBtn: "إرسال طلب النموذج التجريبي ($5)",
        submittingBtn: "جاري إرسال الطلب...",
        successTitle: "تم استلام طلبك بنجاح",
        successBody: "وصل طلب النموذج التجريبي ($5) إلى Moltix AI. سنتواصل معك قريباً عبر البريد الإلكتروني أو واتساب لتأكيد البدء.",
        errorTitle: "تعذر إرسال الطلب",
        errorBody: "حدثت مشكلة أثناء إرسال النموذج. تأكد من الاتصال بالإنترنت وحاول مرة أخرى.",
        footerBrand: "Moltix AI — شركة تابعة لمجموعة MK CREATIVE الدولية",
        footerNote: "برمجيات مخصصة • مساعدون ذكيون • أتمتة سير العمل"
      }
    };

    let currentLang = "en";
    let leadStep = 0;
    let leadData = { name: "", contact: "", need: "" };
    let transcript = [];

    const htmlRoot = document.getElementById("htmlRoot");
    const langToggle = document.getElementById("langToggle");
    const chatMessages = document.getElementById("chatMessages");
    const quickChips = document.getElementById("quickChips");
    const chatForm = document.getElementById("chatForm");
    const chatInput = document.getElementById("chatInput");
    const resetChatBtn = document.getElementById("resetChatBtn");
    const leadBadge = document.getElementById("leadBadge");

    const moltixForm = document.getElementById("moltixForm");
    const submitBtn = document.getElementById("submitBtn");
    const successBox = document.getElementById("successBox");
    const errorBox = document.getElementById("errorBox");

    function appendMessage(sender, text, isTemp = false) {
      if (!isTemp) {
        transcript.push(`${sender.toUpperCase()}: ${text}`);
      }
      const wrapper = document.createElement("div");
      wrapper.className = sender === "user" ? "flex justify-end" : "flex justify-start";
      if (isTemp) wrapper.id = "tempTyping";

      const bubble = document.createElement("div");
      bubble.className =
        sender === "user"
          ? "max-w-[82%] rounded-2xl rounded-br-sm px-4 py-3 text-sm text-white brand-btn shadow-md leading-relaxed"
          : "max-w-[85%] rounded-2xl rounded-bl-sm px-4 py-3 text-sm text-slate-100 bg-white/[0.06] border border-white/10 leading-relaxed";
      bubble.textContent = text;

      wrapper.appendChild(bubble);
      chatMessages.appendChild(wrapper);
      chatMessages.scrollTop = chatMessages.scrollHeight;
    }

    function removeTempMessage() {
      const temp = document.getElementById("tempTyping");
      if (temp) temp.remove();
    }

    function renderChips() {
      quickChips.innerHTML = "";
      translations[currentLang].chatChips.forEach((chipText) => {
        const btn = document.createElement("button");
        btn.type = "button";
        btn.className =
          "px-3 py-1.5 rounded-full text-xs font-medium bg-white/5 hover:bg-neonblue/15 border border-white/10 hover:border-neonblue/40 text-slate-200 transition cursor-pointer";
        btn.textContent = chipText;
        btn.addEventListener("click", () => handleUserChat(chipText));
        quickChips.appendChild(btn);
      });
    }

    function resetChat() {
      const t = translations[currentLang];
      chatMessages.innerHTML = "";
      transcript = [];
      leadStep = 0;
      leadData = { name: "", contact: "", need: "" };
      leadBadge.classList.add("hidden");
      appendMessage("bot", t.chatWelcome);
      renderChips();
    }

    function applyLanguage(lang) {
      currentLang = lang;
      const t = translations[lang];
      htmlRoot.setAttribute("dir", t.dir);
      htmlRoot.setAttribute("lang", t.langAttr);
      document.body.classList.toggle("font-arabic", lang === "ar");
      langToggle.textContent = t.toggleLabel;
      chatInput.placeholder = t.chatPlaceholder;

      document.querySelectorAll("[data-i18n]").forEach((el) => {
        const key = el.getAttribute("data-i18n");
        if (t[key] !== undefined) {
          el.innerHTML = t[key];
        }
      });

      resetChat();
    }

    async function getAiReply(message) {
      const lower = message.toLowerCase();
      const t = translations[currentLang];

      const leadTriggers = ["request $5", "book", "callback", "contact", "order", "yes", "اطلب ديمو", "تواصل", "حجز", "اطلب", "نعم", "ايوه", "أيوه", "سجل"];
      if (leadTriggers.some((w) => lower.includes(w))) {
        leadStep = 1;
        return t.askName;
      }

      const faqs = currentLang === "en" ? CONFIG.faqEn : CONFIG.faqAr;
      for (const item of faqs) {
        if (item.keywords.some((kw) => lower.includes(kw))) {
          return item.answer;
        }
      }

      try {
        const res = await fetch(CONFIG.workerProxyUrl, {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify({
            message,
            knowledgeBase: currentLang === "en" ? CONFIG.knowledgeBaseEn : CONFIG.knowledgeBaseAr,
            clientName: CONFIG.clientNameEn,
            lang: currentLang
          })
        });

        if (res.ok) {
          const data = await res.json();
          if (data.reply) return data.reply;
        }
      } catch (e) {
        // Fallback if network or worker fails
      }

      return t.fallback;
    }

    async function sendChatLeadToFormspree() {
      const t = translations[currentLang];
      appendMessage("bot", t.submitting);

      const formData = new FormData();
      formData.append("source", "Moltix AI Live Chat Sandbox");
      formData.append("offer_tier", "$5 Custom Demo");
      formData.append("name", leadData.name);
      formData.append("contact", leadData.contact);
      formData.append("details", leadData.need);
      formData.append("chat_transcript", transcript.join("\n"));

      try {
        const response = await fetch(CONFIG.formspreeEndpoint, {
          method: "POST",
          body: formData,
          headers: { Accept: "application/json" }
        });

        if (response.ok) {
          leadStep = 4;
          leadBadge.classList.remove("hidden");
          appendMessage("bot", t.submitted.replace("{name}", leadData.name));
        } else {
          appendMessage("bot", t.submitError);
        }
      } catch (err) {
        appendMessage("bot", t.submitError);
      }
    }

    async function handleUserChat(rawText) {
      const text = rawText.trim();
      if (!text) return;

      appendMessage("user", text);
      chatInput.value = "";
      const t = translations[currentLang];

      if (leadStep === 1) {
        leadData.name = text;
        leadStep = 2;
        setTimeout(() => appendMessage("bot", t.askContact.replace("{name}", leadData.name)), 250);
        return;
      }

      if (leadStep === 2) {
        leadData.contact = text;
        leadStep = 3;
        setTimeout(() => appendMessage("bot", t.askNeed), 250);
        return;
      }

      if (leadStep === 3) {
        leadData.need = text;
        await sendChatLeadToFormspree();
        return;
      }

      appendMessage("bot", t.thinking, true);
      const reply = await getAiReply(text);
      removeTempMessage();
      appendMessage("bot", reply);
    }

    chatForm.addEventListener("submit", (e) => {
      e.preventDefault();
      handleUserChat(chatInput.value);
    });

    resetChatBtn.addEventListener("click", resetChat);

    langToggle.addEventListener("click", () => {
      applyLanguage(currentLang === "en" ? "ar" : "en");
    });

    moltixForm.addEventListener("submit", async (e) => {
      e.preventDefault();
      successBox.classList.add("hidden");
      errorBox.classList.add("hidden");

      const originalText = translations[currentLang].submitBtn;
      submitBtn.disabled = true;
      submitBtn.textContent = translations[currentLang].submittingBtn;

      try {
        const formData = new FormData(moltixForm);
        const response = await fetch(moltixForm.action, {
          method: "POST",
          body: formData,
          headers: { Accept: "application/json" }
        });

        if (response.ok) {
          moltixForm.reset();
          successBox.classList.remove("hidden");
          successBox.scrollIntoView({ behavior: "smooth", block: "nearest" });
        } else {
          errorBox.classList.remove("hidden");
        }
      } catch (err) {
        errorBox.classList.remove("hidden");
      } finally {
        submitBtn.disabled = false;
        submitBtn.textContent = originalText;
      }
    });

    applyLanguage("en");
  </script>
</body>
</html>
