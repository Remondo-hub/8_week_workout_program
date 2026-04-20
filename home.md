# 8_week_workout_program
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
<title>برنامج 8 أسابيع | إحماء + تبريد متكامل | جلسات متوازنة</title>
<style>
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  body {
    font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', sans-serif;
    background: #f7f7f2;
    color: #1e293b;
    padding: 1.5rem;
    line-height: 1.5;
  }

  .container {
    max-width: 1300px;
    margin: 0 auto;
  }

  .hero {
    text-align: center;
    margin-bottom: 2rem;
  }
  .hero h1 {
    font-size: 1.9rem;
    font-weight: 800;
    background: linear-gradient(135deg, #1e3c5c, #2a6f8f);
    background-clip: text;
    -webkit-background-clip: text;
    color: transparent;
  }
  .hero p {
    color: #475569;
    margin-top: 6px;
    font-size: 0.9rem;
  }

  .tabs {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
    justify-content: center;
    margin-bottom: 2rem;
    border-bottom: 1px solid #e2e8f0;
    padding-bottom: 10px;
  }
  .tab {
    background: white;
    border: none;
    padding: 8px 20px;
    border-radius: 60px;
    font-size: 0.85rem;
    font-weight: 600;
    cursor: pointer;
    color: #334155;
    transition: 0.2s;
    border: 1px solid #e2e8f0;
  }
  .tab.active {
    background: #1e4a76;
    color: white;
    border-color: #1e4a76;
    box-shadow: 0 4px 10px rgba(30,74,118,0.2);
  }

  .card {
    background: white;
    border-radius: 28px;
    padding: 1.5rem;
    margin-bottom: 1.8rem;
    box-shadow: 0 5px 18px rgba(0,0,0,0.03);
    border: 1px solid #eef2f6;
  }
  .card-title {
    font-size: 1.4rem;
    font-weight: 800;
    color: #0f2b3d;
    border-right: 5px solid #2c7da0;
    padding-right: 16px;
    margin-bottom: 1.2rem;
    display: flex;
    align-items: center;
    gap: 12px;
    flex-wrap: wrap;
  }
  .badge {
    display: inline-block;
    font-size: 0.7rem;
    font-weight: 600;
    padding: 4px 12px;
    border-radius: 40px;
  }
  .badge-blue { background: #e0f2fe; color: #0369a1; }
  .badge-green { background: #dcfce7; color: #15803d; }
  .badge-amber { background: #fef3c7; color: #b45309; }
  .badge-red { background: #ffe4e6; color: #be123c; }
  .badge-purple { background: #f3e8ff; color: #6b21a5; }

  .session-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 24px;
    margin: 20px 0;
  }
  .session-col {
    flex: 1;
    min-width: 280px;
    background: #fefefe;
    border-radius: 28px;
    padding: 1.2rem;
    background: #fafaf8;
    border: 1px solid #eef2f6;
  }
  .session-title {
    font-size: 1.3rem;
    font-weight: 800;
    margin-bottom: 10px;
  }
  .exercise-card-click {
    background: #ffffff;
    border: 1px solid #e9edf2;
    border-radius: 20px;
    padding: 12px 14px;
    margin-bottom: 12px;
    cursor: pointer;
    transition: all 0.2s ease;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-wrap: wrap;
  }
  .exercise-card-click:hover {
    background: #f1f5f9;
    transform: translateY(-2px);
    border-color: #b9d0e8;
  }
  .exercise-name-ar {
    font-weight: 700;
    font-size: 0.95rem;
  }
  .exercise-name-en {
    font-size: 0.7rem;
    font-family: monospace;
    color: #5b6e8c;
    background: #f1f5f9;
    padding: 2px 8px;
    border-radius: 30px;
  }
  .sets-reps {
    font-size: 0.7rem;
    background: #eef2ff;
    padding: 3px 10px;
    border-radius: 30px;
    color: #1e4a76;
    font-weight: 600;
  }
  .video-icon {
    font-size: 0.7rem;
    background: #eef2ff;
    padding: 4px 8px;
    border-radius: 30px;
  }

  /* modal */
  .modal {
    display: none;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0,0,0,0.85);
    z-index: 2000;
    justify-content: center;
    align-items: center;
    backdrop-filter: blur(4px);
  }
  .modal-content {
    background: #fff;
    max-width: 700px;
    width: 92%;
    border-radius: 36px;
    padding: 22px;
    max-height: 85vh;
    overflow-y: auto;
    direction: rtl;
  }
  .modal-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    border-bottom: 2px solid #e2e8f0;
    padding-bottom: 12px;
  }
  .close-modal {
    font-size: 28px;
    cursor: pointer;
    background: none;
    border: none;
  }
  .video-container {
    position: relative;
    padding-bottom: 56.25%;
    height: 0;
    margin: 18px 0;
    background: #000;
    border-radius: 20px;
    overflow: hidden;
  }
  .video-container iframe {
    position: absolute;
    width: 100%;
    height: 100%;
  }
  .muscle-tag {
    background: #e6f2ef;
    color: #1e6f5c;
    border-radius: 40px;
    padding: 4px 12px;
    font-size: 12px;
    display: inline-block;
    margin-left: 6px;
    margin-bottom: 6px;
  }
  .instruction-list {
    padding-right: 1.2rem;
    margin: 12px 0;
  }
  .warmup-cool-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    margin-top: 10px;
  }
  .phase-card {
    background: #fefce8;
    border-radius: 24px;
    padding: 1rem;
    flex: 1;
    min-width: 240px;
    border: 1px solid #fde68a;
  }
  .cool-card {
    background: #e6f7f0;
    border-color: #a7f3d0;
  }
  .tracker-table {
    width: 100%;
    font-size: 0.8rem;
    border-collapse: collapse;
  }
  .tracker-table th, .tracker-table td {
    padding: 10px 8px;
    border: 1px solid #e9edf2;
    text-align: center;
  }
  .tracker-table th:first-child, .tracker-table td:first-child {
    text-align: right;
  }
  input, select {
    border-radius: 40px;
    border: 1px solid #cbd5e1;
    padding: 6px 12px;
    font-family: inherit;
  }
  button {
    background: #eef2ff;
    border: none;
    border-radius: 40px;
    padding: 6px 14px;
    font-weight: 500;
    cursor: pointer;
  }
  button.primary {
    background: #1e4a76;
    color: white;
  }
  .alert {
    background: #fff7e5;
    border-right: 4px solid #f5a623;
    padding: 12px 18px;
    border-radius: 20px;
    margin: 16px 0;
    font-size: 0.85rem;
  }
  .section {
    display: none;
  }
  .section.active {
    display: block;
  }
  @media (max-width: 700px) {
    body { padding: 1rem; }
    .session-col { min-width: 100%; }
  }
</style>
</head>
<body>
<div class="container">
  <div class="hero">
    <h1>🧘 برنامج 8 أسابيع | إحماء + تبريد متكامل</h1>
    <p>جلسة A (دفع + أرجل + بطن) ≡ جلسة B (سحب + أرجل خلفية + قبضة) | اضغط لأي تمرين للفيديو والشرح</p>
  </div>

  <div class="tabs">
    <button class="tab active" data-tab="schedule">📅 الجدول الأسبوعي</button>
    <button class="tab" data-tab="warmupCooldown">🔥🧊 الإحماء والتبريد</button>
    <button class="tab" data-tab="sessionA">💪 جلسة A (دفع + أرجل + بطن)</button>
    <button class="tab" data-tab="sessionB">🏋️ جلسة B (سحب + أرجل خلفية + قبضة)</button>
    <button class="tab" data-tab="progression">📈 التطور التدريجي</button>
    <button class="tab" data-tab="tracker">📊 متابعة التقدم</button>
    <button class="tab" data-tab="tips">⭐ نصائح إضافية</button>
  </div>

  <!-- الجدول الأسبوعي -->
  <div id="schedule" class="section active">
    <div class="card">
      <div class="card-title">🗓️ جدول مرن – جلسة A & B (مرتين أسبوعياً، متوازنتان)</div>
      <div class="session-grid">
        <div class="session-col">
          <div class="session-title">🔥 جلسة A</div>
          <div class="badge badge-blue">دفع + أرجل أمامية + بطن</div>
          <p style="margin-top: 8px; font-size:13px;">التركيز: صدر، أكتاف، ترايسبس، فخذ أمامي، أرداف، بطن.</p>
          <p style="font-size:12px;">⏱️ المدة: 45-55 دقيقة | راحة 60-90 ث</p>
        </div>
        <div class="session-col">
          <div class="session-title">💪 جلسة B</div>
          <div class="badge badge-green">سحب + أرجل خلفية + قبضة</div>
          <p style="margin-top: 8px; font-size:13px;">التركيز: ظهر، بايسبس، أوتار الركبة، أرداف، قبضة.</p>
          <p style="font-size:12px;">⏱️ المدة: 45-55 دقيقة | راحة 60-90 ث</p>
        </div>
      </div>
      <div class="alert">⭐ جدول مثالي: الاثنين (جلسة A) والخميس (جلسة B) أو الثلاثاء والجمعة. استرح 48-72 ساعة بين الجلسات.</div>
    </div>
  </div>

  <!-- ========== الإحماء والتبريد معاً ========== -->
  <div id="warmupCooldown" class="section">
    <div class="card">
      <div class="card-title">🔥 الإحماء الديناميكي (قبل التمرين – 8 إلى 10 دقائق)</div>
      <div class="warmup-cool-grid">
        <div class="phase-card">
          <span class="badge badge-amber">المرحلة 1 (2 دقيقة)</span>
          <p style="margin-top:8px;"><strong>تنشيط المفاصل:</strong><br>• دوران الرقبة (10 كل اتجاه)<br>• دوران الكتفين (15 أمام/خلف)<br>• دوران الحوض (10×)<br>• دوران الكاحل (10 لكل قدم)</p>
        </div>
        <div class="phase-card">
          <span class="badge badge-amber">المرحلة 2 (3 دقائق)</span>
          <p><strong>رفع نبضات القلب:</strong><br>• الجري في المكان – 45 ث<br>• قفز النجمة – 45 ث<br>• رفع الركبة للصدر – 45 ث<br>• Butt Kicks – 45 ث</p>
        </div>
        <div class="phase-card">
          <span class="badge badge-amber">المرحلة 3 (3-4 دقائق)</span>
          <p><strong>إطالة ديناميكية + تحضير:</strong><br>• تأرجح الذراعين – 45 ث<br>• طعنات متناوبة مع دوران – 8× لكل جهة<br>• انزال الجذع للأمام – 10 مرات<br>• قرفصاء خفيفة – 12 تكرار</p>
        </div>
      </div>
    </div>

    <div class="card">
      <div class="card-title">🧊 التبريد والإطالة الثابتة (بعد التمرين – 5 إلى 7 دقائق)</div>
      <div class="warmup-cool-grid">
        <div class="phase-card cool-card">
          <span class="badge badge-green">إطالة العضلات الرئيسية</span>
          <p><strong>• وضعية الطفل (Child’s Pose):</strong> 45 ثانية – لتمدد الظهر والكتفين<br>
          <strong>• إطالة الصدر بالبار/الجدار:</strong> 30 ث لكل جانب<br>
          <strong>• إطالة أوتار الركبة جالساً:</strong> 45 ث لكل رجل<br>
          <strong>• إطالة الفخذ الأمامي واقفاً:</strong> 30 ث لكل رجل<br>
          <strong>• إطالة الأرداف (Pigeon Pose):</strong> 45 ث لكل جانب</p>
        </div>
        <div class="phase-card cool-card">
          <span class="badge badge-green">تبريد عام + تنفس</span>
          <p><strong>• تعليق سلبي على البار (Passive Hang):</strong> 45-60 ثانية – لإطالة العمود الفقري وتفريغ الضغط.<br>
          <strong>• تنفس عميق (شهيق-زفير بطيء):</strong> 1 دقيقة – لخفض نبضات القلب.<br>
          <strong>• مشي بطيء:</strong> دقيقتان لتهدئة الدورة الدموية.</p>
        </div>
      </div>
      <div class="alert">⚠️ التبريد يساعد على تقليل آلام العضلات المتأخرة وتحسين المرونة. لا تتجاهله أبداً.</div>
    </div>
  </div>

  <!-- جلسة A -->
  <div id="sessionA" class="section">
    <div class="card">
      <div class="card-title">🔥 جلسة A – دفع + أرجل أمامية + بطن (اضغط للفيديو والشرح)</div>
      <div id="sessionAList" class="session-grid" style="flex-direction:column; gap:8px;"></div>
      <div class="alert">📌 تمارين متوازنة: 3-4 مجموعات | راحة 60-75 ثانية | تطور أسبوعي.</div>
    </div>
  </div>

  <!-- جلسة B -->
  <div id="sessionB" class="section">
    <div class="card">
      <div class="card-title">💪 جلسة B – سحب + أرجل خلفية + قبضة (اضغط للفيديو والشرح)</div>
      <div id="sessionBList" class="session-grid" style="flex-direction:column; gap:8px;"></div>
      <div class="alert">💪 صعوبة مكافئة لجلسة A – تناسق تام في البرنامج.</div>
    </div>
  </div>

  <!-- التطور التدريجي -->
  <div id="progression" class="section">
    <div class="card">
      <div class="card-title">📈 التطور التدريجي (8 أسابيع)</div>
      <div id="progVisual"></div>
      <div class="alert">✨ زيادة التكرار +1-2 أسبوعياً | تقليل الراحة 5 ثوانٍ كل أسبوعين | إضافة مجموعة رابعة بعد الأسبوع 4.</div>
    </div>
  </div>

  <!-- متابعة التقدم -->
  <div id="tracker" class="section">
    <div class="card">
      <div class="card-title">📊 متابعة تقدمك (جميع التمارين)</div>
      <div style="display:flex; gap:12px; flex-wrap:wrap; margin-bottom:16px;">
        <input type="text" id="trackerName" placeholder="👤 اسمك" style="width:150px">
        <select id="weekSelectTracker"></select>
        <button id="saveWeekTracker" class="primary">💾 حفظ الأسبوع</button>
        <button id="exportTracker">📁 تحميل JSON</button>
        <button id="importTracker">📂 استعادة</button>
        <input type="file" id="importFileTracker" style="display:none" accept=".json">
        <button id="resetTracker" style="background:#fee2e2;">🗑️ إعادة تعيين</button>
      </div>
      <div style="overflow-x:auto; border-radius:24px; border:1px solid #eef2f6;">
        <table class="tracker-table" id="fullTrackerTable">
          <thead id="trackerHeader"></thead>
          <tbody id="trackerBody"></tbody>
        </table>
      </div>
      <div class="alert">📌 سجل عدد التكرارات أو الثواني (للبلانك/شنق ساكن). البيانات تحفظ محلياً وتُصدّر.</div>
    </div>
  </div>

  <!-- نصائح إضافية -->
  <div id="tips" class="section">
    <div class="card"><div class="card-title">🥗 تغذية وتعافي</div><p>بروتين 1.6-2.2 غ/كغ، نوم 7-8 ساعات، وجبة بعد التمرين خلال ساعتين.</p></div>
    <div class="card"><div class="card-title">⚠️ سلامة</div><p>لا تثبت المرفقين بقسوة، تمرن في أوقات معتدلة، استمع لجسمك.</p></div>
    <div class="card"><div class="card-title">🌿 التعامل مع الطقس</div><p>في الحر الشديد: تدرب صباحاً أو بعد المغرب، اشرب ماء مع إلكتروليت. في البرد: إحماء أطول 10 دقائق.</p></div>
  </div>
</div>

<!-- مودال الفيديو والشرح -->
<div id="exerciseModal" class="modal">
  <div class="modal-content">
    <div class="modal-header">
      <h3 id="modalTitle">التمرين</h3>
      <button class="close-modal" onclick="closeModal()">✖</button>
    </div>
    <div id="modalMuscles" style="display:flex; flex-wrap:wrap; gap:6px; margin:10px 0;"></div>
    <div id="modalVideo" class="video-container"></div>
    <div id="modalInstructions"></div>
    <button onclick="closeModal()" style="background:#e2e8f0; border:none; border-radius:30px; padding:6px 15px;">إغلاق</button>
  </div>
</div>

<script>
  // بيانات التمارين مع المجموعات والتكرارات
  const exercisesDB = [
    // جلسة A (دفع + أرجل + بطن) - 9 تمارين
    { ar: "بوش-أب عريض", en: "Wide Push-up", session: "A", sets: "3-4", reps: "10-15", rest: "60ث", muscles: "صدر كبير, أمامي كتف, ترايسبس", videoId: "IODxDxX7oi4", instructions: "وضع الألواح مع يدين أوسع من الكتفين. أنزل صدرك ببطء، ادفع بقوة." },
    { ar: "بوش-أب ضيق (Diamond)", en: "Diamond Push-up", session: "A", sets: "3", reps: "8-12", rest: "60ث", muscles: "ترايسبس, صدر داخلي", videoId: "yXjKqQKc7ZQ", instructions: "شكل الماس باليدين، أنزل ببطء، ركز على الترايسبس." },
    { ar: "بوش-أب بايك (Pike)", en: "Pike Push-up", session: "A", sets: "3", reps: "8-12", rest: "60ث", muscles: "أكتاف أمامية, ترايسبس", videoId: "c8GqH0S8WrE", instructions: "ارفع الأرداف عالياً بشكل V، أنزل رأسك نحو الأرض." },
    { ar: "قرفصاء عميق", en: "Deep Squat", session: "A", sets: "3-4", reps: "15-20", rest: "60ث", muscles: "فخذ أمامي, أوتار الركبة, أرداف", videoId: "aclHkVaku9U", instructions: "قدمان بعرض الكتفين، انزل بوركك تحت الركبة." },
    { ar: "لانج متناوب", en: "Alternating Lunge", session: "A", sets: "3", reps: "10-12/رجل", rest: "60ث", muscles: "أرداف, فخذ أمامي", videoId: "QOVaHwYtH8M", instructions: "خطوة للأمام مع ثني الركبتين 90 درجة." },
    { ar: "جسر الأرداف", en: "Glute Bridge", session: "A", sets: "3", reps: "15-20", rest: "45ث", muscles: "أرداف كبرى, أوتار الركبة", videoId: "8bbN1h8gZGk", instructions: "استلقِ على الظهر، ارفع الحوض للأعلى." },
    { ar: "رفع ركبتين على البار", en: "Hanging Knee Raise", session: "A", sets: "3", reps: "10-15", rest: "45ث", muscles: "بطن مستقيمة", videoId: "B9w7U2k9hL0", instructions: "تعلق بالبار، ارفع ركبتيك نحو الصدر." },
    { ar: "بلانك (لوح)", en: "Plank", session: "A", sets: "3", reps: "30-45 ث", rest: "30ث", muscles: "الجذع العميق", videoId: "pSHjTRCQjIw", instructions: "ارتكن على الساعدين، جسم مستقيم، شد البطن." },
    { ar: "طعنة مائلة", en: "Oblique Crunch", session: "A", sets: "3", reps: "12/جانب", rest: "30ث", muscles: "عضلات البطن المائلة", videoId: "5F-Z1P_rpY0", instructions: "استلقاء، رفع الكتف مع دوران الجذع." },
    // جلسة B (سحب + أرجل خلفية + قبضة) - 9 تمارين متوازنة
    { ar: "عقلة واسعة", en: "Wide Pull-up", session: "B", sets: "3-4", reps: "أقصى عدد (5+)", rest: "90ث", muscles: "ظهر عريض, بايسبس", videoId: "eGo4IYlbE5g", instructions: "قبضة فوقية عريضة، اسحب صدرك نحو البار." },
    { ar: "شنق أسترالي", en: "Australian Row", session: "B", sets: "3", reps: "10-15", rest: "60ث", muscles: "ظهر أوسط, خلفي كتف", videoId: "eL4QZ5V8yZc", instructions: "بار منخفض، جسم مائل، اسحب صدرك للبار." },
    { ar: "عقلة قبضة سفلية (Chin-up)", en: "Chin-up", session: "B", sets: "3", reps: "أقصى عدد", rest: "90ث", muscles: "بايسبس, ظهر سفلي", videoId: "YbQvJqZw3Rs", instructions: "قبضة سفلية، اسحب حتى يلامس ذقنك البار." },
    { ar: "شنق محايد", en: "Neutral Grip Row", session: "B", sets: "3", reps: "10-12", rest: "60ث", muscles: "عضلات المعين", videoId: "7MVJ5N7e4xA", instructions: "قبضة محايدة، اسحب البار نحو منتصف الصدر." },
    { ar: "قرفصاء أحادي الرجل (مساعد)", en: "Pistol Squat", session: "B", sets: "3", reps: "5-8/رجل", rest: "75ث", muscles: "فخذ أمامي, أرداف", videoId: "vMp5hR-rQkI", instructions: "امسك باراً للتوازن، انزل على رجل واحدة." },
    { ar: "تمرين Nordic Curl", en: "Nordic Curl", session: "B", sets: "3", reps: "5-8", rest: "60ث", muscles: "أوتار الركبة", videoId: "O9KJ5vJb5wU", instructions: "ثبت الكعبين تحت بار، أنزل الجذع ببطء." },
    { ar: "رفع رجل خلفية واقفاً", en: "Standing Hip Extension", session: "B", sets: "3", reps: "12-15/رجل", rest: "45ث", muscles: "أرداف, أوتار الركبة", videoId: "tQ2XK5pV3nE", instructions: "امسك البار للتوازن، ارفع رجلاً للخلف." },
    { ar: "شنق ساكن (قبضة)", en: "Dead Hang", session: "B", sets: "3", reps: "30-60 ث", rest: "45ث", muscles: "سواعد, قبضة", videoId: "Hq0s7cF2T3U", instructions: "تعلق بالبار بوضعية معلق سلبي." },
    { ar: "رفع الكعبين واقفاً", en: "Standing Calf Raise", session: "B", sets: "3", reps: "20-25", rest: "45ث", muscles: "عضلة الساق", videoId: "5i6tCJ4oU5A", instructions: "قف على حافة مرتفعة، ارفع كعبيك للأعلى." }
  ];

  function buildSessions() {
    const containerA = document.getElementById("sessionAList");
    const containerB = document.getElementById("sessionBList");
    containerA.innerHTML = "";
    containerB.innerHTML = "";
    exercisesDB.forEach((ex, idx) => {
      const card = document.createElement("div");
      card.className = "exercise-card-click";
      card.onclick = () => openModal(idx);
      card.innerHTML = `
        <div style="display:flex; justify-content:space-between; width:100%; align-items:center; flex-wrap:wrap; gap:6px;">
          <div><span class="exercise-name-ar">${ex.ar}</span> <span class="exercise-name-en">${ex.en}</span></div>
          <div style="display:flex; gap:6px; align-items:center;">
            <span class="sets-reps">${ex.sets}×${ex.reps}</span>
            <span class="sets-reps" style="background:#e6f2ef;">⏱️ راحة ${ex.rest}</span>
            <span class="video-icon">🎥 فيديو</span>
          </div>
        </div>
      `;
      if(ex.session === "A") containerA.appendChild(card);
      else containerB.appendChild(card);
    });
  }

  function openModal(index) {
    const ex = exercisesDB[index];
    const modal = document.getElementById("exerciseModal");
    document.getElementById("modalTitle").innerHTML = `${ex.ar} <span style="font-size:14px; direction:ltr;">${ex.en}</span>`;
    const musclesDiv = document.getElementById("modalMuscles");
    musclesDiv.innerHTML = ex.muscles.split(',').map(m => `<span class="muscle-tag">💪 ${m.trim()}</span>`).join('');
    const videoContainer = document.getElementById("modalVideo");
    videoContainer.innerHTML = `<iframe src="https://www.youtube.com/embed/${ex.videoId}?rel=0" frameborder="0" allowfullscreen></iframe>`;
    const steps = ex.instructions.split('\n');
    document.getElementById("modalInstructions").innerHTML = `<h4>📖 طريقة الأداء:</h4><ul class="instruction-list">${steps.map(s => `<li>${s}</li>`).join('')}</ul><div class="alert" style="margin-top:10px;"><strong>⚙️ الجهد الموصى به:</strong> ${ex.sets} مجموعات × ${ex.reps} | راحة ${ex.rest}</div>`;
    modal.style.display = "flex";
  }

  function closeModal() {
    const modal = document.getElementById("exerciseModal");
    modal.style.display = "none";
    const iframe = document.querySelector("#modalVideo iframe");
    if(iframe) { let src = iframe.src; iframe.src = ""; iframe.src = src; }
  }
  window.closeModal = closeModal;

  // التطور التدريجي
  const phasesArr = [
    { w:"1-2", label:"بناء القاعدة", pct:25, desc:"3 مجموعات — تقنية" },
    { w:"3-4", label:"تثبيت الحجم", pct:45, desc:"3 مجموعات + تقليل راحة" },
    { w:"5-6", label:"رفع الشدة", pct:70, desc:"4 مجموعات + نسخ أصعب" },
    { w:"7", label:"ذروة", pct:90, desc:"أقصى تكرارات" },
    { w:"8", label:"ديلود", pct:40, desc:"شدة 60% تعافٍ" }
  ];
  const progDiv = document.getElementById("progVisual");
  progDiv.innerHTML = phasesArr.map(p => `
    <div style="margin-bottom:16px;">
      <div style="display:flex; justify-content:space-between;"><span>${p.w}</span><span>${p.label}</span></div>
      <div style="background:#e2e8f0; height:12px; border-radius:20px; margin:6px 0;"><div style="width:${p.pct}%; background:#1e4a76; height:12px; border-radius:20px;"></div></div>
      <div style="font-size:12px;">${p.desc}</div>
    </div>
  `).join('');

  // نظام التتبع
  const allTrackerExercises = exercisesDB.map(ex => `${ex.ar} (${ex.en}) — ${ex.sets}×${ex.reps}`);
  const unitsTracker = exercisesDB.map(ex => (ex.ar.includes("بلانك") || ex.ar.includes("شنق ساكن") || ex.reps.includes("ث")) ? "ثانية" : "تكرار");
  let globalData = {};
  function loadData() { const s = localStorage.getItem("fullWarmupCoolTracker"); if(s) globalData = JSON.parse(s); else globalData = {}; }
  function saveData() { localStorage.setItem("fullWarmupCoolTracker", JSON.stringify(globalData)); }
  function initWeekSelect() { const sel = document.getElementById("weekSelectTracker"); sel.innerHTML = ""; for(let i=1;i<=8;i++) sel.innerHTML += `<option value="${i}">الأسبوع ${i}</option>`; sel.value = "1"; }
  function renderFullTracker() {
    const userName = document.getElementById("trackerName").value.trim();
    const week = parseInt(document.getElementById("weekSelectTracker").value);
    if(!userName) { document.getElementById("trackerHeader").innerHTML = ""; document.getElementById("trackerBody").innerHTML = `<tr><td colspan="3">👈 أدخل اسمك<td>`; return; }
    if(!globalData[userName]) globalData[userName] = {};
    const weekKey = `week${week}`;
    if(!globalData[userName][weekKey]) globalData[userName][weekKey] = new Array(allTrackerExercises.length).fill("");
    const weekArr = globalData[userName][weekKey];
    let headerHtml = `<tr><th style="min-width:240px;">التمرين + الجهد الموصى به</th><th>قيمتك</th><th>الوحدة</th></tr>`;
    document.getElementById("trackerHeader").innerHTML = headerHtml;
    let body = "";
    for(let i=0; i<allTrackerExercises.length; i++) {
      body += `<tr><td style="text-align:right;">${allTrackerExercises[i]}</td>
      <td><input type="text" id="trackVal_${i}" value="${weekArr[i] || ""}" placeholder="عدد/ثانية" style="width:100px;"></td>
      <td>${unitsTracker[i]}</td>
      </tr>`;
    }
    body += `<tr><td colspan="3"><button id="inlineSaveTracker" class="primary">💾 حفظ الأسبوع ${week}</button></td></tr>`;
    document.getElementById("trackerBody").innerHTML = body;
    const inlineBtn = document.getElementById("inlineSaveTracker");
    if(inlineBtn) inlineBtn.onclick = () => { if(!userName) return; const newVals = []; for(let i=0;i<allTrackerExercises.length;i++) newVals.push(document.getElementById(`trackVal_${i}`)?.value.trim() || ""); globalData[userName][weekKey] = newVals; saveData(); alert(`✅ حفظ الأسبوع ${week}`); renderFullTracker(); };
  }
  document.getElementById("saveWeekTracker")?.addEventListener("click", ()=>{ const uname = document.getElementById("trackerName").value.trim(); const week = parseInt(document.getElementById("weekSelectTracker").value); if(!uname) return; const weekKey=`week${week}`; const newVals=[]; for(let i=0;i<allTrackerExercises.length;i++) newVals.push(document.getElementById(`trackVal_${i}`)?.value.trim() || ""); if(!globalData[uname]) globalData[uname]={}; globalData[uname][weekKey]=newVals; saveData(); alert(`✅ حفظ الأسبوع ${week}`); renderFullTracker(); });
  document.getElementById("trackerName")?.addEventListener("input", renderFullTracker);
  document.getElementById("weekSelectTracker")?.addEventListener("change", renderFullTracker);
  document.getElementById("exportTracker")?.addEventListener("click", ()=>{ const dataStr=JSON.stringify(globalData,null,2); const blob=new Blob([dataStr],{type:"application/json"}); const a=document.createElement("a"); a.href=URL.createObjectURL(blob); a.download=`workout_full_${Date.now()}.json`; a.click(); URL.revokeObjectURL(a.href); alert("تم التصدير"); });
  document.getElementById("importTracker")?.addEventListener("click", ()=> document.getElementById("importFileTracker").click());
  document.getElementById("importFileTracker")?.addEventListener("change", (e)=>{ const file=e.target.files[0]; if(!file) return; const reader=new FileReader(); reader.onload=(ev)=>{ try{ const imported=JSON.parse(ev.target.result); if(typeof imported==="object"){ globalData=imported; saveData(); renderFullTracker(); alert("تمت الاستعادة"); } }catch(err){ alert("ملف غير صالح"); } }; reader.readAsText(file); });
  document.getElementById("resetTracker")?.addEventListener("click", ()=>{ if(confirm("مسح كل البيانات؟")){ localStorage.removeItem("fullWarmupCoolTracker"); globalData={}; renderFullTracker(); alert("تم المسح"); } });

  // تبديل التبويب
  const tabs = document.querySelectorAll('.tab');
  const sections = document.querySelectorAll('.section');
  tabs.forEach(tab => {
    tab.addEventListener('click', () => {
      const target = tab.getAttribute('data-tab');
      tabs.forEach(t => t.classList.remove('active'));
      tab.classList.add('active');
      sections.forEach(sec => sec.classList.remove('active'));
      document.getElementById(target).classList.add('active');
      if(target === 'tracker') renderFullTracker();
    });
  });

  buildSessions();
  loadData();
  initWeekSelect();
  renderFullTracker();
</script>
</body>
</html>
