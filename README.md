# -
鍼灸院未来予想図シュミレーション
<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>鍼灸院経営シュミレーション</title>
  <style>
    /* 設計通りのCSS */
    body { font-family: Arial, sans-serif; margin: 20px; }
    .container { max-width: 1200px; margin: 0 auto; }
    .header { text-align: center; margin-bottom: 30px; }
    .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 30px; }
    .input-section, .results-section { background: #f5f5f5; padding: 20px; border-radius: 10px; }
    .form-group { margin-bottom: 15px; }
    label { display: block; margin-bottom: 5px; font-weight: bold; }
    input[type="number"] { width: 100%; padding: 10px; border: 1px solid #ddd; border-radius: 5px; }
    button { background: #2E5B8A; color: white; padding: 15px 30px; border: none; border-radius: 5px; cursor: pointer; font-size: 16px; }
    .results { margin-top: 20px; }
    .result-item { margin-bottom: 10px; font-weight: bold; }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">
      <h1>技術向上後の鍼灸院経営『未来予想図』シュミレーション</h1>
      <p>使い方と説明</p>
      <p>・入力欄に「今のあなたのリアルな数字」を入れてください。すると、算出結果欄に高単価メニュー導入後の「鍼灸院の新しい未来」が表示されます。</p>
    </div>

    <div class="form-grid">
      <div class="input-section">
        <h2>今の鍼灸院のリアルな数字</h2>
        <div class="form-group">
          <label for="current-price">施術単価（円）</label>
          <input type="number" id="current-price" value="10000">
        </div>
        <div class="form-group">
          <label for="patient-count">1日の平均患者人数（人）</label>
          <input type="number" id="patient-count" value="10">
        </div>
        <div class="form-group">
          <label for="work-days">月の稼働日数（日）</label>
          <input type="number" id="work-days" value="25">
        </div>
        <div class="form-group">
          <label for="treatment-time">1人あたりの施術時間（分）</label>
          <input type="number" id="treatment-time" value="60">
        </div>
        <div class="form-group">
          <label for="fatigue-level">疲労度（1〜10）</label>
          <input type="number" id="fatigue-level" value="9">
        </div>
        <p>※仮の数値が入力されていますのであなたのリアルな数字を入力してください。</p>
        <button onclick="calculateResults()">結果を算出</button>
      </div>

      <div class="results-section">
        <h2>鍼灸院の未来予想図</h2>
        <div class="results">
          <p>月商：¥<span id="monthly-sales">0</span></p>
          <p>①毎月新しく生み出される自由時間：<span id="free-time">0</span>時間</p>
          <p>②高単価メニュー導入後のリピート収益／月：¥<span id="repeat-revenue">0</span></p>
          <p>③高単価メニュー導入後の推定疲労度：<span id="estimated-fatigue">0</span>度</p>
          <p>④現在の月商とリピート収益の合計：¥<span id="total-revenue">0</span></p>
        </div>
      </div>
    </div>

    <script>
      function calculateResults() {
        const currentPrice = parseInt(document.getElementById('current-price').value) || 0;
        const patientCount = parseInt(document.getElementById('patient-count').value) || 0;
        const workDays = parseInt(document.getElementById('work-days').value) || 0;
        const treatmentTime = parseInt(document.getElementById('treatment-time').value) || 0;
        const fatigueLevel = parseInt(document.getElementById('fatigue-level').value) || 0;

        // 計算処理
        const newPrice = currentPrice * 2;
        const newPatientCount = patientCount / 2;
        const monthlySales = newPrice * newPatientCount * workDays;
        const freeTime = patientCount * treatmentTime / 60 * 0.5;
        const repeatRevenue = monthlySales * 0.8;
        const estimatedFatigue = fatigueLevel * 0.5;
        const totalRevenue = monthlySales + repeatRevenue;

        // 結果表示
        document.getElementById('monthly-sales').textContent = monthlySales.toLocaleString();
        document.getElementById('free-time').textContent = freeTime.toFixed(1);
        document.getElementById('repeat-revenue').textContent = repeatRevenue.toLocaleString();
        document.getElementById('estimated-fatigue').textContent = estimatedFatigue.toFixed(1);
        document.getElementById('total-revenue').textContent = totalRevenue.toLocaleString();
      }
    </script>
  </div>
</body>
</html>
