<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>LIFE OS 2026 – Ultra Discipline</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
/* ===== RESET ===== */
* {
  box-sizing: border-box;
  font-family: Inter, system-ui, sans-serif;
}

/* ===== BASE ===== */
body {
  margin: 0;
  background: #0b0e14;
  color: #e5e7eb;
  line-height: 1.6;
}

h1, h2 {
  margin-top: 0;
}

ul {
  padding-left: 18px;
}

/* ===== LAYOUT ===== */
.header {
  padding: 28px;
  text-align: center;
  border-bottom: 1px solid #1f2937;
}

.tagline {
  color: #2eff7b;
  font-weight: 500;
}

.block {
  background: #121826;
  margin: 16px;
  padding: 22px;
  border-radius: 12px;
}

.focus {
  border-left: 4px solid #5da9ff;
}

.power {
  border-left: 4px solid #2eff7b;
}

.rule {
  margin-top: 10px;
  color: #2eff7b;
  font-weight: 500;
}

.laws {
  background: #111827;
  border: 2px dashed #ef4444;
}

.footer {
  text-align: center;
  padding: 18px;
  color: #9ca3af;
}

/* ===== CHECKBOX ===== */
label {
  display: block;
  margin: 8px 0;
}

input[type="checkbox"] {
  transform: scale(1.2);
  margin-right: 8px;
}

/* ===== MOBILE ===== */
@media (max-width: 768px) {
  body {
    font-size: 15px;
  }
  .block {
    margin: 12px;
    padding: 18px;
  }
  h1 {
    font-size: 22px;
  }
}
</style>
</head>

<body>

<!-- ===== HEADER ===== -->
<header class="header">
  <h1>LIFE OS 2026</h1>
  <p class="tagline">I don’t chase hype. I execute systems.</p>
</header>

<!-- ===== MORNING ===== -->
<section class="block">
  <h2>🌅 Morning – Setup Mode</h2>
  <ul>
    <li>8:00–8:20 → Wake, wash, water, bed (Phone ❌)</li>
    <li>8:20–9:00 → Observe community (no scroll)</li>
    <li>Note 5 creator tweets + rough ideas</li>
  </ul>
</section>

<!-- ===== CORE BLOCK 1 ===== -->
<section class="block focus">
  <h2>🧠 Core Block 1 – Airdrop Content (Think + Draft)</h2>
  <p>9:00 – 12:00</p>
  <ul>
    <li>Tweet drafts</li>
    <li>Insight notes</li>
    <li>Education / Update / Opinion</li>
  </ul>
  <div class="rule">Minimum Output: 3 solid drafts</div>
</section>

<!-- ===== BREAK ===== -->
<section class="block">
  <h2>☕ Break</h2>
  <p>12:00 – 12:30 (No reels, no scroll)</p>
</section>

<!-- ===== CORE BLOCK 2 ===== -->
<section class="block focus">
  <h2>🧠 Core Block 2 – Post + Engage</h2>
  <p>12:30 – 3:00</p>
  <ul>
    <li>Post best 1–2 tweets</li>
    <li>Quality replies</li>
    <li>Community presence</li>
  </ul>
  <div class="rule">Spam ❌ | Copy ❌ | Samajh ke likhna ✅</div>
</section>

<!-- ===== RESET ===== -->
<section class="block">
  <h2>💤 Reset</h2>
  <p>3:00 – 4:00 → Walk / Eyes closed / Screens ❌</p>
</section>

<!-- ===== TRADING ===== -->
<section class="block">
  <h2>📊 Trading Learning (Secondary)</h2>
  <ul>
    <li>Chart reading</li>
    <li>Backtesting</li>
    <li>Notes (No live trade)</li>
  </ul>
  <div class="rule">Trading secondary | Content time sacred</div>
</section>

<!-- ===== NIGHT POWER ===== -->
<section class="block power">
  <h2>🔥 Night Power Block – Creator Mode</h2>
  <p>7:00 – 10:30</p>
  <ul>
    <li>High-level airdrop content</li>
    <li>Threads & deep insights</li>
    <li>Original takes</li>
  </ul>
  <div class="rule">Quantity ❌ | Authority ✅</div>
</section>

<!-- ===== DAILY EXECUTION ===== -->
<section class="block">
  <h2>✅ Daily Execution (Streak System)</h2>

  <label><input type="checkbox" class="task"> Morning setup done</label>
  <label><input type="checkbox" class="task"> 3 content drafts written</label>
  <label><input type="checkbox" class="task"> 1–2 tweets published</label>
  <label><input type="checkbox" class="task"> Night power block completed</label>

  <p>🔥 Streak: <strong><span id="streak">0</span></strong> days</p>
</section>

<!-- ===== DISCIPLINE LAWS ===== -->
<section class="block laws">
  <h2>📵 Discipline Laws</h2>
  <ul>
    <li>Content = kaam</li>
    <li>Scroll = kaam nahi</li>
    <li>Bina likhe din = FAIL</li>
    <li>Copy vibe = DISQUALIFY</li>
  </ul>
</section>

<!-- ===== FOOTER ===== -->
<footer class="footer">
  <p>Airdrop creators earn. Testnet grinders don’t.</p>
  <strong>Visibility &gt; Wallet count</strong>
</footer>

<!-- ===== SCRIPT ===== -->
<script>
/* ===== STREAK LOGIC ===== */
const tasks = document.querySelectorAll(".task");
const streakEl = document.getElementById("streak");

let streak = parseInt(localStorage.getItem("streak")) || 0;
streakEl.innerText = streak;

tasks.forEach(task => {
  task.addEventListener("change", checkAllDone);
});

function checkAllDone() {
  const allDone = [...tasks].every(t => t.checked);

  if (allDone) {
    streak++;
    localStorage.setItem("streak", streak);
    streakEl.innerText = streak;
  }
}

/* ===== DAILY RESET ===== */
function dailyReset() {
  const today = new Date().toDateString();
  const lastReset = localStorage.getItem("lastReset");

  if (lastReset !== today) {
    tasks.forEach(t => t.checked = false);
    localStorage.setItem("lastReset", today);
  }
}
dailyReset();

/* ===== NIGHT REMINDER ===== */
function nightReminder() {
  const now = new Date();
  const reminder = new Date();
  reminder.setHours(19, 0, 0); // 7 PM

  const delay = reminder - now;
  if (delay > 0) {
    setTimeout(() => {
      alert("🔥 Night Power Block time. Build authority.");
    }, delay);
  }
}
nightReminder();
</script>

</body>
</html>
