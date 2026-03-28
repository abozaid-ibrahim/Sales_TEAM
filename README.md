<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AI Agents — دليل المبيعات</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;600;700;900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root {
    --gold: #C9A84C;
    --gold-light: #E8C96A;
    --dark: #0A0A0A;
    --dark2: #111111;
    --dark3: #1A1A1A;
    --white: #F5F0E8;
    --muted: #888;
    --accent: #C9A84C;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  @media print {
    body { background: #0A0A0A !important; -webkit-print-color-adjust: exact; print-color-adjust: exact; }
    .page { box-shadow: none !important; }
    .print-btn { display: none !important; }
  }

  body {
    background: #050505;
    font-family: 'Cairo', sans-serif;
    color: var(--white);
    display: flex;
    justify-content: center;
    align-items: flex-start;
    min-height: 100vh;
    padding: 30px 20px;
  }

  .page {
    width: 794px;
    min-height: 1123px;
    background: var(--dark);
    position: relative;
    overflow: hidden;
    box-shadow: 0 0 80px rgba(201,168,76,0.15), 0 0 200px rgba(0,0,0,0.8);
  }

  /* Decorative lines */
  .page::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0; bottom: 0;
    background:
      repeating-linear-gradient(
        90deg,
        transparent,
        transparent 79px,
        rgba(201,168,76,0.04) 79px,
        rgba(201,168,76,0.04) 80px
      );
    pointer-events: none;
  }

  .gold-bar {
    height: 4px;
    background: linear-gradient(90deg, transparent, var(--gold), var(--gold-light), var(--gold), transparent);
  }

  /* HEADER */
  .header {
    padding: 36px 48px 28px;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    border-bottom: 1px solid rgba(201,168,76,0.2);
  }

  .logo-area {
    display: flex;
    flex-direction: column;
    align-items: flex-end;
  }

  .logo-tag {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--gold);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 6px;
  }

  .logo-main {
    font-size: 28px;
    font-weight: 900;
    color: var(--white);
    line-height: 1;
  }

  .logo-main span {
    color: var(--gold);
  }

  .header-badge {
    background: rgba(201,168,76,0.1);
    border: 1px solid rgba(201,168,76,0.3);
    padding: 8px 16px;
    text-align: center;
  }

  .badge-num {
    font-family: 'Space Mono', monospace;
    font-size: 32px;
    font-weight: 700;
    color: var(--gold);
    line-height: 1;
    display: block;
  }

  .badge-label {
    font-size: 10px;
    color: var(--muted);
    display: block;
    margin-top: 2px;
  }

  /* HERO */
  .hero {
    padding: 40px 48px 36px;
    position: relative;
  }

  .hero-eyebrow {
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    color: var(--gold);
    letter-spacing: 4px;
    text-transform: uppercase;
    margin-bottom: 16px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .hero-eyebrow::before {
    content: '';
    display: inline-block;
    width: 30px;
    height: 1px;
    background: var(--gold);
  }

  .hero-headline {
    font-size: 38px;
    font-weight: 900;
    line-height: 1.25;
    margin-bottom: 12px;
  }

  .hero-headline .gold { color: var(--gold); }

  .hero-sub {
    font-size: 13px;
    color: #aaa;
    font-weight: 300;
    direction: ltr;
    text-align: right;
    font-family: 'Space Mono', monospace;
    letter-spacing: 1px;
  }

  /* CALL SCRIPT */
  .section {
    padding: 0 48px;
    margin-bottom: 28px;
  }

  .section-title {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    letter-spacing: 4px;
    color: var(--gold);
    text-transform: uppercase;
    margin-bottom: 14px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .section-title::after {
    content: '';
    flex: 1;
    height: 1px;
    background: rgba(201,168,76,0.2);
  }

  /* SCRIPT STEPS */
  .steps {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 12px;
    direction: rtl;
  }

  .step {
    background: var(--dark3);
    border: 1px solid rgba(201,168,76,0.12);
    padding: 16px 18px;
    position: relative;
    transition: border-color 0.2s;
  }

  .step:hover { border-color: rgba(201,168,76,0.4); }

  .step-num {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--gold);
    letter-spacing: 2px;
    margin-bottom: 8px;
    display: block;
  }

  .step-title {
    font-size: 14px;
    font-weight: 700;
    margin-bottom: 6px;
    color: var(--white);
  }

  .step-body {
    font-size: 12px;
    color: #aaa;
    line-height: 1.7;
    font-weight: 300;
  }

  .step-quote {
    margin-top: 10px;
    padding: 10px 12px;
    background: rgba(201,168,76,0.06);
    border-right: 3px solid var(--gold);
    font-size: 12px;
    color: var(--white);
    font-style: italic;
    line-height: 1.6;
  }

  .step.full-width {
    grid-column: 1 / -1;
  }

  /* POWER STAT */
  .power-row {
    display: flex;
    gap: 12px;
    margin-bottom: 28px;
    padding: 0 48px;
  }

  .power-card {
    flex: 1;
    background: linear-gradient(135deg, rgba(201,168,76,0.12), rgba(201,168,76,0.04));
    border: 1px solid rgba(201,168,76,0.25);
    padding: 18px 20px;
    text-align: center;
  }

  .power-num {
    font-family: 'Space Mono', monospace;
    font-size: 30px;
    font-weight: 700;
    color: var(--gold);
    line-height: 1;
    display: block;
  }

  .power-label-ar {
    font-size: 13px;
    font-weight: 700;
    color: var(--white);
    margin-top: 4px;
    display: block;
  }

  .power-label-en {
    font-size: 9px;
    color: var(--muted);
    font-family: 'Space Mono', monospace;
    letter-spacing: 1px;
    display: block;
    margin-top: 2px;
  }

  /* WHO TO CALL */
  .targets {
    display: flex;
    gap: 10px;
    direction: rtl;
  }

  .target {
    flex: 1;
    border: 1px solid rgba(201,168,76,0.2);
    padding: 14px 16px;
    background: var(--dark3);
    display: flex;
    align-items: flex-start;
    gap: 10px;
  }

  .target.no {
    border-color: rgba(255,80,80,0.2);
    background: rgba(255,50,50,0.04);
  }

  .target-icon {
    font-size: 20px;
    line-height: 1;
    flex-shrink: 0;
  }

  .target-label {
    font-size: 9px;
    font-family: 'Space Mono', monospace;
    letter-spacing: 2px;
    color: var(--gold);
    margin-bottom: 6px;
    display: block;
    text-transform: uppercase;
  }

  .target.no .target-label { color: #f55; }

  .target-names {
    font-size: 12px;
    color: var(--white);
    font-weight: 600;
    line-height: 1.7;
  }

  /* INCENTIVE BOX */
  .incentive {
    margin: 0 48px 28px;
    background: linear-gradient(135deg, rgba(201,168,76,0.15), rgba(201,168,76,0.05));
    border: 1px solid var(--gold);
    padding: 20px 24px;
    display: flex;
    align-items: center;
    gap: 20px;
    direction: rtl;
  }

  .incentive-icon {
    font-size: 36px;
    flex-shrink: 0;
  }

  .incentive-title {
    font-size: 16px;
    font-weight: 900;
    color: var(--gold);
    margin-bottom: 4px;
  }

  .incentive-body {
    font-size: 12px;
    color: #bbb;
    line-height: 1.7;
  }

  .incentive-body strong {
    color: var(--white);
  }

  /* FOOTER */
  .footer {
    margin-top: auto;
    padding: 20px 48px;
    border-top: 1px solid rgba(201,168,76,0.15);
    display: flex;
    justify-content: space-between;
    align-items: center;
    direction: ltr;
  }

  .footer-cta {
    text-align: left;
  }

  .footer-cta-label {
    font-family: 'Space Mono', monospace;
    font-size: 9px;
    color: var(--gold);
    letter-spacing: 3px;
    text-transform: uppercase;
    margin-bottom: 4px;
  }

  .footer-cta-link {
    font-family: 'Space Mono', monospace;
    font-size: 13px;
    color: var(--white);
    text-decoration: none;
    border-bottom: 1px solid var(--gold);
    padding-bottom: 1px;
  }

  .footer-right {
    text-align: right;
    direction: rtl;
  }

  .footer-tag {
    font-size: 11px;
    color: var(--muted);
    margin-bottom: 2px;
  }

  .footer-brand {
    font-size: 16px;
    font-weight: 900;
    color: var(--gold);
  }

  .divider {
    height: 1px;
    background: rgba(201,168,76,0.12);
    margin: 24px 48px;
  }

  .print-btn {
    position: fixed;
    bottom: 30px;
    left: 50%;
    transform: translateX(-50%);
    background: var(--gold);
    color: var(--dark);
    border: none;
    padding: 12px 32px;
    font-family: 'Cairo', sans-serif;
    font-size: 14px;
    font-weight: 700;
    cursor: pointer;
    letter-spacing: 1px;
    box-shadow: 0 4px 30px rgba(201,168,76,0.4);
    transition: all 0.2s;
    z-index: 100;
  }

  .print-btn:hover {
    background: var(--gold-light);
    box-shadow: 0 6px 40px rgba(201,168,76,0.6);
  }

  /* APP LINKS */
  .app-links {
    display: flex;
    gap: 10px;
    align-items: center;
    direction: ltr;
    flex-wrap: wrap;
  }

  .app-btn {
    display: flex;
    align-items: center;
    gap: 7px;
    background: rgba(201,168,76,0.08);
    border: 1px solid rgba(201,168,76,0.3);
    padding: 7px 14px;
    text-decoration: none;
    color: var(--white);
    font-family: 'Space Mono', monospace;
    font-size: 10px;
    letter-spacing: 0.5px;
    transition: all 0.2s;
  }

  .app-btn:hover {
    background: rgba(201,168,76,0.18);
    border-color: var(--gold);
  }

  .app-btn svg {
    flex-shrink: 0;
  }

  .app-btn .btn-label {
    display: flex;
    flex-direction: column;
    line-height: 1.2;
  }

  .app-btn .btn-top {
    font-size: 8px;
    color: var(--muted);
    text-transform: uppercase;
    letter-spacing: 1px;
  }

  .app-btn .btn-name {
    font-size: 11px;
    color: var(--white);
    font-weight: 700;
  }

  .web-btn {
    display: flex;
    align-items: center;
    gap: 7px;
    background: var(--gold);
    padding: 7px 16px;
    text-decoration: none;
    color: var(--dark);
    font-family: 'Space Mono', monospace;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 0.5px;
    transition: all 0.2s;
  }

  .web-btn:hover { background: var(--gold-light); }
</style>
</head>
<body>

<div class="page">

  <div class="gold-bar"></div>

  <!-- HEADER -->
  <div class="header">
    <div class="header-badge">
      <span class="badge-num">+1000</span>
      <span class="badge-label">BROKERS + AI AGENTS FOR YOU</span>
    </div>
    <div class="logo-area">
      <span class="logo-tag">Sales Script Guide · دليل المبيعات</span>
      <div class="logo-main">LENA<span>.AI</span></div>
    </div>
  </div>

  <!-- HERO -->
  <div class="hero">
    <div class="hero-eyebrow">للمستشار العقاري · FOR YOUR SALES TEAM</div>
    <div class="hero-headline">
      خلّي <span class="gold">الذكاء الاصطناعي</span><br>يشتغل بدلك<br>
      <span style="font-size: 22px; color: #aaa; font-weight: 300;">على مدار الساعة، بلا توقف</span>
    </div>
    <div class="hero-sub">Generate leads · Run campaigns · Close faster</div>
  </div>

  <!-- POWER STATS -->
  <div class="power-row">
    <div class="power-card">
      <span class="power-num">+1000</span>
      <span class="power-label-ar">بروكر على الأبليكيشن</span>
      <span class="power-label-en">Human Brokers on your project</span>
    </div>
    <div class="power-card" style="background: linear-gradient(135deg, rgba(201,168,76,0.2), rgba(201,168,76,0.08)); border-color: rgba(201,168,76,0.45);">
      <span class="power-num">+∞</span>
      <span class="power-label-ar">وكيل ذكاء اصطناعي</span>
      <span class="power-label-en">AI Agents running 24/7</span>
    </div>
    <div class="power-card">
      <span class="power-num">24/7</span>
      <span class="power-label-ar">بلا توقف، بلا راتب</span>
      <span class="power-label-en">Zero downtime · Zero salary</span>
    </div>
  </div>

  <!-- CALL SCRIPT -->
  <div class="section">
    <div class="section-title">سكريبت المكالمة · CALL SCRIPT</div>
    <div class="steps">

      <div class="step">
        <span class="step-num">STEP 01 · الترحيب</span>
        <div class="step-title">حضرتك إيه أخبارك؟ 🤝</div>
        <div class="step-body">ابدأ بحفاوة واحترام — مش كمكالمة مبيعات، كأنك بتكلم حد قريب منك وبتحترمه</div>
        <div class="step-quote">
          "مساء النور يا فندم! حضرتك عامل إيه؟ كل سنة وحضرتك بخير وصحة يا [الاسم] 🙂"
        </div>
      </div>

      <div class="step">
        <span class="step-num">STEP 02 · ابدأ تاخد وتدي</span>
        <div class="step-title">سأل واعرض في نفس الوقت 📲</div>
        <div class="step-body">خلّيه يحس إنك جبتله حاجة قبل ما تطلب منه — مش بس بتكلمه عشان تبيع</div>
        <div class="step-quote">
          "ايه أخبار الأسعار عند حضرتك؟ فيه أي تغيير في الوحدات؟
          ابعتلنا التفاصيل — عندنا خانة أخبار في الأبليكيشن بنوصّل فيها أي تحديث
          للبروكرز على طول، في نفس اللحظة."
        </div>
      </div>

      <div class="step full-width" style="background: linear-gradient(135deg, rgba(201,168,76,0.1), rgba(201,168,76,0.04)); border-color: rgba(201,168,76,0.35);">
        <span class="step-num">STEP 03 · وضّح القيمة بوضوح</span>
        <div class="step-title">احنا بنعرض على حضرتك 3 حاجات دلوقتي 🚀</div>
        <div class="step-body">قوله بصراحة وثقة — مش لفّ ودوران</div>
        <div style="display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 8px; margin-top: 10px; direction: rtl;">
          <div style="background: rgba(0,0,0,0.3); padding: 10px; border-right: 2px solid var(--gold);">
            <div style="font-size: 11px; font-weight: 700; color: var(--gold); margin-bottom: 4px;">🤖 حضرتك عارف مشكلة النترا</div>
            <div style="font-size: 11px; color: #bbb; line-height: 1.5;">الذكاء الاصطناعي بيرد على العملاء اللي مش بيتردوا عليهم — 24/7 بدون ما حد يتعب</div>
          </div>
          <div style="background: rgba(0,0,0,0.3); padding: 10px; border-right: 2px solid var(--gold);">
            <div style="font-size: 11px; font-weight: 700; color: var(--gold); margin-bottom: 4px;">👥 +1000 بروكر دفعة واحدة</div>
            <div style="font-size: 11px; color: #bbb; line-height: 1.5;">بنوصّل مشروع حضرتك لألف بروكر في نفس اللحظة — مباشرة على موبايلاتهم</div>
          </div>
          <div style="background: rgba(0,0,0,0.3); padding: 10px; border-right: 2px solid var(--gold);">
            <div style="font-size: 11px; font-weight: 700; color: var(--gold); margin-bottom: 4px;">📢 السوق دايماً عارف أخبارك</div>
            <div style="font-size: 11px; color: #bbb; line-height: 1.5;">تغييرات الأسعار، خطط الدفع، والوحدات المتاحة — البروكرز بيعرفوا أول بأول</div>
          </div>
        </div>
        <div class="step-quote" style="margin-top: 12px;">
          "احنا بنعرض على حضرتك باترنرشب — حضرتك بتستخدم السيستم بتاعنا تشارك أخبار المشروع
          والـ availability مع الألف بروكر عندنا، والذكاء الاصطناعي بيتولى العملاء اللي مش بيرد."
        </div>
      </div>

      <div class="step">
        <span class="step-num">STEP 04 · اطلب الاجتماع</span>
        <div class="step-title">اطلب بثقة واحترام 📅</div>
        <div class="step-body">حدّد من تريده بوضوح — قرار زي ده محتاج صاحب القرار الحقيقي</div>
        <div class="step-quote">
          "محتاج 30 دقيقة من وقت حضرتك — أو مع الـ CEO أو المدير التجاري
          + مدير التسويق. ومش هنحتاج أكتر من كده."
        </div>
      </div>

    </div>
  </div>

  <div class="divider"></div>

  <!-- WHO TO REACH -->
  <div class="section">
    <div class="section-title">من تتكلم معه؟ · WHO TO REACH</div>
    <div class="targets">
      <div class="target">
        <div class="target-icon">✅</div>
        <div>
          <span class="target-label">REACH THEM</span>
          <div class="target-names">
            CEO / المدير التنفيذي<br>
            المدير التجاري<br>
            مدير التسويق
          </div>
        </div>
      </div>
      <div class="target no">
        <div class="target-icon">🚫</div>
        <div>
          <span class="target-label">SKIP</span>
          <div class="target-names">
            مدير المبيعات<br>
            الإداريون<br>
            الموظفون التنفيذيون
          </div>
        </div>
      </div>
      <div class="target" style="flex: 1.5;">
        <div class="target-icon">💡</div>
        <div>
          <span class="target-label">INSIDER TIP · نصيحة ذهبية</span>
          <div class="target-names">
            لو تكلّمت مع مسؤول مبيعات عند العميل<br>
            <span style="color: var(--gold); font-size: 12px;">وعّده بنسبة من الصفقة لو وصّلك للقرار</span>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- INCENTIVE BOX -->
  <div class="incentive">
    <div class="incentive-icon">🤝</div>
    <div>
      <div class="incentive-title">حوّل موظف العميل لحليف · Turn Gatekeepers into Allies</div>
      <div class="incentive-body">
        لو قابلت مسؤول مبيعات أو موظف داخلي — قوله صراحة:<br>
        <strong>"لو وصّلتني للـ CEO أو المدير التجاري وتمت الصفقة، هديك نسبة مباشرة."</strong><br>
        هذا يحوّله من حاجز إلى بوّابة.
      </div>
    </div>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-cta">
      <div class="footer-cta-label">شارك بعد المكالمة · Share after the call</div>
      <div class="app-links" style="margin-top: 8px;">
        <a class="app-btn" href="https://apps.apple.com/eg/app/lena-ai/id6745050088" target="_blank">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="var(--gold)"><path d="M18.71 19.5c-.83 1.24-1.71 2.45-3.05 2.47-1.34.03-1.77-.79-3.29-.79-1.53 0-2 .77-3.27.82-1.31.05-2.3-1.32-3.14-2.53C4.25 17 2.94 12.45 4.7 9.39c.87-1.52 2.43-2.48 4.12-2.51 1.28-.02 2.5.87 3.29.87.78 0 2.26-1.07 3.8-.91.65.03 2.47.26 3.64 1.98-.09.06-2.17 1.28-2.15 3.81.03 3.02 2.65 4.03 2.68 4.04-.03.07-.42 1.44-1.38 2.83M13 3.5c.73-.83 1.94-1.46 2.94-1.5.13 1.17-.34 2.35-1.04 3.19-.69.85-1.83 1.51-2.95 1.42-.15-1.15.41-2.35 1.05-3.11z"/></svg>
          <div class="btn-label">
            <span class="btn-top">Download on</span>
            <span class="btn-name">App Store</span>
          </div>
        </a>
        <a class="app-btn" href="https://play.google.com/store/apps/details?id=net.lenaai.LenaAIDashboardApp" target="_blank">
          <svg width="18" height="18" viewBox="0 0 24 24" fill="var(--gold)"><path d="M3.18 23.76c.3.17.64.22.99.14l12.6-7.28-2.79-2.79-10.8 9.93zm-1.85-20.4C1.12 3.67 1 4.03 1 4.5v15c0 .47.12.83.33 1.14l.06.06 8.4-8.4v-.2L1.39 3.7l-.06.06zM20.49 10.7l-2.52-1.46-3.12 3.12 3.12 3.12 2.55-1.47c.73-.42.73-1.1 0-1.52l-.03.21zM4.17.24L16.77 7.5l-2.79 2.79L3.18.36C3.48.28 3.87.06 4.17.24z"/></svg>
          <div class="btn-label">
            <span class="btn-top">Get it on</span>
            <span class="btn-name">Google Play</span>
          </div>
        </a>
        <a class="web-btn" href="https://lenaai.net/" target="_blank">
          <svg width="14" height="14" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 17.93c-3.95-.49-7-3.85-7-7.93 0-.62.08-1.21.21-1.79L9 15v1c0 1.1.9 2 2 2v1.93zm6.9-2.54c-.26-.81-1-1.39-1.9-1.39h-1v-3c0-.55-.45-1-1-1H8v-2h2c.55 0 1-.45 1-1V7h2c1.1 0 2-.9 2-2v-.41c2.93 1.19 5 4.06 5 7.41 0 2.08-.8 3.97-2.1 5.39z"/></svg>
          lenaai.net
        </a>
      </div>
    </div>
    <div class="footer-right">
      <div class="footer-tag">منصة الوسطاء العقاريين بالذكاء الاصطناعي</div>
      <div class="footer-brand">LENA.AI</div>
    </div>
  </div>

  <div class="gold-bar"></div>

</div>

<button class="print-btn" onclick="window.print()">🖨️ طباعة / Print PDF</button>

</body>
</html>
