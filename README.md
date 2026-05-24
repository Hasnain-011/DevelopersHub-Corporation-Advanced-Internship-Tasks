<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>DevelopersHub – AI/ML Internship | Hasnain Ali</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=JetBrains+Mono:wght@400;600&display=swap" rel="stylesheet" />
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --bg: #0a0e1a;
    --bg2: #0f1525;
    --bg3: #151c30;
    --surface: #1a2340;
    --surface2: #1f2a4a;
    --border: rgba(99,179,237,0.12);
    --border2: rgba(99,179,237,0.25);
    --accent: #63b3ed;
    --accent2: #7ee8a2;
    --accent3: #f6ad55;
    --accent4: #fc8181;
    --accent5: #b794f4;
    --text: #e2e8f4;
    --text2: #94a3c0;
    --text3: #5a6a8a;
    --glow: 0 0 20px rgba(99,179,237,0.15);
  }

  html { scroll-behavior: smooth; }

  body {
    font-family: 'Space Grotesk', sans-serif;
    background: var(--bg);
    color: var(--text);
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* ── Animated background grid ── */
  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background-image:
      linear-gradient(rgba(99,179,237,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(99,179,237,0.03) 1px, transparent 1px);
    background-size: 48px 48px;
    pointer-events: none;
    z-index: 0;
  }

  /* ── Orbs ── */
  .orb {
    position: fixed;
    border-radius: 50%;
    filter: blur(80px);
    pointer-events: none;
    z-index: 0;
    animation: orb-drift 12s ease-in-out infinite alternate;
  }
  .orb-1 { width: 500px; height: 500px; background: rgba(99,179,237,0.06); top: -100px; right: -100px; animation-delay: 0s; }
  .orb-2 { width: 400px; height: 400px; background: rgba(126,232,162,0.05); bottom: 100px; left: -100px; animation-delay: -4s; }
  .orb-3 { width: 300px; height: 300px; background: rgba(183,148,244,0.05); top: 40%; left: 40%; animation-delay: -8s; }

  @keyframes orb-drift {
    from { transform: translate(0, 0) scale(1); }
    to   { transform: translate(30px, 20px) scale(1.05); }
  }

  /* ── Layout ── */
  .container {
    position: relative;
    z-index: 1;
    max-width: 900px;
    margin: 0 auto;
    padding: 0 24px 80px;
  }

  /* ── Hero ── */
  .hero {
    text-align: center;
    padding: 80px 0 60px;
    animation: fade-up 0.8s ease both;
  }

  .hero-badge {
    display: inline-flex;
    align-items: center;
    gap: 8px;
    background: rgba(99,179,237,0.08);
    border: 1px solid rgba(99,179,237,0.2);
    border-radius: 100px;
    padding: 6px 16px;
    font-size: 12px;
    color: var(--accent);
    letter-spacing: 0.08em;
    text-transform: uppercase;
    margin-bottom: 28px;
    animation: pulse-border 3s ease infinite;
  }

  @keyframes pulse-border {
    0%, 100% { border-color: rgba(99,179,237,0.2); }
    50%       { border-color: rgba(99,179,237,0.5); }
  }

  .hero-badge .dot {
    width: 6px; height: 6px;
    border-radius: 50%;
    background: var(--accent);
    animation: blink 1.5s ease infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0.2; }
  }

  .hero h1 {
    font-size: clamp(32px, 6vw, 56px);
    font-weight: 700;
    letter-spacing: -0.02em;
    line-height: 1.15;
    margin-bottom: 16px;
  }

  .hero h1 .line-1 { display: block; color: var(--text); }
  .hero h1 .line-2 {
    display: block;
    background: linear-gradient(135deg, var(--accent) 0%, var(--accent5) 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .hero-sub {
    font-size: 16px;
    color: var(--text2);
    max-width: 560px;
    margin: 0 auto 40px;
  }

  .hero-meta {
    display: flex;
    justify-content: center;
    gap: 32px;
    flex-wrap: wrap;
  }

  .meta-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4px;
  }

  .meta-val {
    font-size: 28px;
    font-weight: 700;
    color: var(--accent);
    font-family: 'JetBrains Mono', monospace;
    animation: count-up 1.5s ease both;
  }

  .meta-label {
    font-size: 12px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.08em;
  }

  .meta-sep {
    width: 1px;
    height: 40px;
    background: var(--border2);
    align-self: center;
  }

  /* ── Divider ── */
  .divider {
    height: 1px;
    background: linear-gradient(90deg, transparent, var(--border2), transparent);
    margin: 48px 0;
  }

  /* ── Section headings ── */
  .section-label {
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 11px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.12em;
    margin-bottom: 24px;
  }

  .section-label::before {
    content: '';
    flex: 0 0 32px;
    height: 1px;
    background: var(--border2);
  }

  /* ── Tech pills ── */
  .tech-row {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 48px;
    animation: fade-up 0.8s 0.3s ease both;
  }

  .pill {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    padding: 6px 14px;
    border-radius: 100px;
    border: 1px solid;
    transition: transform 0.2s, box-shadow 0.2s;
    cursor: default;
  }

  .pill:hover { transform: translateY(-2px); box-shadow: 0 4px 16px rgba(0,0,0,0.3); }

  .pill-blue   { color: var(--accent);  border-color: rgba(99,179,237,0.3);  background: rgba(99,179,237,0.07); }
  .pill-green  { color: var(--accent2); border-color: rgba(126,232,162,0.3); background: rgba(126,232,162,0.07); }
  .pill-amber  { color: var(--accent3); border-color: rgba(246,173,85,0.3);  background: rgba(246,173,85,0.07); }
  .pill-purple { color: var(--accent5); border-color: rgba(183,148,244,0.3); background: rgba(183,148,244,0.07); }
  .pill-red    { color: var(--accent4); border-color: rgba(252,129,129,0.3); background: rgba(252,129,129,0.07); }

  /* ── Task cards ── */
  .tasks-grid {
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .task-card {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 28px 32px;
    position: relative;
    overflow: hidden;
    transition: border-color 0.3s, transform 0.3s, box-shadow 0.3s;
    animation: fade-up 0.7s ease both;
  }

  .task-card::before {
    content: '';
    position: absolute;
    inset: 0;
    border-radius: 16px;
    opacity: 0;
    transition: opacity 0.3s;
    pointer-events: none;
  }

  .task-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 8px 32px rgba(0,0,0,0.4);
  }

  .task-card.blue  { --c: var(--accent);  --cb: rgba(99,179,237,0.07); }
  .task-card.green { --c: var(--accent2); --cb: rgba(126,232,162,0.07); }
  .task-card.amber { --c: var(--accent3); --cb: rgba(246,173,85,0.07); }

  .task-card:hover { border-color: var(--c); }
  .task-card::before { background: var(--cb); }
  .task-card:hover::before { opacity: 1; }

  /* Accent bar */
  .task-card::after {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--c), transparent);
    opacity: 0;
    transition: opacity 0.3s;
  }
  .task-card:hover::after { opacity: 1; }

  .task-header {
    display: flex;
    align-items: flex-start;
    justify-content: space-between;
    gap: 16px;
    margin-bottom: 16px;
  }

  .task-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    color: var(--c);
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border2);
    border-radius: 8px;
    padding: 4px 10px;
    white-space: nowrap;
    flex-shrink: 0;
  }

  .task-title {
    font-size: 18px;
    font-weight: 600;
    color: var(--text);
    flex: 1;
  }

  .status-badge {
    flex-shrink: 0;
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 100px;
    background: rgba(126,232,162,0.1);
    border: 1px solid rgba(126,232,162,0.25);
    color: var(--accent2);
    letter-spacing: 0.06em;
    text-transform: uppercase;
  }

  .task-desc {
    font-size: 14px;
    color: var(--text2);
    margin-bottom: 20px;
    line-height: 1.65;
  }

  /* Steps */
  .steps {
    display: flex;
    flex-direction: column;
    gap: 8px;
    margin-bottom: 20px;
  }

  .step {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    font-size: 13px;
    color: var(--text2);
  }

  .step-dot {
    width: 20px; height: 20px;
    border-radius: 50%;
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--c);
    display: flex; align-items: center; justify-content: center;
    font-size: 10px;
    color: var(--c);
    flex-shrink: 0;
    margin-top: 1px;
    font-family: 'JetBrains Mono', monospace;
  }

  /* Metrics row */
  .metrics {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
    gap: 12px;
    margin-bottom: 20px;
  }

  .metric {
    background: rgba(0,0,0,0.2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 12px 14px;
    text-align: center;
  }

  .metric-val {
    font-family: 'JetBrains Mono', monospace;
    font-size: 20px;
    font-weight: 600;
    color: var(--c);
    display: block;
    margin-bottom: 3px;
  }

  .metric-label {
    font-size: 11px;
    color: var(--text3);
    text-transform: uppercase;
    letter-spacing: 0.07em;
  }

  /* Tag chips */
  .tag-row {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }

  .tag {
    font-family: 'JetBrains Mono', monospace;
    font-size: 11px;
    padding: 3px 10px;
    border-radius: 6px;
    background: rgba(255,255,255,0.04);
    border: 1px solid var(--border);
    color: var(--text3);
  }

  /* ── Results table ── */
  .results-section {
    animation: fade-up 0.7s 0.2s ease both;
  }

  .results-table {
    width: 100%;
    border-collapse: separate;
    border-spacing: 0;
    font-size: 13px;
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 48px;
  }

  .results-table th {
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--text3);
    background: var(--bg3);
    padding: 12px 16px;
    text-align: left;
    font-weight: 500;
    border-bottom: 1px solid var(--border);
  }

  .results-table td {
    padding: 13px 16px;
    border-bottom: 1px solid var(--border);
    color: var(--text2);
    vertical-align: middle;
  }

  .results-table tr:last-child td { border-bottom: none; }

  .results-table tr:hover td { background: rgba(99,179,237,0.04); }

  .score-bar-wrap {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .score-bar-bg {
    flex: 1;
    height: 4px;
    background: rgba(255,255,255,0.06);
    border-radius: 2px;
    overflow: hidden;
  }

  .score-bar-fill {
    height: 100%;
    border-radius: 2px;
    animation: bar-grow 1.2s ease both;
    transform-origin: left;
  }

  @keyframes bar-grow {
    from { transform: scaleX(0); }
    to   { transform: scaleX(1); }
  }

  .score-val {
    font-family: 'JetBrains Mono', monospace;
    font-size: 12px;
    color: var(--text);
    min-width: 38px;
    text-align: right;
  }

  /* ── Setup block ── */
  .setup-block {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    overflow: hidden;
    margin-bottom: 48px;
    animation: fade-up 0.7s 0.3s ease both;
  }

  .setup-header {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 12px 20px;
    background: var(--bg3);
    border-bottom: 1px solid var(--border);
    font-size: 12px;
    color: var(--text3);
    font-family: 'JetBrains Mono', monospace;
  }

  .dot-row { display: flex; gap: 6px; }
  .dot-r { width: 10px; height: 10px; border-radius: 50%; background: #fc8181; }
  .dot-y { width: 10px; height: 10px; border-radius: 50%; background: #f6ad55; }
  .dot-g { width: 10px; height: 10px; border-radius: 50%; background: #7ee8a2; }

  .setup-block pre {
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    line-height: 1.8;
    padding: 20px 24px;
    color: var(--text2);
    overflow-x: auto;
  }

  pre .cmd  { color: var(--accent); }
  pre .cmt  { color: var(--text3); }
  pre .str  { color: var(--accent2); }
  pre .flag { color: var(--accent3); }

  /* ── Author card ── */
  .author-card {
    background: var(--surface);
    border: 1px solid var(--border2);
    border-radius: 20px;
    padding: 36px 40px;
    display: flex;
    align-items: center;
    gap: 28px;
    flex-wrap: wrap;
    position: relative;
    overflow: hidden;
    animation: fade-up 0.7s 0.4s ease both;
  }

  .author-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 2px;
    background: linear-gradient(90deg, var(--accent), var(--accent5), var(--accent2));
  }

  .author-avatar {
    width: 72px; height: 72px;
    border-radius: 50%;
    background: linear-gradient(135deg, rgba(99,179,237,0.3), rgba(183,148,244,0.3));
    border: 2px solid var(--border2);
    display: flex; align-items: center; justify-content: center;
    font-size: 26px;
    font-weight: 700;
    color: var(--text);
    flex-shrink: 0;
    position: relative;
  }

  .author-avatar::after {
    content: '';
    position: absolute;
    inset: -4px;
    border-radius: 50%;
    border: 1px solid rgba(99,179,237,0.2);
    animation: avatar-ring 2s linear infinite;
  }

  @keyframes avatar-ring {
    from { transform: rotate(0deg); }
    to   { transform: rotate(360deg); }
  }

  .author-info { flex: 1; }

  .author-name {
    font-size: 22px;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 4px;
  }

  .author-role {
    font-size: 14px;
    color: var(--text2);
    margin-bottom: 12px;
  }

  .author-chips {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
  }

  .author-chip {
    font-size: 11px;
    padding: 4px 12px;
    border-radius: 100px;
    border: 1px solid var(--border);
    color: var(--text3);
    background: rgba(255,255,255,0.03);
  }

  /* ── Timeline (structure) ── */
  .file-tree {
    background: var(--surface);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 24px;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px;
    color: var(--text2);
    line-height: 2;
    margin-bottom: 48px;
    animation: fade-up 0.7s 0.15s ease both;
  }

  .tree-folder { color: var(--accent3); }
  .tree-nb     { color: var(--accent); }
  .tree-md     { color: var(--accent5); }
  .tree-line   { color: var(--text3); user-select: none; }

  /* ── Animations ── */
  @keyframes fade-up {
    from { opacity: 0; transform: translateY(24px); }
    to   { opacity: 1; transform: translateY(0); }
  }

  @keyframes count-up {
    from { opacity: 0; transform: scale(0.7); }
    to   { opacity: 1; transform: scale(1); }
  }

  .task-card:nth-child(1) { animation-delay: 0.1s; }
  .task-card:nth-child(2) { animation-delay: 0.2s; }
  .task-card:nth-child(3) { animation-delay: 0.3s; }

  @media (max-width: 600px) {
    .hero { padding: 48px 0 40px; }
    .task-header { flex-wrap: wrap; }
    .author-card { flex-direction: column; text-align: center; }
    .author-chips { justify-content: center; }
  }
</style>
</head>
<body>

<div class="orb orb-1"></div>
<div class="orb orb-2"></div>
<div class="orb orb-3"></div>

<div class="container">

  <!-- ── Hero ── -->
  <div class="hero">
    <div class="hero-badge"><div class="dot"></div>AI / ML Engineering Internship</div>
    <h1>
      <span class="line-1">DevelopersHub Corporation</span>
      <span class="line-2">Advanced Internship Tasks</span>
    </h1>
    <p class="hero-sub">
      Hands-on implementation of transformer fine-tuning, production ML pipelines,
      and LLM-based classification systems.
    </p>
    <div class="hero-meta">
      <div class="meta-item">
        <span class="meta-val">3</span>
        <span class="meta-label">Tasks Completed</span>
      </div>
      <div class="meta-sep"></div>
      <div class="meta-item">
        <span class="meta-val">5</span>
        <span class="meta-label">Total Tasks</span>
      </div>
      <div class="meta-sep"></div>
      <div class="meta-item">
        <span class="meta-val">~95%</span>
        <span class="meta-label">Best Accuracy</span>
      </div>
      <div class="meta-sep"></div>
      <div class="meta-item">
        <span class="meta-val">May 25</span>
        <span class="meta-label">Due Date 2026</span>
      </div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ── Tech stack ── -->
  <div class="section-label">Technology Stack</div>
  <div class="tech-row">
    <span class="pill pill-blue">🤗 Transformers</span>
    <span class="pill pill-blue">BERT</span>
    <span class="pill pill-blue">PyTorch</span>
    <span class="pill pill-green">scikit-learn</span>
    <span class="pill pill-green">joblib</span>
    <span class="pill pill-amber">Gradio</span>
    <span class="pill pill-amber">Streamlit</span>
    <span class="pill pill-purple">LangChain</span>
    <span class="pill pill-purple">LLMs</span>
    <span class="pill pill-red">pandas</span>
    <span class="pill pill-red">numpy</span>
    <span class="pill pill-blue">HuggingFace Datasets</span>
    <span class="pill pill-green">GridSearchCV</span>
    <span class="pill pill-amber">TF-IDF</span>
  </div>

  <!-- ── Repo structure ── -->
  <div class="section-label">Repository Structure</div>
  <div class="file-tree">
    <span class="tree-folder">📁 developershub-ml-internship/</span><br>
    <span class="tree-line">├── </span><span class="tree-nb">Task1_BERT_News_Classifier.ipynb</span><br>
    <span class="tree-line">├── </span><span class="tree-nb">Task2_ML_Pipeline_Churn.ipynb</span><br>
    <span class="tree-line">├── </span><span class="tree-nb">Task5_Auto_Tagging_LLM.ipynb</span><br>
    <span class="tree-line">└── </span><span class="tree-md">README.md</span>
  </div>

  <!-- ── Tasks ── -->
  <div class="section-label">Completed Tasks</div>
  <div class="tasks-grid">

    <!-- Task 1 -->
    <div class="task-card blue">
      <div class="task-header">
        <span class="task-num">TASK 01</span>
        <span class="task-title">News Topic Classifier Using BERT</span>
        <span class="status-badge">✓ Complete</span>
      </div>
      <p class="task-desc">
        Fine-tuned <code style="font-family:'JetBrains Mono',monospace;font-size:12px;background:rgba(255,255,255,0.06);padding:2px 6px;border-radius:4px;">bert-base-uncased</code>
        on the AG News dataset to classify headlines into World, Sports, Business, and Sci/Tech categories.
        Deployed as an interactive Gradio app with live probability scoring.
      </p>
      <div class="steps">
        <div class="step"><div class="step-dot">1</div><span>Loaded AG News (120K train / 7.6K test) from Hugging Face Datasets</span></div>
        <div class="step"><div class="step-dot">2</div><span>Tokenized with BertTokenizer (max_length=128, dynamic padding)</span></div>
        <div class="step"><div class="step-dot">3</div><span>Fine-tuned 3 epochs — lr 2e-5, batch 16, FP16, weight decay 0.01</span></div>
        <div class="step"><div class="step-dot">4</div><span>Evaluated with Accuracy, weighted F1, and per-class confusion matrix</span></div>
        <div class="step"><div class="step-dot">5</div><span>Deployed Gradio interface for live headline classification</span></div>
      </div>
      <div class="metrics">
        <div class="metric"><span class="metric-val">~95%</span><span class="metric-label">Accuracy</span></div>
        <div class="metric"><span class="metric-val">~95%</span><span class="metric-label">F1 Score</span></div>
        <div class="metric"><span class="metric-val">4</span><span class="metric-label">Classes</span></div>
        <div class="metric"><span class="metric-val">110M</span><span class="metric-label">Parameters</span></div>
      </div>
      <div class="tag-row">
        <span class="tag">bert-base-uncased</span>
        <span class="tag">transformers</span>
        <span class="tag">HuggingFace Trainer</span>
        <span class="tag">gradio</span>
        <span class="tag">transfer learning</span>
      </div>
    </div>

    <!-- Task 2 -->
    <div class="task-card green">
      <div class="task-header">
        <span class="task-num">TASK 02</span>
        <span class="task-title">End-to-End ML Pipeline — Customer Churn</span>
        <span class="status-badge">✓ Complete</span>
      </div>
      <p class="task-desc">
        Built a production-ready, leakage-free sklearn Pipeline with ColumnTransformer for the IBM Telco Churn
        dataset. Trained three models, tuned hyperparameters via GridSearchCV, and exported the champion
        pipeline with joblib.
      </p>
      <div class="steps">
        <div class="step"><div class="step-dot">1</div><span>EDA on 7,043 customers — visualised churn by contract type, tenure, charges</span></div>
        <div class="step"><div class="step-dot">2</div><span>ColumnTransformer: median imputation + StandardScaler for numerics; OHE for categoricals</span></div>
        <div class="step"><div class="step-dot">3</div><span>Trained Logistic Regression, Random Forest, Gradient Boosting in unified Pipeline</span></div>
        <div class="step"><div class="step-dot">4</div><span>GridSearchCV (5-fold stratified CV) optimised for ROC-AUC</span></div>
        <div class="step"><div class="step-dot">5</div><span>Exported champion pipeline via joblib — verified reload + prediction consistency</span></div>
      </div>
      <div class="metrics">
        <div class="metric"><span class="metric-val">~81%</span><span class="metric-label">Accuracy</span></div>
        <div class="metric"><span class="metric-val">~0.85</span><span class="metric-label">ROC-AUC</span></div>
        <div class="metric"><span class="metric-val">3</span><span class="metric-label">Models Trained</span></div>
        <div class="metric"><span class="metric-val">5-Fold</span><span class="metric-label">CV Strategy</span></div>
      </div>
      <div class="tag-row">
        <span class="tag">sklearn.Pipeline</span>
        <span class="tag">ColumnTransformer</span>
        <span class="tag">GridSearchCV</span>
        <span class="tag">joblib</span>
        <span class="tag">RandomForest</span>
        <span class="tag">GradientBoosting</span>
      </div>
    </div>

    <!-- Task 5 -->
    <div class="task-card amber">
      <div class="task-header">
        <span class="task-num">TASK 05</span>
        <span class="task-title">Auto-Tagging Support Tickets Using LLM</span>
        <span class="status-badge">✓ Complete</span>
      </div>
      <p class="task-desc">
        Compared zero-shot, few-shot, and fine-tuned approaches for automatically tagging customer support
        tickets. Output: top-3 category tags with confidence scores per ticket, exported to JSON and CSV.
      </p>
      <div class="steps">
        <div class="step"><div class="step-dot">1</div><span>Curated 30 realistic tickets across 6 categories (Billing, Technical, Account, Product, Shipping, Security)</span></div>
        <div class="step"><div class="step-dot">2</div><span>Zero-shot: facebook/bart-large-mnli with raw category names</span></div>
        <div class="step"><div class="step-dot">3</div><span>Few-shot: keyword-enriched label descriptions as NLI hypothesis templates</span></div>
        <div class="step"><div class="step-dot">4</div><span>Fine-tuned baseline: TF-IDF + Logistic Regression with Leave-One-Out CV</span></div>
        <div class="step"><div class="step-dot">5</div><span>Side-by-side comparison with confusion matrices — top-3 tags output per ticket</span></div>
      </div>
      <div class="metrics">
        <div class="metric"><span class="metric-val">~75%</span><span class="metric-label">Zero-Shot</span></div>
        <div class="metric"><span class="metric-val">~83%</span><span class="metric-label">Few-Shot</span></div>
        <div class="metric"><span class="metric-val">~87%</span><span class="metric-label">Fine-Tuned</span></div>
        <div class="metric"><span class="metric-val">Top-3</span><span class="metric-label">Tags / Ticket</span></div>
      </div>
      <div class="tag-row">
        <span class="tag">bart-large-mnli</span>
        <span class="tag">zero-shot</span>
        <span class="tag">few-shot</span>
        <span class="tag">prompt engineering</span>
        <span class="tag">TF-IDF</span>
        <span class="tag">LOO-CV</span>
      </div>
    </div>

  </div><!-- /tasks-grid -->

  <div class="divider"></div>

  <!-- ── Results summary ── -->
  <div class="section-label results-section">Key Results Summary</div>
  <table class="results-table">
    <thead>
      <tr>
        <th>Task</th>
        <th>Model</th>
        <th>Accuracy</th>
        <th>F1 / AUC</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style="color:var(--text);font-weight:500;">Task 1 – News Classifier</td>
        <td style="font-family:'JetBrains Mono',monospace;font-size:12px;">BERT fine-tuned</td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:95%;background:var(--accent);animation-delay:0.2s;"></div></div>
            <span class="score-val">95%</span>
          </div>
        </td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:95%;background:var(--accent5);animation-delay:0.4s;"></div></div>
            <span class="score-val">F1 0.95</span>
          </div>
        </td>
      </tr>
      <tr>
        <td style="color:var(--text);font-weight:500;">Task 2 – Churn (LR)</td>
        <td style="font-family:'JetBrains Mono',monospace;font-size:12px;">Logistic Regression</td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:80%;background:var(--accent2);animation-delay:0.5s;"></div></div>
            <span class="score-val">80%</span>
          </div>
        </td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:84%;background:var(--accent5);animation-delay:0.6s;"></div></div>
            <span class="score-val">AUC 0.84</span>
          </div>
        </td>
      </tr>
      <tr>
        <td style="color:var(--text);font-weight:500;">Task 2 – Churn (RF)</td>
        <td style="font-family:'JetBrains Mono',monospace;font-size:12px;">Random Forest</td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:80%;background:var(--accent2);animation-delay:0.7s;"></div></div>
            <span class="score-val">80%</span>
          </div>
        </td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:84%;background:var(--accent5);animation-delay:0.8s;"></div></div>
            <span class="score-val">AUC 0.84</span>
          </div>
        </td>
      </tr>
      <tr>
        <td style="color:var(--text);font-weight:500;">Task 2 – Churn (GB)</td>
        <td style="font-family:'JetBrains Mono',monospace;font-size:12px;">Gradient Boosting</td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:81%;background:var(--accent2);animation-delay:0.9s;"></div></div>
            <span class="score-val">81%</span>
          </div>
        </td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:85%;background:var(--accent5);animation-delay:1.0s;"></div></div>
            <span class="score-val">AUC 0.85</span>
          </div>
        </td>
      </tr>
      <tr>
        <td style="color:var(--text);font-weight:500;">Task 5 – Zero-Shot</td>
        <td style="font-family:'JetBrains Mono',monospace;font-size:12px;">BART-large-MNLI</td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:75%;background:var(--accent3);animation-delay:1.1s;"></div></div>
            <span class="score-val">75%</span>
          </div>
        </td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:74%;background:var(--accent5);animation-delay:1.2s;"></div></div>
            <span class="score-val">F1 0.74</span>
          </div>
        </td>
      </tr>
      <tr>
        <td style="color:var(--text);font-weight:500;">Task 5 – Few-Shot</td>
        <td style="font-family:'JetBrains Mono',monospace;font-size:12px;">BART + enriched labels</td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:83%;background:var(--accent3);animation-delay:1.3s;"></div></div>
            <span class="score-val">83%</span>
          </div>
        </td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:82%;background:var(--accent5);animation-delay:1.4s;"></div></div>
            <span class="score-val">F1 0.82</span>
          </div>
        </td>
      </tr>
      <tr>
        <td style="color:var(--text);font-weight:500;">Task 5 – Fine-Tuned</td>
        <td style="font-family:'JetBrains Mono',monospace;font-size:12px;">TF-IDF + LR (LOO-CV)</td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:87%;background:var(--accent3);animation-delay:1.5s;"></div></div>
            <span class="score-val">87%</span>
          </div>
        </td>
        <td>
          <div class="score-bar-wrap">
            <div class="score-bar-bg"><div class="score-bar-fill" style="width:86%;background:var(--accent5);animation-delay:1.6s;"></div></div>
            <span class="score-val">F1 0.86</span>
          </div>
        </td>
      </tr>
    </tbody>
  </table>

  <!-- ── Setup block ── -->
  <div class="section-label">Setup & Installation</div>
  <div class="setup-block">
    <div class="setup-header">
      <div class="dot-row"><div class="dot-r"></div><div class="dot-y"></div><div class="dot-g"></div></div>
      bash — setup
    </div>
    <pre><span class="cmt"># Clone the repository</span>
<span class="cmd">git clone</span> <span class="str">https://github.com/hasnainali/developershub-ml-internship.git</span>
<span class="cmd">cd</span> developershub-ml-internship

<span class="cmt"># Install all dependencies</span>
<span class="cmd">pip install</span> <span class="flag">transformers datasets torch scikit-learn</span> <span class="flag">\</span>
             <span class="flag">gradio joblib pandas numpy matplotlib seaborn accelerate</span>

<span class="cmt"># Launch Jupyter</span>
<span class="cmd">jupyter notebook</span>

<span class="cmt"># GPU recommended for Task 1 (Google Colab free tier works great)</span>
<span class="cmt"># Tasks 2 and 5 run fine on CPU</span></pre>
  </div>

  <div class="divider"></div>

  <!-- ── Author ── -->
  <div class="section-label">Author</div>
  <div class="author-card">
    <div class="author-avatar">HA</div>
    <div class="author-info">
      <div class="author-name">Hasnain Ali</div>
      <div class="author-role">AI / ML Engineering Intern &nbsp;·&nbsp; DevelopersHub Corporation</div>
      <div class="author-chips">
        <span class="author-chip">🤖 Machine Learning</span>
        <span class="author-chip">🧠 NLP & Transformers</span>
        <span class="author-chip">📊 Data Science</span>
        <span class="author-chip">⚙️ MLOps</span>
      </div>
    </div>
  </div>

</div><!-- /container -->
</body>
</html>
