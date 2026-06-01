# EZRA 5.0 — פרומפט להדבקה ישירה בכל מודל שפה

**הוראות ליזם:**
1. העתק את כל הטקסט הכחול (מהמילה "אתה" עד סוף הדף)
2. הדבק בכל מודל שפה — Claude / ChatGPT / Gemini
3. הוסף מיד אחריו את מסמך התפיסה שלך
4. שמור את הפלט כקובץ `דוח.html` ← פתח בדפדפן

---

```
אתה מומחה לניהול סיכונים במערכת החינוך הישראלית.

קרא את מסמך התפיסה בסוף ההוראות ומלא את תבנית ה-HTML הבאה.

חוקים מחייבים — חייב לקרוא לפני:
1. החלף אך ורק את ה-{{}} — אל תשנה שום תג HTML, CSS או JavaScript
2. הפלט: קוד HTML מלא בלבד — ללא הסברים, ללא markdown, ללא ```
3. התמקד בהיבטים פדגוגיים ורגולטוריים — ללא נתונים כספיים
4. זהה בדיוק 3 מטרות מהמסמך
5. גזור 4-5 סיכונים מהמטרות — כל סיכון קשור למטרה ספציפית
6. חומרת סיכון = הסתברות(1-10) × נזק(1-10)
7. המלצות קונקרטיות — אחת לכל מטרה
8. ציון חדשנות = ממוצע 4 רכיבים (1-10 כל אחד)
9. ערכים תקינים לסוג חומרה: risk-very-high / risk-high / risk-medium / risk-low
10. ערכים תקינים לתג חומרה: severity-very-high / severity-high / severity-medium / severity-low
11. ערכים תקינים לסטטוס אסדרה: badge-full / badge-partial / badge-dev / badge-improve
12. לכל סיכון — מלא את {{סיכון_N_מקור}} בציטוט קצר של המקור הרגולטורי הרלוונטי (לדוג': "חוזר מנכ"ל לאסדרת חדשנות" / "חוק לימוד חובה, תש"ט–1949" / "אופק חדש")

תבנית HTML — מלא את ה-{{}} בלבד:

<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>דוח ניהול סיכונים — {{שם_הפרויקט}}</title>
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Segoe UI',Tahoma,sans-serif;line-height:1.6;background:linear-gradient(135deg,#667eea,#764ba2);color:#2c3e50}
.wrap{max-width:1100px;margin:0 auto;background:rgba(255,255,255,.98);border-radius:20px;box-shadow:0 25px 50px rgba(0,0,0,.15);overflow:hidden}
.hdr{background:linear-gradient(135deg,#1a3a5c,#2c3e50);color:#fff;padding:50px 40px;text-align:center}
.hdr h1{font-size:2.6em;margin-bottom:10px;text-shadow:2px 2px 4px rgba(0,0,0,.3)}
.hdr .sub{font-size:1.2em;opacity:.9;margin-bottom:6px}
.hdr .meta{display:inline-block;background:rgba(255,255,255,.2);padding:7px 16px;border-radius:20px;font-size:.85em;margin-top:10px}
.nav{position:sticky;top:0;background:linear-gradient(135deg,#34495e,#2c3e50);z-index:900;box-shadow:0 4px 8px rgba(0,0,0,.2)}
.nav ul{display:flex;list-style:none}
.nav li{flex:1}
.nav a{display:block;padding:14px 8px;color:#bdc3c7;text-decoration:none;text-align:center;font-weight:600;font-size:.8em;transition:all .3s;border-left:1px solid #2c3e50}
.nav li:first-child a{border-left:none}
.nav a:hover{background:#2c3e50;color:#fff}
section{scroll-margin-top:55px}
.sec-hdr{background:linear-gradient(135deg,#e74c3c,#c0392b);color:#fff;padding:22px 35px;font-size:1.8em;font-weight:700;text-align:center;position:relative}
.sec-hdr::after{content:'';position:absolute;bottom:-10px;left:50%;transform:translateX(-50%);width:60px;height:4px;background:rgba(255,255,255,.8);border-radius:2px}
.proj-ov{padding:35px;background:linear-gradient(135deg,#f8f9fa,#e9ecef)}
.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:18px;margin-top:20px}
.card{background:#fff;padding:20px;border-radius:14px;box-shadow:0 6px 20px rgba(0,0,0,.07);border-top:4px solid #3498db}
.card h4{color:#2c3e50;margin-bottom:8px;font-size:1em}
.list-sec{background:#fff;margin:22px 35px;padding:24px;border-radius:14px;box-shadow:0 4px 12px rgba(0,0,0,.07)}
.list-sec h3{color:#2c3e50;margin-bottom:14px;font-size:1.3em;text-align:center}
.item{background:#f8f9fa;margin:10px 0;padding:16px;border-radius:9px;border-right:4px solid #27ae60}
.risks-wrap{padding:35px;background:#fff}
.risk-sum{display:grid;grid-template-columns:repeat(4,1fr);gap:14px;margin-bottom:28px}
.sum-card{background:linear-gradient(135deg,#f8f9fa,#e9ecef);padding:18px;border-radius:12px;text-align:center;box-shadow:0 6px 20px rgba(0,0,0,.08)}
.sum-num{font-size:2.5em;font-weight:700;margin-bottom:6px}
.c-vh{color:#e74c3c}.c-h{color:#f39c12}.c-m{color:#e8b800}.c-l{color:#27ae60}
.risks-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(360px,1fr));gap:22px;margin-top:24px}
.risk-card{background:#fff;border-radius:14px;box-shadow:0 8px 25px rgba(0,0,0,.09);padding:24px;border-top:5px solid}
.risk-very-high{border-top-color:#e74c3c}.risk-high{border-top-color:#f39c12}.risk-medium{border-top-color:#e8b800}.risk-low{border-top-color:#27ae60}
.risk-head{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:14px;gap:10px}
.risk-title{font-size:1.1em;font-weight:700;color:#2c3e50;flex:1}
.sev{padding:5px 12px;border-radius:20px;font-size:.75em;font-weight:700;color:#fff;white-space:nowrap}
.severity-very-high{background:#e74c3c}.severity-high{background:#f39c12}.severity-medium{background:#e8b800;color:#2c3e50}.severity-low{background:#27ae60}
.metrics{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;margin:14px 0;text-align:center}
.metric{background:#f8f9fa;padding:12px;border-radius:9px}
.metric-val{font-size:1.6em;font-weight:700;color:#2c3e50}
.metric-lbl{font-size:.8em;color:#7f8c8d;margin-top:3px}
.desc{color:#34495e;line-height:1.7;background:#f8f9fa;padding:14px;border-radius:9px;margin-top:12px;border-right:4px solid #bdc3c7;font-size:.95em}
.impact-title{font-weight:700;color:#e74c3c;margin:14px 0 6px}
.opp-title{font-weight:700;color:#27ae60;margin:14px 0 6px}
.ulist{list-style:none;padding-right:10px}
.ulist li{padding:6px 0;border-bottom:1px solid #ecf0f1;font-size:.92em}
.ulist.imp li::before{content:'⚠️';margin-left:6px}
.ulist.opp li::before{content:'✅';margin-left:6px}
.r-src{font-size:.82em;color:#555;background:#f0f4ff;padding:7px 12px;border-radius:7px;margin-top:10px;border-right:3px solid #3498db}
.r-src strong{color:#2980b9}
.sources-wrap{background:linear-gradient(135deg,#1a252f,#2c3e50);padding:35px;color:#fff}
.src-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:16px;margin-top:20px}
.src-cat{background:rgba(255,255,255,.08);border-radius:11px;padding:16px;border:1px solid rgba(255,255,255,.14)}
.src-cat-title{font-size:.95em;font-weight:700;color:#1abc9c;margin-bottom:10px;padding-bottom:7px;border-bottom:2px solid rgba(26,188,156,.3)}
.src-item{margin:5px 0;padding:6px 10px;background:rgba(255,255,255,.06);border-radius:6px;border-right:3px solid #1abc9c}
.src-item a{color:#abebc6;text-decoration:none;font-size:.86em;line-height:1.4}
.src-item a:hover{color:#1abc9c;text-decoration:underline}
.src-note{margin-top:18px;background:rgba(26,188,156,.1);border:1px solid rgba(26,188,156,.25);border-radius:9px;padding:13px;font-size:.83em;color:rgba(255,255,255,.8)}
.src-note strong{color:#1abc9c}
.strats{padding:40px 35px;background:linear-gradient(135deg,#ecf0f1,#dfe6e9)}
.strat{background:#fff;margin:22px 0;border-radius:18px;box-shadow:0 12px 30px rgba(0,0,0,.09);overflow:hidden}
.strat-hdr{background:linear-gradient(135deg,#27ae60,#2ecc71);color:#fff;padding:18px 24px;font-weight:700;font-size:1.15em}
.strat-body{padding:22px 24px}
.strat-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:14px;margin-top:14px}
.strat-item{background:#f8f9fa;padding:14px;border-radius:10px;border-right:4px solid #27ae60}
.strat-item h5{color:#27ae60;margin-bottom:5px;font-size:.95em}
.strat-item p{font-size:.88em;color:#34495e}
.badge-t{display:inline-block;background:#3498db;color:#fff;padding:3px 10px;border-radius:12px;font-size:.75em;margin-top:6px}
.badge-k{display:inline-block;background:#8e44ad;color:#fff;padding:3px 10px;border-radius:12px;font-size:.75em;margin-top:6px}
.innov-reg{background:linear-gradient(135deg,#f8f9fa,#e9ecef);padding:40px 35px}
.white-box{background:#fff;padding:24px;border-radius:14px;margin:20px 0;box-shadow:0 6px 20px rgba(0,0,0,.07)}
.comm-box{background:#f0f8ff;padding:18px;border-radius:12px;margin-top:18px;border-left:5px solid #3498db}
.innov-level{background:linear-gradient(135deg,#8e44ad,#9b59b6);color:#fff;padding:40px 35px;text-align:center}
.innov-score{font-size:4.5em;font-weight:700;margin:20px 0;text-shadow:2px 2px 5px rgba(0,0,0,.3)}
.innov-lbl{font-size:1.2em;opacity:.9;margin-top:-12px;margin-bottom:12px}
.comp-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(240px,1fr));gap:18px;margin-top:28px}
.comp{background:rgba(255,255,255,.14);padding:18px;border-radius:13px;border:1px solid rgba(255,255,255,.2)}
.comp-score{font-size:2.2em;font-weight:700;color:#f39c12;margin-bottom:6px}
.comp-title{font-size:1em;font-weight:700;margin-bottom:6px}
.reg-wrap{padding:35px;background:#ecf0f1}
.reg-table{width:100%;background:#fff;border-radius:14px;overflow:hidden;box-shadow:0 6px 20px rgba(0,0,0,.07)}
.reg-table th,.reg-table td{padding:14px 16px;text-align:right;border-bottom:1px solid #ecf0f1;vertical-align:top}
.reg-table th{background:#34495e;color:#fff;font-weight:700}
.badge-full{background:#27ae60;color:#fff;padding:3px 10px;border-radius:10px;font-size:.82em;font-weight:700;display:inline-block}
.badge-partial{background:#f39c12;color:#fff;padding:3px 10px;border-radius:10px;font-size:.82em;font-weight:700;display:inline-block}
.badge-dev{background:#3498db;color:#fff;padding:3px 10px;border-radius:10px;font-size:.82em;font-weight:700;display:inline-block}
.badge-improve{background:#e74c3c;color:#fff;padding:3px 10px;border-radius:10px;font-size:.82em;font-weight:700;display:inline-block}
.exec{padding:40px 35px;background:linear-gradient(135deg,#2c3e50,#34495e);color:#fff}
.exec-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:18px;margin:22px 0}
.exec-card{background:rgba(255,255,255,.1);padding:18px;border-radius:13px;border:1px solid rgba(255,255,255,.14)}
.exec-card h4{color:#f39c12;font-size:1em;margin-bottom:8px}
.recs{background:rgba(255,255,255,.07);padding:20px;border-radius:13px;margin-top:16px}
.recs h3{color:#f39c12;margin-bottom:14px}
.rec{background:rgba(255,255,255,.07);margin:10px 0;padding:14px;border-radius:9px;border-right:4px solid #f39c12;font-size:.92em}
.ftr{background:#1a252f;color:#7f8c8d;text-align:center;padding:25px;font-size:.88em}
.ftr strong{color:#3498db}
.btn-edit,.btn-pdf,.btn-save{position:fixed;color:#fff;border:none;padding:12px 20px;border-radius:25px;cursor:pointer;font-size:.9em;font-weight:700;z-index:1000;left:20px}
.btn-edit{top:20px;background:#3498db;box-shadow:0 4px 15px rgba(52,152,219,.4)}
.btn-edit.on{background:#27ae60}
.btn-pdf{top:68px;background:#e74c3c;box-shadow:0 4px 15px rgba(231,76,60,.4)}
.btn-save{top:116px;background:#8e44ad;box-shadow:0 4px 15px rgba(142,68,173,.4)}
.editable{padding:3px;border-radius:3px;transition:all .3s}
.editable[contenteditable=true]{background:rgba(52,152,219,.1);border:2px dashed #3498db;outline:none;cursor:text;padding:5px}
html{scroll-behavior:smooth}
@media(max-width:700px){.nav a{font-size:.7em;padding:10px 4px}.risks-grid,.grid,.comp-grid{grid-template-columns:1fr}.metrics{grid-template-columns:1fr}.risk-sum{grid-template-columns:1fr 1fr}}
@media print{*{-webkit-print-color-adjust:exact!important;print-color-adjust:exact!important}.btn-edit,.btn-pdf,.btn-save,.nav{display:none!important}body{background:#fff!important}.wrap{box-shadow:none!important;border-radius:0!important;max-width:100%!important}.risk-card,.strat,.card,.white-box{page-break-inside:avoid!important}@page{margin:10mm;size:A4}}
</style>
</head>
<body>
<div class="wrap">
<button class="btn-edit" id="eBtn" onclick="toggleEdit()">🎨 עריכה</button>
<button class="btn-pdf" onclick="window.print()">📄 PDF</button>
<button class="btn-save" onclick="saveHTML()">💾 שמור</button>

<header class="hdr">
  <h1 class="editable">⚠️ דוח ניהול סיכונים</h1>
  <div class="sub editable">{{שם_הפרויקט}} — {{תיאור_קצר}}</div>
  <div class="meta editable">אחראי: {{שם_אחראי}} • {{תאריך}}</div>
</header>

<nav class="nav"><ul>
  <li><a href="#s1">📋 פרויקט</a></li>
  <li><a href="#s2">⚠️ סיכונים</a></li>
  <li><a href="#s3">📈 התמודדות</a></li>
  <li><a href="#s4">🚀 אסדרה</a></li>
  <li><a href="#s5">📊 חדשנות</a></li>
  <li><a href="#s6">✅ רגולציה</a></li>
  <li><a href="#s7">📝 סיכום</a></li>
<li><a href="#s8">📚 מקורות</a></li>
</ul></nav>

<!-- סעיף 1: פרויקט -->
<section id="s1">
<div class="sec-hdr editable">📋 הגדרת הפרויקט</div>
<div class="proj-ov">
  <div class="grid">
    <div class="card"><h4>👤 <span class="editable">אחראי פרויקט</span></h4><p class="editable">{{אחראי_פרויקט}}</p></div>
    <div class="card"><h4>🏢 <span class="editable">ארגון</span></h4><p class="editable">{{ארגון}}</p></div>
    <div class="card"><h4>🌍 <span class="editable">היקף</span></h4><p class="editable">{{היקף_הפרויקט}}</p></div>
    <div class="card"><h4>📅 <span class="editable">לוח זמנים</span></h4><p class="editable">{{לוח_זמנים}}</p></div>
    <div class="card"><h4>🚀 <span class="editable">סוג חדשנות</span></h4><p class="editable">{{סוג_החדשנות}}</p></div>
    <div class="card"><h4>📋 <span class="editable">סטטוס רגולטורי</span></h4><p class="editable">{{סטטוס_רגולטורי}}</p></div>
  </div>
</div>
<div class="list-sec">
  <h3 class="editable">🎯 מטרות הפרויקט</h3>
  <div class="item editable"><strong>1. {{מטרה_1_כותרת}}</strong><br>{{מטרה_1_תיאור}}</div>
  <div class="item editable"><strong>2. {{מטרה_2_כותרת}}</strong><br>{{מטרה_2_תיאור}}</div>
  <div class="item editable"><strong>3. {{מטרה_3_כותרת}}</strong><br>{{מטרה_3_תיאור}}</div>
</div>
<div class="list-sec">
  <h3 class="editable">📋 תוצרים מצופים</h3>
  <div class="item editable"><strong>{{תוצר_1_כותרת}}</strong> — {{תוצר_1_תיאור}}</div>
  <div class="item editable"><strong>{{תוצר_2_כותרת}}</strong> — {{תוצר_2_תיאור}}</div>
  <div class="item editable"><strong>{{תוצר_3_כותרת}}</strong> — {{תוצר_3_תיאור}}</div>
</div>
</section>

<!-- סעיף 2: סיכונים -->
<section id="s2">
<div class="sec-hdr editable">⚠️ ניהול סיכונים</div>
<div class="risks-wrap">
  <div class="risk-sum">
    <div class="sum-card"><div class="sum-num c-vh editable">{{ספירה_גבוהה_מאוד}}</div><div>גבוהה מאוד</div></div>
    <div class="sum-card"><div class="sum-num c-h editable">{{ספירה_גבוהה}}</div><div>גבוהה</div></div>
    <div class="sum-card"><div class="sum-num c-m editable">{{ספירה_בינונית}}</div><div>בינונית</div></div>
    <div class="sum-card"><div class="sum-num c-l editable">{{ספירה_נמוכה}}</div><div>נמוכה</div></div>
  </div>
  <div class="risks-grid">

    <!-- סיכון 1 — שכפל/מחק לפי הצורך -->
    <div class="risk-card {{סיכון_1_רמה}}">
      <div class="risk-head">
        <div class="risk-title editable">{{סיכון_1_כותרת}}</div>
        <div class="sev {{סיכון_1_תג_חומרה}} editable">{{סיכון_1_תווית_חומרה}}</div>
      </div>
      <div style="font-size:.9em;color:#3498db;margin-bottom:10px" class="editable">{{סיכון_1_קישור_למטרה}}</div>
      <div class="metrics">
        <div class="metric"><div class="metric-val editable">{{סיכון_1_הסתברות}}</div><div class="metric-lbl">הסתברות</div></div>
        <div class="metric"><div class="metric-val editable">{{סיכון_1_נזק}}</div><div class="metric-lbl">עוצמת נזק</div></div>
        <div class="metric"><div class="metric-val editable">{{סיכון_1_ציון}}</div><div class="metric-lbl">דרגת חומרה</div></div>
      </div>
      <div class="desc editable">{{סיכון_1_תיאור}}</div>
      <div class="r-src editable">📌 <strong>מקור:</strong> {{סיכון_1_מקור}}</div>
      <div class="impact-title editable">השלכות:</div>
      <ul class="ulist imp">
        <li class="editable">{{סיכון_1_השלכה_1}}</li>
        <li class="editable">{{סיכון_1_השלכה_2}}</li>
        <li class="editable">{{סיכון_1_השלכה_3}}</li>
      </ul>
      <div class="opp-title editable">הזדמנויות:</div>
      <ul class="ulist opp">
        <li class="editable">{{סיכון_1_הזדמנות_1}}</li>
        <li class="editable">{{סיכון_1_הזדמנות_2}}</li>
      </ul>
    </div>

    <!-- סיכון 2 -->
    <div class="risk-card {{סיכון_2_רמה}}">
      <div class="risk-head">
        <div class="risk-title editable">{{סיכון_2_כותרת}}</div>
        <div class="sev {{סיכון_2_תג_חומרה}} editable">{{סיכון_2_תווית_חומרה}}</div>
      </div>
      <div style="font-size:.9em;color:#3498db;margin-bottom:10px" class="editable">{{סיכון_2_קישור_למטרה}}</div>
      <div class="metrics">
        <div class="metric"><div class="metric-val editable">{{סיכון_2_הסתברות}}</div><div class="metric-lbl">הסתברות</div></div>
        <div class="metric"><div class="metric-val editable">{{סיכון_2_נזק}}</div><div class="metric-lbl">עוצמת נזק</div></div>
        <div class="metric"><div class="metric-val editable">{{סיכון_2_ציון}}</div><div class="metric-lbl">דרגת חומרה</div></div>
      </div>
      <div class="desc editable">{{סיכון_2_תיאור}}</div>
      <div class="r-src editable">📌 <strong>מקור:</strong> {{סיכון_2_מקור}}</div>
      <div class="impact-title editable">השלכות:</div>
      <ul class="ulist imp">
        <li class="editable">{{סיכון_2_השלכה_1}}</li>
        <li class="editable">{{סיכון_2_השלכה_2}}</li>
      </ul>
      <div class="opp-title editable">הזדמנויות:</div>
      <ul class="ulist opp">
        <li class="editable">{{סיכון_2_הזדמנות_1}}</li>
      </ul>
    </div>

    <!-- סיכון 3 -->
    <div class="risk-card {{סיכון_3_רמה}}">
      <div class="risk-head">
        <div class="risk-title editable">{{סיכון_3_כותרת}}</div>
        <div class="sev {{סיכון_3_תג_חומרה}} editable">{{סיכון_3_תווית_חומרה}}</div>
      </div>
      <div style="font-size:.9em;color:#3498db;margin-bottom:10px" class="editable">{{סיכון_3_קישור_למטרה}}</div>
      <div class="metrics">
        <div class="metric"><div class="metric-val editable">{{סיכון_3_הסתברות}}</div><div class="metric-lbl">הסתברות</div></div>
        <div class="metric"><div class="metric-val editable">{{סיכון_3_נזק}}</div><div class="metric-lbl">עוצמת נזק</div></div>
        <div class="metric"><div class="metric-val editable">{{סיכון_3_ציון}}</div><div class="metric-lbl">דרגת חומרה</div></div>
      </div>
      <div class="desc editable">{{סיכון_3_תיאור}}</div>
      <div class="r-src editable">📌 <strong>מקור:</strong> {{סיכון_3_מקור}}</div>
      <div class="impact-title editable">השלכות:</div>
      <ul class="ulist imp">
        <li class="editable">{{סיכון_3_השלכה_1}}</li>
        <li class="editable">{{סיכון_3_השלכה_2}}</li>
      </ul>
      <div class="opp-title editable">הזדמנויות:</div>
      <ul class="ulist opp">
        <li class="editable">{{סיכון_3_הזדמנות_1}}</li>
      </ul>
    </div>

    <!-- סיכון 4 -->
    <div class="risk-card {{סיכון_4_רמה}}">
      <div class="risk-head">
        <div class="risk-title editable">{{סיכון_4_כותרת}}</div>
        <div class="sev {{סיכון_4_תג_חומרה}} editable">{{סיכון_4_תווית_חומרה}}</div>
      </div>
      <div style="font-size:.9em;color:#3498db;margin-bottom:10px" class="editable">{{סיכון_4_קישור_למטרה}}</div>
      <div class="metrics">
        <div class="metric"><div class="metric-val editable">{{סיכון_4_הסתברות}}</div><div class="metric-lbl">הסתברות</div></div>
        <div class="metric"><div class="metric-val editable">{{סיכון_4_נזק}}</div><div class="metric-lbl">עוצמת נזק</div></div>
        <div class="metric"><div class="metric-val editable">{{סיכון_4_ציון}}</div><div class="metric-lbl">דרגת חומרה</div></div>
      </div>
      <div class="desc editable">{{סיכון_4_תיאור}}</div>
      <div class="r-src editable">📌 <strong>מקור:</strong> {{סיכון_4_מקור}}</div>
      <div class="impact-title editable">השלכות:</div>
      <ul class="ulist imp">
        <li class="editable">{{סיכון_4_השלכה_1}}</li>
        <li class="editable">{{סיכון_4_השלכה_2}}</li>
      </ul>
      <div class="opp-title editable">הזדמנויות:</div>
      <ul class="ulist opp">
        <li class="editable">{{סיכון_4_הזדמנות_1}}</li>
      </ul>
    </div>

  </div>
</div>
</section>

<!-- סעיף 3: אסטרטגיות -->
<section id="s3">
<div class="sec-hdr editable">📈 תוכנית התמודדות</div>
<div class="strats">

  <div class="strat">
    <div class="strat-hdr editable">{{אסטרטגיה_1_כותרת}}</div>
    <div class="strat-body">
      <p class="editable" style="color:#34495e;margin-bottom:14px">{{אסטרטגיה_1_תיאור}}</p>
      <div class="strat-grid">
        <div class="strat-item"><h5 class="editable">{{אסטרטגיה_1_שלב_1_כותרת}}</h5><p class="editable">{{אסטרטגיה_1_שלב_1_תיאור}}</p><span class="badge-t">{{אסטרטגיה_1_שלב_1_תאריך}}</span></div>
        <div class="strat-item"><h5 class="editable">{{אסטרטגיה_1_שלב_2_כותרת}}</h5><p class="editable">{{אסטרטגיה_1_שלב_2_תיאור}}</p><span class="badge-t">{{אסטרטגיה_1_שלב_2_תאריך}}</span></div>
        <div class="strat-item"><h5 class="editable">מדד הצלחה</h5><p class="editable">{{אסטרטגיה_1_kpi}}</p><span class="badge-k">KPI</span></div>
      </div>
    </div>
  </div>

  <div class="strat">
    <div class="strat-hdr editable">{{אסטרטגיה_2_כותרת}}</div>
    <div class="strat-body">
      <p class="editable" style="color:#34495e;margin-bottom:14px">{{אסטרטגיה_2_תיאור}}</p>
      <div class="strat-grid">
        <div class="strat-item"><h5 class="editable">{{אסטרטגיה_2_שלב_1_כותרת}}</h5><p class="editable">{{אסטרטגיה_2_שלב_1_תיאור}}</p><span class="badge-t">{{אסטרטגיה_2_שלב_1_תאריך}}</span></div>
        <div class="strat-item"><h5 class="editable">{{אסטרטגיה_2_שלב_2_כותרת}}</h5><p class="editable">{{אסטרטגיה_2_שלב_2_תיאור}}</p><span class="badge-t">{{אסטרטגיה_2_שלב_2_תאריך}}</span></div>
        <div class="strat-item"><h5 class="editable">מדד הצלחה</h5><p class="editable">{{אסטרטגיה_2_kpi}}</p><span class="badge-k">KPI</span></div>
      </div>
    </div>
  </div>

</div>
</section>

<!-- סעיף 4: אסדרת חדשנות -->
<section id="s4">
<div class="sec-hdr editable">🚀 אסדרת חדשנות</div>
<div class="innov-reg">
  <div class="white-box">
    <h3 style="color:#8e44ad;margin-bottom:12px" class="editable">{{חדשנות_כותרת}}</h3>
    <p class="editable" style="color:#34495e;line-height:1.8">{{חדשנות_תיאור}}</p>
    <p class="editable" style="color:#34495e;line-height:1.8;margin-top:10px">{{rri_עקרונות}}</p>
  </div>
  <div class="comm-box">
    <h4>🏛️ המלצת ועדת המשנה לאסדרת חדשנות</h4>
    <p class="editable" style="color:#34495e;line-height:1.8">{{המלצת_ועדה}}</p>
  </div>
</div>
</section>

<!-- סעיף 5: רמת חדשנות -->
<section id="s5">
<div class="sec-hdr editable">📊 רמת החדשנות</div>
<div class="innov-level">
  <h2 class="editable" style="font-size:1.4em;margin-bottom:4px">ציון חדשנות כולל</h2>
  <div class="innov-score editable">{{ציון_חדשנות}}</div>
  <div class="innov-lbl editable">/ 10 — {{תווית_חדשנות}}</div>
  <p class="editable" style="opacity:.85;max-width:600px;margin:0 auto 16px">{{תיאור_ציון_חדשנות}}</p>
  <div class="comp-grid">
    <div class="comp"><div class="comp-score editable">{{רכיב_1_ציון}}</div><div class="comp-title editable">השפעה פדגוגית</div><p class="editable" style="opacity:.85;font-size:.9em">{{רכיב_1_תיאור}}</p></div>
    <div class="comp"><div class="comp-score editable">{{רכיב_2_ציון}}</div><div class="comp-title editable">מורכבות טכנולוגית</div><p class="editable" style="opacity:.85;font-size:.9em">{{רכיב_2_תיאור}}</p></div>
    <div class="comp"><div class="comp-score editable">{{רכיב_3_ציון}}</div><div class="comp-title editable">שינוי ארגוני</div><p class="editable" style="opacity:.85;font-size:.9em">{{רכיב_3_תיאור}}</p></div>
    <div class="comp"><div class="comp-score editable">{{רכיב_4_ציון}}</div><div class="comp-title editable">סיכון טכנולוגי</div><p class="editable" style="opacity:.85;font-size:.9em">{{רכיב_4_תיאור}}</p></div>
  </div>
</div>
</section>

<!-- סעיף 6: רגולציה -->
<section id="s6">
<div class="sec-hdr editable">✅ התאמה לדרישות אסדרה</div>
<div class="reg-wrap">
  <table class="reg-table">
    <thead><tr><th>דרישת אסדרה</th><th>סטטוס</th><th>פעולה נדרשת</th></tr></thead>
    <tbody>
      <tr><td class="editable"><strong>{{רגולציה_1_שם}}</strong><br><small>{{רגולציה_1_פירוט}}</small></td><td><span class="{{רגולציה_1_סטטוס_תג}}">{{רגולציה_1_סטטוס_טקסט}}</span></td><td class="editable">{{רגולציה_1_פעולה}}</td></tr>
      <tr><td class="editable"><strong>{{רגולציה_2_שם}}</strong><br><small>{{רגולציה_2_פירוט}}</small></td><td><span class="{{רגולציה_2_סטטוס_תג}}">{{רגולציה_2_סטטוס_טקסט}}</span></td><td class="editable">{{רגולציה_2_פעולה}}</td></tr>
      <tr><td class="editable"><strong>{{רגולציה_3_שם}}</strong><br><small>{{רגולציה_3_פירוט}}</small></td><td><span class="{{רגולציה_3_סטטוס_תג}}">{{רגולציה_3_סטטוס_טקסט}}</span></td><td class="editable">{{רגולציה_3_פעולה}}</td></tr>
      <tr><td class="editable"><strong>{{רגולציה_4_שם}}</strong><br><small>{{רגולציה_4_פירוט}}</small></td><td><span class="{{רגולציה_4_סטטוס_תג}}">{{רגולציה_4_סטטוס_טקסט}}</span></td><td class="editable">{{רגולציה_4_פעולה}}</td></tr>
    </tbody>
  </table>
</div>
</section>

<!-- סעיף 7: סיכום -->
<section id="s7">
<div class="sec-hdr editable">📝 סיכום מנהלים והמלצות</div>
<div class="exec">
  <h2 style="text-align:center;color:#f39c12;margin-bottom:18px" class="editable">סיכום ביצועי</h2>
  <div class="exec-grid">
    <div class="exec-card"><h4>📊 רמת חדשנות</h4><p class="editable">{{סיכום_חדשנות}}</p></div>
    <div class="exec-card"><h4>🔐 הסיכון הגדול</h4><p class="editable">{{סיכום_סיכון_עיקרי}}</p></div>
    <div class="exec-card"><h4>⚠️ רמת סיכון כוללת</h4><p class="editable">{{סיכום_רמת_סיכון}}</p></div>
  </div>
  <div class="recs">
    <h3>💡 המלצות מרכזיות</h3>
    <div class="rec editable"><strong>1. {{המלצה_1_כותרת}}</strong><br>{{המלצה_1_תיאור}}</div>
    <div class="rec editable"><strong>2. {{המלצה_2_כותרת}}</strong><br>{{המלצה_2_תיאור}}</div>
    <div class="rec editable"><strong>3. {{המלצה_3_כותרת}}</strong><br>{{המלצה_3_תיאור}}</div>
  </div>
  <p class="editable" style="text-align:center;margin-top:20px;opacity:.75;font-size:.9em">{{צעדים_מיידיים}}</p>
</div>
</section>

<!-- סעיף 8: מקורות ידע -->
<section id="s8">
<div class="sec-hdr" style="background:linear-gradient(135deg,#16a085,#1abc9c)">📚 מקורות ידע</div>
<div class="sources-wrap">
  <p style="text-align:center;font-size:1em;color:rgba(255,255,255,.8);max-width:700px;margin:0 auto 10px">הדוח מבוסס על מאגר ידע מוסמך ועדכני. כל ניתוח, סיכון והמלצה מתבסס על המקורות המפורטים להלן.</p>
  <div class="src-grid">
    <div class="src-cat">
      <div class="src-cat-title">🏛️ חוקים ורגולציית חינוך</div>
      <div class="src-item"><a href="https://innovate.education.gov.il/" target="_blank">📌 חוזר מנכ"ל לאסדרת חדשנות</a></div>
      <div class="src-item"><a href="https://www.nevo.co.il/law_html/law01/053_001.htm" target="_blank">⚖️ חוק לימוד חובה, תש"ט–1949</a></div>
      <div class="src-item"><a href="https://edu.gov.il/owlHtml/sites/MazkirutPed/ChozreMankal/" target="_blank">📂 מאגר חוזרי מנכ"ל</a></div>
      <div class="src-item"><a href="https://www.nevo.co.il/law_html/law01/058_001.htm" target="_blank">⚖️ חוק חינוך ממלכתי, 1953</a></div>
      <div class="src-item"><a href="https://edu.gov.il/minhalpedagogy/law" target="_blank">📋 חוקי חינוך כלליים</a></div>
      <div class="src-item"><a href="https://edu.gov.il/minhalpedagogy/shaat-chinuch/core" target="_blank">📖 תוכנית ליבה לשעת חינוך</a></div>
    </div>
    <div class="src-cat">
      <div class="src-cat-title">🤖 חדשנות אחראית ובינה מלאכותית</div>
      <div class="src-item"><a href="https://innovate.education.gov.il/AI" target="_blank">🧠 שימוש בכלי בינה מלאכותית בחינוך (2025)</a></div>
      <div class="src-item"><a href="https://innovate.education.gov.il/regulation-map" target="_blank">🗺️ מפת התמצאות לאסדרת חדשנות</a></div>
    </div>
    <div class="src-cat">
      <div class="src-cat-title">📊 תכנון, בקרה ושכר</div>
      <div class="src-item"><a href="https://harhayeda.gov.il/media/4wqogjpb/20241208-tasc-di-cio-methodology-for-publishing-v01.pdf" target="_blank">📄 מדריך לתכנון ובקרה (CIO, 2024)</a></div>
      <div class="src-item"><a href="https://www.irgun-morim.org.il/oz-letmura" target="_blank">📝 עוז לתמורה – ארגון המורים</a></div>
      <div class="src-item"><a href="https://www.edu.gov.il/minhalpedagogy/ofek-hadash" target="_blank">📝 אופק חדש – הסתדרות המורים</a></div>
    </div>
    <div class="src-cat">
      <div class="src-cat-title">📅 ארגון לימודים ופיתוח מקצועי</div>
      <div class="src-item"><a href="https://edu.gov.il/owlHtml/sites/MazkirutPed/ChozreMankal/Pages/tashpav-1-11.aspx" target="_blank">🗓️ ארגון הלמידה בחינוך העל-יסודי תשפ"ו</a></div>
      <div class="src-item"><a href="https://teachers.education.gov.il/professional-development" target="_blank">🎓 פיתוח מקצועי – פורטל עובדי הוראה</a></div>
      <div class="src-item"><a href="https://www.edu.gov.il/minhalpedagogy/histadrut" target="_blank">🏫 הנחיות הסתדרות המורים</a></div>
      <div class="src-item"><a href="https://edu.gov.il/minhalpedagogy/curricula/textbooks" target="_blank">📚 מאגר ספרי לימוד מאושרים</a></div>
    </div>
  </div>
  <div class="src-note"><strong>📌 הערת שימוש:</strong> כל ציטוט רגולטורי בסעיפי הסיכונים וההמלצות מתבסס על מקורות אלו. לבדיקת עדכניות המדיניות: <a href="https://edu.gov.il" target="_blank" style="color:#1abc9c">edu.gov.il</a></div>
</div>
</section>

<footer class="ftr">
  <p class="editable">{{כותרת_תחתונה}}</p>
  <p style="margin-top:6px;opacity:.8" class="editable">{{מקורות}}</p>
  <p style="margin-top:10px"><strong>פיתוח ועיצוב: ד"ר אסף אוזן</strong></p>
</footer>
</div>

<script>
let ed=false;
function toggleEdit(){
  ed=!ed;
  document.querySelectorAll('.editable').forEach(e=>e.setAttribute('contenteditable',ed));
  const b=document.getElementById('eBtn');
  b.textContent=ed?'💾 סיים עריכה':'🎨 עריכה';
  b.classList.toggle('on',ed);
}
function saveHTML(){
  const a=document.createElement('a');
  a.href='data:text/html;charset=utf-8,'+encodeURIComponent(document.documentElement.outerHTML);
  a.download='risk_report.html';a.click();
}
</script>
</body>
</html>

---
כעת נתח את מסמך התפיסה הבא והחלף את כל ה-{{}} בתוכן המתאים.
החזר את ה-HTML המלא בלבד — ללא שום טקסט לפני או אחרי:

[הדבק כאן את מסמך התפיסה]
```
