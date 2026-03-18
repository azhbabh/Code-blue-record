<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Code Blue Record System</title>
<link href="https://fonts.googleapis.com/css2?family=Rajdhani:wght@400;500;600;700&family=Share+Tech+Mono&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #f0f4f8;
    --surface: #ffffff;
    --surface2: #f7f9fc;
    --border: #dde3ed;
    --border-strong: #bcc8dc;
    --red: #d62839;
    --red-light: #fff0f1;
    --red-mid: #ffd6da;
    --blue: #1a56db;
    --blue-light: #eff4ff;
    --blue-mid: #c7d7fd;
    --green: #057a55;
    --green-light: #ecfdf5;
    --green-mid: #a7f3d0;
    --yellow: #92400e;
    --yellow-light: #fffbeb;
    --yellow-mid: #fde68a;
    --purple: #6b21a8;
    --purple-light: #faf5ff;
    --purple-mid: #e9d5ff;
    --orange: #9a3412;
    --orange-light: #fff7ed;
    --orange-mid: #fed7aa;
    --cyan: #0e7490;
    --cyan-light: #ecfeff;
    --cyan-mid: #a5f3fc;
    --text: #1e293b;
    --text-mid: #475569;
    --text-dim: #94a3b8;
    --shadow: 0 1px 3px rgba(0,0,0,0.08), 0 1px 2px rgba(0,0,0,0.05);
    --shadow-md: 0 4px 12px rgba(0,0,0,0.10), 0 2px 4px rgba(0,0,0,0.06);
    --mono: 'Share Tech Mono', monospace;
    --head: 'Rajdhani', sans-serif;
    --body: 'Inter', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body { background: var(--bg); color: var(--text); font-family: var(--body); min-height: 100vh; }

  /* HEADER */
  .header {
    background: var(--surface);
    border-bottom: 3px solid var(--red);
    padding: 0 32px;
    position: sticky; top: 0; z-index: 100;
    box-shadow: var(--shadow-md);
  }
  .header-inner {
    max-width: 1280px; margin: 0 auto;
    display: flex; align-items: center; justify-content: space-between;
    height: 68px;
  }
  .logo { display: flex; align-items: center; gap: 14px; }
  .logo-icon {
    width: 44px; height: 44px; background: var(--red); border-radius: 10px;
    display: flex; align-items: center; justify-content: center; font-size: 22px;
    box-shadow: 0 2px 8px rgba(214,40,57,0.35);
    animation: pulse-red 2.2s ease-in-out infinite;
  }
  @keyframes pulse-red {
    0%,100% { box-shadow: 0 2px 8px rgba(214,40,57,0.35); }
    50%      { box-shadow: 0 2px 20px rgba(214,40,57,0.65); }
  }
  .logo-text h1 {
    font-family: var(--head); font-size: 22px; font-weight: 700;
    letter-spacing: 3px; color: var(--red); text-transform: uppercase;
  }
  .logo-text span { font-family: var(--mono); font-size: 10px; color: var(--text-dim); letter-spacing: 1.5px; }
  .header-right { display: flex; align-items: center; gap: 14px; }
  .live-clock {
    font-family: var(--mono); font-size: 17px; font-weight: 600; color: var(--blue);
    background: var(--blue-light); border: 1px solid var(--blue-mid);
    padding: 6px 14px; border-radius: 6px;
  }
  .record-count-chip {
    background: var(--red-light); border: 1px solid var(--red-mid); border-radius: 6px;
    padding: 6px 14px; font-family: var(--mono); font-size: 12px; color: var(--red);
    font-weight: 700; letter-spacing: 1px;
  }
  .record-count-chip span { font-size: 17px; }

  /* MAIN */
  .main { max-width: 1280px; margin: 0 auto; padding: 28px 24px; }

  /* ALERT BANNER */
  .alert-banner {
    background: var(--red-light); border: 1px solid var(--red-mid);
    border-left: 4px solid var(--red); border-radius: 8px;
    padding: 12px 18px; margin-bottom: 24px;
    display: flex; align-items: center; gap: 10px;
    font-family: var(--head); font-size: 14px; letter-spacing: 1.5px;
    color: var(--red); text-transform: uppercase;
  }
  .blink { animation: blink 1s step-end infinite; font-size: 16px; }
  @keyframes blink { 0%,100%{opacity:1} 50%{opacity:0} }

  /* FORM CARD */
  .form-card {
    background: var(--surface); border: 1px solid var(--border); border-radius: 12px;
    padding: 28px 32px; margin-bottom: 28px; box-shadow: var(--shadow);
    position: relative; overflow: hidden;
  }
  .form-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
    background: linear-gradient(90deg, var(--red), var(--blue));
  }

  .section-title {
    font-family: var(--head); font-size: 12px; letter-spacing: 2.5px; color: var(--blue);
    text-transform: uppercase; font-weight: 700; margin-bottom: 18px;
    display: flex; align-items: center; gap: 8px;
  }
  .section-title::after {
    content: ''; flex: 1; height: 1px;
    background: linear-gradient(90deg, var(--border-strong), transparent);
  }

  .form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-bottom: 20px; }
  .form-grid.three { grid-template-columns: 1fr 1fr 1fr; }
  .form-group { display: flex; flex-direction: column; gap: 5px; }
  .form-group.full { grid-column: 1 / -1; }

  label { font-size: 11px; font-weight: 600; color: var(--text-mid); letter-spacing: 0.8px; text-transform: uppercase; }
  input, select, textarea {
    background: var(--surface2); border: 1px solid var(--border); border-radius: 6px;
    color: var(--text); font-family: var(--body); font-size: 14px; padding: 9px 12px;
    outline: none; transition: border-color 0.18s, box-shadow 0.18s;
  }
  input:focus, select:focus, textarea:focus {
    border-color: var(--blue); box-shadow: 0 0 0 3px rgba(26,86,219,0.12); background: #fff;
  }
  select option { background: #fff; color: var(--text); }
  textarea { resize: vertical; min-height: 80px; }
  ::placeholder { color: var(--text-dim); }

  /* TOGGLE YES/NO */
  .toggle-group {
    display: flex; border-radius: 7px; overflow: hidden;
    border: 1.5px solid var(--border-strong); width: fit-content; box-shadow: var(--shadow);
  }
  .toggle-btn {
    padding: 9px 30px; border: none; background: var(--surface2);
    color: var(--text-dim); font-family: var(--head); font-size: 13px; font-weight: 600;
    letter-spacing: 2px; cursor: pointer; transition: all 0.18s; text-transform: uppercase;
  }
  .toggle-btn:first-child { border-right: 1.5px solid var(--border-strong); }
  .toggle-btn:hover { background: var(--border); color: var(--text); }
  .toggle-btn.active-yes { background: var(--green-light); color: var(--green); font-weight: 700; }
  .toggle-btn.active-no  { background: var(--red-light);   color: var(--red);   font-weight: 700; }
  .announce-time-wrap { display: none; align-items: center; gap: 10px; margin-top: 10px; animation: fadeIn 0.22s ease; }
  .announce-time-wrap.visible { display: flex; }
  @keyframes fadeIn { from{opacity:0;transform:translateY(-5px)} to{opacity:1;transform:none} }

  /* ECG RHYTHM BUTTONS */
  .rhythm-group { display: flex; gap: 8px; flex-wrap: wrap; margin-top: 4px; }
  .rhythm-btn {
    padding: 9px 20px; border-radius: 7px; border: 1.5px solid var(--border-strong);
    background: var(--surface2); color: var(--text-mid); font-family: var(--mono);
    font-size: 13px; font-weight: 600; letter-spacing: 1px; cursor: pointer;
    transition: all 0.18s; text-transform: uppercase; box-shadow: var(--shadow);
  }
  .rhythm-btn:hover { border-color: var(--blue); color: var(--blue); background: var(--blue-light); }
  .rhythm-btn.active-vf  { background: var(--red-light);    border-color: var(--red);    color: var(--red);    box-shadow: 0 0 0 3px var(--red-mid); }
  .rhythm-btn.active-vt  { background: var(--orange-light); border-color: #c2410c;       color: #c2410c;       box-shadow: 0 0 0 3px var(--orange-mid); }
  .rhythm-btn.active-pea { background: var(--yellow-light); border-color: #b45309;       color: #b45309;       box-shadow: 0 0 0 3px var(--yellow-mid); }
  .rhythm-btn.active-asy { background: var(--purple-light); border-color: var(--purple); color: var(--purple); box-shadow: 0 0 0 3px var(--purple-mid); }
  .rhythm-btn.active-oth { background: var(--cyan-light);   border-color: var(--cyan);   color: var(--cyan);   box-shadow: 0 0 0 3px var(--cyan-mid); }
  .rhythm-others-input { display: none; margin-top: 8px; animation: fadeIn 0.22s ease; }
  .rhythm-others-input.visible { display: block; }

  /* CHECKLIST */
  .checklist-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(190px,1fr)); gap: 8px; margin-top: 4px; }
  .check-item {
    display: flex; align-items: center; gap: 9px;
    background: var(--surface2); border: 1px solid var(--border); border-radius: 6px;
    padding: 8px 11px; cursor: pointer; transition: all 0.15s;
  }
  .check-item:hover { border-color: var(--blue); background: var(--blue-light); }
  .check-item input[type="checkbox"] { width: 15px; height: 15px; accent-color: var(--blue); padding: 0; border: none; background: none; box-shadow: none; flex-shrink: 0; }
  .check-item label { font-size: 12px; font-weight: 500; cursor: pointer; color: var(--text); text-transform: none; letter-spacing: 0; }

  /* IV MEDICATION */
  .iv-med-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px,1fr)); gap: 10px; margin-top: 6px; }
  .iv-med-card {
    background: var(--surface2); border: 1.5px solid var(--border); border-radius: 8px;
    overflow: hidden; transition: all 0.18s; cursor: pointer;
  }
  .iv-med-card:hover { border-color: var(--blue-mid); }
  .iv-med-card.selected { border-color: var(--blue); background: var(--blue-light); box-shadow: 0 0 0 3px var(--blue-mid); }
  .iv-med-header {
    display: flex; align-items: center; gap: 9px;
    padding: 10px 12px; user-select: none;
  }
  .iv-med-header input[type="checkbox"] { width: 15px; height: 15px; accent-color: var(--blue); flex-shrink: 0; cursor: pointer; }
  .iv-med-name { font-size: 13px; font-weight: 600; color: var(--text); flex: 1; }
  .iv-med-badge {
    font-family: var(--mono); font-size: 10px; font-weight: 700;
    padding: 2px 7px; border-radius: 4px; text-transform: uppercase; letter-spacing: 0.5px;
    background: var(--purple-light); color: var(--purple); border: 1px solid var(--purple-mid);
  }
  .iv-med-body {
    display: none; padding: 10px 12px; padding-top: 0;
    border-top: 1px solid var(--border);
    animation: fadeIn 0.2s ease;
  }
  .iv-med-body.visible { display: block; }
  .iv-dose-row { display: flex; align-items: center; gap: 8px; margin-top: 8px; flex-wrap: wrap; }
  .iv-dose-row label { font-size: 10px; font-weight: 700; color: var(--text-dim); letter-spacing: 1px; text-transform: uppercase; white-space: nowrap; margin-bottom: 0; }
  .iv-time-input { font-family: var(--mono); font-size: 13px; padding: 6px 9px; border-radius: 5px; border: 1px solid var(--border-strong); background: #fff; color: var(--text); outline: none; width: 120px; transition: border-color 0.15s; }
  .iv-time-input:focus { border-color: var(--blue); box-shadow: 0 0 0 2px var(--blue-mid); }
  .btn-stat {
    display: flex; align-items: center; gap: 5px;
    padding: 6px 12px; border-radius: 5px;
    background: var(--red); color: #fff;
    border: none; font-family: var(--head); font-size: 12px; font-weight: 700;
    letter-spacing: 1.5px; cursor: pointer; text-transform: uppercase;
    box-shadow: 0 2px 6px rgba(214,40,57,0.3); transition: all 0.15s; white-space: nowrap;
  }
  .btn-stat:hover { background: #b91c2e; transform: translateY(-1px); }
  .btn-stat:active { transform: translateY(0); }
  .stat-dot { width: 7px; height: 7px; border-radius: 50%; background: #fff; animation: statpulse 0.8s ease-in-out infinite; }
  @keyframes statpulse { 0%,100%{opacity:1;transform:scale(1)} 50%{opacity:0.5;transform:scale(0.7)} }
  .iv-dose-count {
    display: flex; align-items: center; gap: 6px; margin-top: 8px;
  }
  .dose-num-btn { width: 26px; height: 26px; border-radius: 5px; border: 1px solid var(--border-strong); background: var(--surface2); color: var(--text-mid); font-size: 16px; cursor: pointer; display: flex; align-items: center; justify-content: center; font-weight: 700; transition: all 0.12s; line-height: 1; }
  .dose-num-btn:hover { background: var(--blue-light); border-color: var(--blue); color: var(--blue); }
  .dose-count-val { font-family: var(--mono); font-size: 13px; font-weight: 700; color: var(--text); min-width: 24px; text-align: center; }
  .dose-times-list { margin-top: 6px; display: flex; flex-wrap: wrap; gap: 5px; }
  .dose-time-chip {
    display: flex; align-items: center; gap: 5px;
    background: #fff; border: 1px solid var(--border-strong); border-radius: 5px;
    padding: 3px 8px 3px 10px; font-family: var(--mono); font-size: 11px; color: var(--blue); font-weight: 600;
  }
  .dose-time-chip .rm { cursor: pointer; color: var(--red); font-size: 12px; line-height: 1; padding: 0 2px; font-weight: 700; }
  .dose-time-chip .rm:hover { color: #b91c2e; }
  .add-dose-row { display: flex; align-items: center; gap: 6px; margin-top: 8px; flex-wrap: wrap; }
  .btn-add-dose {
    padding: 6px 12px; border-radius: 5px;
    background: var(--green-light); color: var(--green);
    border: 1px solid var(--green-mid); font-family: var(--head); font-size: 12px;
    font-weight: 700; letter-spacing: 1px; cursor: pointer; text-transform: uppercase; transition: all 0.15s;
  }
  .btn-add-dose:hover { background: var(--green-mid); }

  /* OUTCOME BUTTONS */
  .outcome-group { display: flex; gap: 8px; flex-wrap: wrap; }
  .outcome-btn {
    padding: 9px 18px; border-radius: 7px; border: 1.5px solid var(--border-strong);
    background: var(--surface2); color: var(--text-mid); font-family: var(--head);
    font-size: 13px; font-weight: 600; letter-spacing: 1.5px; cursor: pointer;
    transition: all 0.18s; text-transform: uppercase; box-shadow: var(--shadow);
  }
  .outcome-btn:hover { border-color: var(--blue); color: var(--blue); background: var(--blue-light); }
  .outcome-btn.active-rosc     { background: var(--green-light);  border-color: var(--green);  color: var(--green);  box-shadow: 0 0 0 3px var(--green-mid); }
  .outcome-btn.active-deceased { background: var(--red-light);    border-color: var(--red);    color: var(--red);    box-shadow: 0 0 0 3px var(--red-mid); }
  .outcome-btn.active-transfer { background: var(--blue-light);   border-color: var(--blue);   color: var(--blue);   box-shadow: 0 0 0 3px var(--blue-mid); }
  .outcome-btn.active-ongoing  { background: var(--yellow-light); border-color: #b45309;       color: #b45309;       box-shadow: 0 0 0 3px var(--yellow-mid); }

  /* ACTION BUTTONS */
  .action-row { display: flex; gap: 10px; justify-content: flex-end; margin-top: 24px; padding-top: 20px; border-top: 1px solid var(--border); }
  .btn { padding: 10px 24px; border-radius: 7px; border: none; font-family: var(--head); font-size: 13px; font-weight: 700; letter-spacing: 2px; cursor: pointer; text-transform: uppercase; transition: all 0.18s; }
  .btn-clear { background: var(--surface2); border: 1.5px solid var(--border-strong); color: var(--text-mid); }
  .btn-clear:hover { background: var(--border); color: var(--text); }
  .btn-save  { background: var(--red);  color: #fff; box-shadow: 0 2px 10px rgba(214,40,57,0.3); }
  .btn-save:hover  { background: #b91c2e; transform: translateY(-1px); box-shadow: 0 4px 16px rgba(214,40,57,0.4); }
  .btn-print { background: var(--blue); color: #fff; box-shadow: 0 2px 10px rgba(26,86,219,0.2); }
  .btn-print:hover { background: #1447b0; transform: translateY(-1px); }

  /* RECORDS CARD */
  .records-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; box-shadow: var(--shadow); }
  .records-header { padding: 16px 24px; border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: space-between; background: var(--surface2); }
  .records-header h2 { font-family: var(--head); font-size: 15px; letter-spacing: 2px; color: var(--text); text-transform: uppercase; font-weight: 700; }
  .search-box { background: var(--surface); border: 1px solid var(--border-strong); border-radius: 6px; color: var(--text); font-family: var(--body); font-size: 13px; padding: 7px 12px; outline: none; width: 230px; transition: border-color 0.18s, box-shadow 0.18s; }
  .search-box:focus { border-color: var(--blue); box-shadow: 0 0 0 3px rgba(26,86,219,0.12); }
  ::placeholder { color: var(--text-dim); }

  table { width: 100%; border-collapse: collapse; }
  thead tr { background: var(--surface2); border-bottom: 2px solid var(--border-strong); }
  th { font-family: var(--mono); font-size: 10px; color: var(--blue); letter-spacing: 1.5px; text-transform: uppercase; padding: 11px 16px; text-align: left; font-weight: 700; }
  tbody tr { border-bottom: 1px solid var(--border); transition: background 0.12s; }
  tbody tr:hover { background: var(--blue-light); }
  td { padding: 12px 16px; font-size: 13px; color: var(--text); }
  td.mono { font-family: var(--mono); font-size: 12px; color: var(--blue); }
  td.name { font-weight: 600; }

  /* BADGES */
  .badge { display: inline-flex; align-items: center; gap: 3px; padding: 3px 9px; border-radius: 5px; font-family: var(--mono); font-size: 11px; letter-spacing: 0.8px; text-transform: uppercase; font-weight: 700; }
  .badge-rosc     { background: var(--green-light);  color: var(--green);  border: 1px solid var(--green-mid); }
  .badge-deceased { background: var(--red-light);    color: var(--red);    border: 1px solid var(--red-mid); }
  .badge-transfer { background: var(--blue-light);   color: var(--blue);   border: 1px solid var(--blue-mid); }
  .badge-ongoing  { background: var(--yellow-light); color: var(--yellow); border: 1px solid var(--yellow-mid); }
  .badge-vf       { background: var(--red-light);    color: var(--red);    border: 1px solid var(--red-mid); }
  .badge-vt       { background: var(--orange-light); color: var(--orange); border: 1px solid var(--orange-mid); }
  .badge-pea      { background: var(--yellow-light); color: var(--yellow); border: 1px solid var(--yellow-mid); }
  .badge-asy      { background: var(--purple-light); color: var(--purple); border: 1px solid var(--purple-mid); }
  .badge-oth      { background: var(--cyan-light);   color: var(--cyan);   border: 1px solid var(--cyan-mid); }
  .badge-yes      { background: var(--green-light);  color: var(--green);  border: 1px solid var(--green-mid); }
  .badge-no       { background: var(--red-light);    color: var(--red);    border: 1px solid var(--red-mid); }
  .badge-unknown  { background: #f1f5f9; color: var(--text-dim); border: 1px solid var(--border-strong); }

  .btn-del  { background: var(--red-light);  border: 1px solid var(--red-mid);  color: var(--red);  padding: 4px 10px; border-radius: 5px; cursor: pointer; font-size: 12px; font-weight: 600; transition: all 0.15s; font-family: var(--body); }
  .btn-del:hover  { background: var(--red-mid); }
  .btn-view { background: var(--blue-light); border: 1px solid var(--blue-mid); color: var(--blue); padding: 4px 10px; border-radius: 5px; cursor: pointer; font-size: 12px; font-weight: 600; margin-right: 5px; transition: all 0.15s; font-family: var(--body); }
  .btn-view:hover { background: var(--blue-mid); }

  .empty-state { padding: 52px; text-align: center; color: var(--text-dim); font-size: 13px; font-weight: 500; }
  .empty-state div { font-size: 36px; margin-bottom: 10px; opacity: 0.4; }

  /* TOAST */
  .toast {
    position: fixed; bottom: 24px; right: 24px;
    background: var(--surface); border: 1px solid var(--green-mid);
    border-left: 4px solid var(--green); border-radius: 8px;
    padding: 13px 18px; font-size: 13px; font-weight: 600; color: var(--green);
    box-shadow: var(--shadow-md); transform: translateY(70px); opacity: 0;
    transition: all 0.28s cubic-bezier(.4,0,.2,1); z-index: 999;
  }
  .toast.show { transform: translateY(0); opacity: 1; }

  /* MODAL */
  .modal-overlay { position: fixed; inset: 0; background: rgba(15,23,42,0.45); z-index: 200; display: none; align-items: center; justify-content: center; backdrop-filter: blur(3px); }
  .modal-overlay.open { display: flex; }
  .modal { background: var(--surface); border: 1px solid var(--border-strong); border-radius: 14px; padding: 28px 32px; width: 90%; max-width: 640px; max-height: 88vh; overflow-y: auto; position: relative; box-shadow: 0 20px 50px rgba(0,0,0,0.18); animation: modalIn 0.22s ease; }
  @keyframes modalIn { from{opacity:0;transform:scale(0.96)} to{opacity:1;transform:none} }
  .modal::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px; background: linear-gradient(90deg, var(--red), var(--blue)); border-radius: 14px 14px 0 0; }
  .modal-title { font-family: var(--head); font-size: 18px; letter-spacing: 2px; color: var(--text); margin-bottom: 20px; font-weight: 700; text-transform: uppercase; }
  .modal-row { display: flex; gap: 14px; margin-bottom: 12px; flex-wrap: wrap; }
  .modal-field { flex: 1; min-width: 150px; }
  .modal-field .lbl { font-size: 10px; font-weight: 700; color: var(--text-dim); letter-spacing: 1.5px; text-transform: uppercase; margin-bottom: 3px; }
  .modal-field .val { font-size: 14px; color: var(--text); font-weight: 600; }
  .modal-field .val.mono { font-family: var(--mono); font-size: 13px; color: var(--blue); }
  .modal-close { position: absolute; top: 16px; right: 18px; background: var(--surface2); border: 1px solid var(--border); color: var(--text-mid); font-size: 16px; width: 30px; height: 30px; border-radius: 6px; cursor: pointer; display: flex; align-items: center; justify-content: center; transition: all 0.15s; }
  .modal-close:hover { background: var(--red-light); color: var(--red); border-color: var(--red-mid); }
  .divider { height: 1px; background: var(--border); margin: 14px 0; }

  /* PRINT */
  @media print {
    .header, .form-card, .records-header .search-box, .btn-del, .btn-view, .alert-banner { display: none !important; }
    body { background: #fff; }
    .records-card { border: none; box-shadow: none; }
  }

  @media (max-width: 720px) {
    .form-grid, .form-grid.three { grid-template-columns: 1fr; }
    .main { padding: 14px 12px; }
    .form-card { padding: 18px 14px; }
    table { font-size: 12px; }
    th, td { padding: 9px 10px; }
    .live-clock { font-size: 14px; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<header class="header">
  <div class="header-inner">
    <div class="logo">
      <div class="logo-icon">🚨</div>
      <div class="logo-text">
        <h1>Code Blue</h1>
        <span>EMERGENCY RESPONSE RECORD SYSTEM</span>
      </div>
    </div>
    <div class="header-right">
      <div class="live-clock" id="liveClock">--:--:--</div>
      <div class="record-count-chip">RECORDS: <span id="recordCount">0</span></div>
    </div>
  </div>
</header>

<!-- MAIN -->
<main class="main">

  <div class="alert-banner">
    <span class="blink">⚠</span>
    <span>Code Blue Record System — Ministry of Health Malaysia</span>
  </div>

  <!-- FORM -->
  <div class="form-card">

    <!-- PATIENT INFO -->
    <div class="section-title">📋 Patient Information</div>
    <div class="form-grid">
      <div class="form-group">
        <label>Full Name *</label>
        <input type="text" id="patientName" placeholder="Patient full name" autocomplete="off">
      </div>
      <div class="form-group">
        <label>RN Number (Registration No.) *</label>
        <input type="text" id="rnNumber" placeholder="e.g. RN-2024-00001" autocomplete="off">
      </div>
      <div class="form-group">
        <label>IC No. / Passport</label>
        <input type="text" id="icNumber" placeholder="e.g. 900101-01-1234">
      </div>
      <div class="form-group">
        <label>Ward / Location</label>
        <input type="text" id="ward" placeholder="e.g. Ward 4B, ICU, A&amp;E">
      </div>
    </div>

    <!-- CODE ANNOUNCED -->
    <div class="section-title">📢 Code Announced</div>
    <div style="margin-bottom:22px">
      <div class="form-group">
        <label>Was Code Blue Announced? *</label>
        <div class="toggle-group" style="margin-top:4px">
          <button class="toggle-btn" id="announceYes" onclick="setAnnounce('yes')">✅ YES</button>
          <button class="toggle-btn" id="announceNo"  onclick="setAnnounce('no')">❌ NO</button>
        </div>
        <div class="announce-time-wrap" id="announceTimeWrap">
          <div style="display:flex;flex-direction:column;gap:5px">
            <label>Time of Announcement</label>
            <input type="time" id="announceTime" style="max-width:200px">
          </div>
        </div>
        <input type="hidden" id="announced" value="">
      </div>
    </div>

    <!-- DATE & TIME -->
    <div class="section-title">🕐 Date &amp; Time of Event</div>
    <div class="form-grid three">
      <div class="form-group">
        <label>Date of Event *</label>
        <input type="date" id="eventDate">
      </div>
      <div class="form-group">
        <label>CPR Start Time *</label>
        <input type="time" id="timeStart">
      </div>
      <div class="form-group">
        <label>CPR End Time</label>
        <input type="time" id="timeEnd">
      </div>
    </div>

    <!-- CLINICAL DETAILS -->
    <div class="section-title">⚕️ Clinical Details</div>
    <div style="margin-bottom:20px">
      <div class="form-group" style="margin-bottom:16px">
        <label>ECG Rhythm (Initial Rhythm) *</label>
        <div class="rhythm-group" id="rhythmGroup">
          <button class="rhythm-btn" data-val="VF"       onclick="setRhythm(this)">⚡ VF</button>
          <button class="rhythm-btn" data-val="VT"       onclick="setRhythm(this)">🌀 VT</button>
          <button class="rhythm-btn" data-val="PEA"      onclick="setRhythm(this)">〰️ PEA</button>
          <button class="rhythm-btn" data-val="Asystole" onclick="setRhythm(this)">▬ Asystole</button>
          <button class="rhythm-btn" data-val="Others"   onclick="setRhythm(this)">… Others</button>
        </div>
        <div class="rhythm-others-input" id="rhythmOthersWrap">
          <input type="text" id="rhythmOthers" placeholder="Specify other rhythm..." style="max-width:320px">
        </div>
        <input type="hidden" id="rhythm" value="">
      </div>
      <div class="form-grid" style="margin-bottom:0">
        <div class="form-group">
          <label>Suspected Cause</label>
          <select id="cause">
            <option value="">-- Select --</option>
            <option>Cardiac Arrest</option>
            <option>Respiratory Arrest</option>
            <option>Anaphylaxis</option>
            <option>Sepsis</option>
            <option>Trauma</option>
            <option>Drowning</option>
            <option>Unknown</option>
            <option>Others</option>
          </select>
        </div>
      </div>
    </div>

    <!-- INTERVENTIONS -->
    <div class="section-title">🩺 Interventions Performed</div>
    <div class="form-group" style="margin-bottom:20px">
      <label>General Interventions</label>
      <div class="checklist-grid" id="interventionList">
        <label class="check-item"><input type="checkbox" value="CPR"><label>CPR</label></label>
        <label class="check-item"><input type="checkbox" value="Defibrillation"><label>Defibrillation</label></label>
        <label class="check-item"><input type="checkbox" value="ETT Intubation"><label>ETT Intubation</label></label>
        <label class="check-item"><input type="checkbox" value="IV Access"><label>IV Access</label></label>
      </div>
    </div>

    <!-- IV MEDICATIONS -->
    <div class="form-group" style="margin-bottom:20px">
      <label>IV Medications Given</label>
      <div class="iv-med-grid" id="ivMedGrid">

        <!-- Adrenaline -->
        <div class="iv-med-card" id="card-adrenaline">
          <div class="iv-med-header" onclick="toggleMed('adrenaline')">
            <input type="checkbox" id="chk-adrenaline" onclick="event.stopPropagation();toggleMed('adrenaline',this.checked)">
            <span class="iv-med-name">Adrenaline</span>
            <span class="iv-med-badge">1mg IV</span>
          </div>
          <div class="iv-med-body" id="body-adrenaline">
            <div class="dose-times-list" id="times-adrenaline"></div>
            <div class="add-dose-row">
              <input type="time" class="iv-time-input" id="time-adrenaline">
              <button class="btn-stat" onclick="statNow('adrenaline')"><span class="stat-dot"></span>STAT</button>
              <button class="btn-add-dose" onclick="addDose('adrenaline')">+ Add Dose</button>
            </div>
          </div>
        </div>

        <!-- Amiodarone -->
        <div class="iv-med-card" id="card-amiodarone">
          <div class="iv-med-header" onclick="toggleMed('amiodarone')">
            <input type="checkbox" id="chk-amiodarone" onclick="event.stopPropagation();toggleMed('amiodarone',this.checked)">
            <span class="iv-med-name">Amiodarone</span>
            <span class="iv-med-badge">300mg IV</span>
          </div>
          <div class="iv-med-body" id="body-amiodarone">
            <div class="dose-times-list" id="times-amiodarone"></div>
            <div class="add-dose-row">
              <input type="time" class="iv-time-input" id="time-amiodarone">
              <button class="btn-stat" onclick="statNow('amiodarone')"><span class="stat-dot"></span>STAT</button>
              <button class="btn-add-dose" onclick="addDose('amiodarone')">+ Add Dose</button>
            </div>
          </div>
        </div>

        <!-- Atropine -->
        <div class="iv-med-card" id="card-atropine">
          <div class="iv-med-header" onclick="toggleMed('atropine')">
            <input type="checkbox" id="chk-atropine" onclick="event.stopPropagation();toggleMed('atropine',this.checked)">
            <span class="iv-med-name">Atropine</span>
            <span class="iv-med-badge">1mg IV</span>
          </div>
          <div class="iv-med-body" id="body-atropine">
            <div class="dose-times-list" id="times-atropine"></div>
            <div class="add-dose-row">
              <input type="time" class="iv-time-input" id="time-atropine">
              <button class="btn-stat" onclick="statNow('atropine')"><span class="stat-dot"></span>STAT</button>
              <button class="btn-add-dose" onclick="addDose('atropine')">+ Add Dose</button>
            </div>
          </div>
        </div>

        <!-- Sodium Bicarbonate -->
        <div class="iv-med-card" id="card-nahco3">
          <div class="iv-med-header" onclick="toggleMed('nahco3')">
            <input type="checkbox" id="chk-nahco3" onclick="event.stopPropagation();toggleMed('nahco3',this.checked)">
            <span class="iv-med-name">Sodium Bicarbonate</span>
            <span class="iv-med-badge">50mmol IV</span>
          </div>
          <div class="iv-med-body" id="body-nahco3">
            <div class="dose-times-list" id="times-nahco3"></div>
            <div class="add-dose-row">
              <input type="time" class="iv-time-input" id="time-nahco3">
              <button class="btn-stat" onclick="statNow('nahco3')"><span class="stat-dot"></span>STAT</button>
              <button class="btn-add-dose" onclick="addDose('nahco3')">+ Add Dose</button>
            </div>
          </div>
        </div>

        <!-- Calcium Gluconate -->
        <div class="iv-med-card" id="card-calcium">
          <div class="iv-med-header" onclick="toggleMed('calcium')">
            <input type="checkbox" id="chk-calcium" onclick="event.stopPropagation();toggleMed('calcium',this.checked)">
            <span class="iv-med-name">Calcium Gluconate</span>
            <span class="iv-med-badge">10ml IV</span>
          </div>
          <div class="iv-med-body" id="body-calcium">
            <div class="dose-times-list" id="times-calcium"></div>
            <div class="add-dose-row">
              <input type="time" class="iv-time-input" id="time-calcium">
              <button class="btn-stat" onclick="statNow('calcium')"><span class="stat-dot"></span>STAT</button>
              <button class="btn-add-dose" onclick="addDose('calcium')">+ Add Dose</button>
            </div>
          </div>
        </div>

        <!-- Magnesium Sulphate -->
        <div class="iv-med-card" id="card-mgso4">
          <div class="iv-med-header" onclick="toggleMed('mgso4')">
            <input type="checkbox" id="chk-mgso4" onclick="event.stopPropagation();toggleMed('mgso4',this.checked)">
            <span class="iv-med-name">Magnesium Sulphate</span>
            <span class="iv-med-badge">2g IV</span>
          </div>
          <div class="iv-med-body" id="body-mgso4">
            <div class="dose-times-list" id="times-mgso4"></div>
            <div class="add-dose-row">
              <input type="time" class="iv-time-input" id="time-mgso4">
              <button class="btn-stat" onclick="statNow('mgso4')"><span class="stat-dot"></span>STAT</button>
              <button class="btn-add-dose" onclick="addDose('mgso4')">+ Add Dose</button>
            </div>
          </div>
        </div>

        <!-- Others -->
        <div class="iv-med-card" id="card-ivothers">
          <div class="iv-med-header" onclick="toggleMed('ivothers')">
            <input type="checkbox" id="chk-ivothers" onclick="event.stopPropagation();toggleMed('ivothers',this.checked)">
            <span class="iv-med-name">Others</span>
            <span class="iv-med-badge" style="background:var(--cyan-light);color:var(--cyan);border-color:var(--cyan-mid)">IV</span>
          </div>
          <div class="iv-med-body" id="body-ivothers">
            <div style="margin-top:6px;margin-bottom:4px">
              <input type="text" id="ivothers-name" placeholder="Medication name..." style="font-size:12px;padding:6px 9px;width:100%">
            </div>
            <div class="dose-times-list" id="times-ivothers"></div>
            <div class="add-dose-row">
              <input type="time" class="iv-time-input" id="time-ivothers">
              <button class="btn-stat" onclick="statNow('ivothers')"><span class="stat-dot"></span>STAT</button>
              <button class="btn-add-dose" onclick="addDose('ivothers')">+ Add Dose</button>
            </div>
          </div>
        </div>

      </div>
    </div>

    <!-- OUTCOME -->
    <div class="section-title">🏥 Patient Outcome</div>
    <div class="form-group" style="margin-bottom:20px">
      <label>Outcome *</label>
      <div class="outcome-group" id="outcomeGroup">
        <button class="outcome-btn" data-val="ROSC"     onclick="setOutcome(this)">✅ ROSC</button>
        <button class="outcome-btn" data-val="Deceased" onclick="setOutcome(this)">🔴 Deceased</button>
        <button class="outcome-btn" data-val="Transfer" onclick="setOutcome(this)">🔵 Transfer</button>
        <button class="outcome-btn" data-val="Ongoing"  onclick="setOutcome(this)">🟡 Ongoing</button>
      </div>
      <input type="hidden" id="outcome" value="">
    </div>

    <div class="form-grid">
      <div class="form-group">
        <label>Responsible Officer</label>
        <input type="text" id="officer" placeholder="Doctor / MO / Senior Nurse name">
      </div>
      <div class="form-group">
        <label>Additional Notes</label>
        <textarea id="notes" placeholder="Any additional notes about this event..."></textarea>
      </div>
    </div>

    <div class="action-row">
      <button class="btn btn-clear" onclick="clearForm()">↺ Clear Form</button>
      <button class="btn btn-print" onclick="window.print()">🖨 Print</button>
      <button class="btn btn-save"  onclick="saveRecord()">💾 Save Record</button>
    </div>
  </div>

  <!-- RECORDS TABLE -->
  <div class="records-card">
    <div class="records-header">
      <h2>📁 Code Blue Records</h2>
      <input class="search-box" type="text" placeholder="🔍 Search name / RN / ward..." oninput="filterRecords(this.value)">
    </div>
    <div id="tableWrap">
      <div class="empty-state"><div>📋</div>No records yet. Save your first record above.</div>
    </div>
  </div>

</main>

<!-- TOAST -->
<div class="toast" id="toast">✔ Record saved successfully</div>

<!-- MODAL -->
<div class="modal-overlay" id="modalOverlay" onclick="closeModal(event)">
  <div class="modal" id="modalBox">
    <button class="modal-close" onclick="document.getElementById('modalOverlay').classList.remove('open')">✕</button>
    <div id="modalContent"></div>
  </div>
</div>

<script>
  let records = JSON.parse(localStorage.getItem('codeBlueRecords') || '[]');
  let filteredRecords = [...records];
  let selectedOutcome = '', selectedAnnounce = '', selectedRhythm = '';

  // IV medication state: { medKey: [time1, time2, ...] }
  const ivMeds = {
    adrenaline: [], amiodarone: [], atropine: [],
    nahco3: [], calcium: [], mgso4: [], ivothers: []
  };
  const ivMedLabels = {
    adrenaline:'Adrenaline (1mg IV)', amiodarone:'Amiodarone (300mg IV)',
    atropine:'Atropine (1mg IV)', nahco3:'Sodium Bicarbonate (50mmol IV)',
    calcium:'Calcium Gluconate (10ml IV)', mgso4:'Magnesium Sulphate (2g IV)',
    ivothers:'Others (IV)'
  };

  function updateClock() {
    document.getElementById('liveClock').textContent =
      new Date().toLocaleTimeString('en-MY', {hour12:false});
  }
  setInterval(updateClock, 1000); updateClock();

  (function() {
    const now = new Date();
    document.getElementById('eventDate').value = now.toISOString().slice(0,10);
    document.getElementById('timeStart').value = now.toTimeString().slice(0,5);
  })();

  // ── Code Announced ──
  function setAnnounce(val) {
    selectedAnnounce = val;
    document.getElementById('announced').value = val;
    document.getElementById('announceYes').className = 'toggle-btn' + (val==='yes' ? ' active-yes' : '');
    document.getElementById('announceNo').className  = 'toggle-btn' + (val==='no'  ? ' active-no'  : '');
    const wrap = document.getElementById('announceTimeWrap');
    if (val === 'yes') wrap.classList.add('visible');
    else { wrap.classList.remove('visible'); document.getElementById('announceTime').value = ''; }
  }

  // ── ECG Rhythm ──
  function setRhythm(btn) {
    document.querySelectorAll('.rhythm-btn').forEach(b => b.className = 'rhythm-btn');
    const val = btn.getAttribute('data-val');
    const cls = {VF:'active-vf', VT:'active-vt', PEA:'active-pea', Asystole:'active-asy', Others:'active-oth'};
    btn.classList.add(cls[val] || '');
    selectedRhythm = val;
    document.getElementById('rhythm').value = val;
    const othWrap = document.getElementById('rhythmOthersWrap');
    if (val === 'Others') othWrap.classList.add('visible');
    else { othWrap.classList.remove('visible'); document.getElementById('rhythmOthers').value = ''; }
  }

  // ── Outcome ──
  function setOutcome(btn) {
    document.querySelectorAll('.outcome-btn').forEach(b => b.className = 'outcome-btn');
    const val = btn.getAttribute('data-val');
    const cls = {ROSC:'active-rosc',Deceased:'active-deceased',Transfer:'active-transfer',Ongoing:'active-ongoing'};
    btn.classList.add(cls[val] || '');
    selectedOutcome = val;
    document.getElementById('outcome').value = val;
  }

  // ── IV Medication ──
  function toggleMed(key, checked) {
    const card = document.getElementById('card-'+key);
    const chk  = document.getElementById('chk-'+key);
    const body = document.getElementById('body-'+key);
    const isOn = (checked !== undefined) ? checked : !chk.checked;
    chk.checked = isOn;
    if (isOn) {
      card.classList.add('selected');
      body.classList.add('visible');
    } else {
      card.classList.remove('selected');
      body.classList.remove('visible');
      ivMeds[key] = [];
      renderDoseTimes(key);
      document.getElementById('time-'+key).value = '';
    }
  }

  function statNow(key) {
    const now = new Date().toTimeString().slice(0,5);
    document.getElementById('time-'+key).value = now;
    addDose(key);
  }

  function addDose(key) {
    const timeEl = document.getElementById('time-'+key);
    const t = timeEl.value;
    if (!t) { timeEl.focus(); return; }
    ivMeds[key].push(t);
    timeEl.value = '';
    renderDoseTimes(key);
  }

  function removeDose(key, idx) {
    ivMeds[key].splice(idx, 1);
    renderDoseTimes(key);
  }

  function renderDoseTimes(key) {
    const list = document.getElementById('times-'+key);
    list.innerHTML = ivMeds[key].map((t,i) =>
      `<span class="dose-time-chip">
        💉 ${t}
        <span class="rm" onclick="removeDose('${key}',${i})">✕</span>
      </span>`
    ).join('');
  }

  function getIVMedsData() {
    const result = [];
    Object.keys(ivMeds).forEach(key => {
      const chk = document.getElementById('chk-'+key);
      if (chk && chk.checked && ivMeds[key].length > 0) {
        let label = ivMedLabels[key];
        if (key === 'ivothers') {
          const n = document.getElementById('ivothers-name').value.trim();
          if (n) label = n + ' (IV)';
        }
        result.push({ med: label, times: [...ivMeds[key]] });
      } else if (chk && chk.checked) {
        let label = ivMedLabels[key];
        if (key === 'ivothers') {
          const n = document.getElementById('ivothers-name').value.trim();
          if (n) label = n + ' (IV)';
        }
        result.push({ med: label, times: [] });
      }
    });
    return result;
  }

  function getInterventions() {
    return [...document.querySelectorAll('#interventionList input:checked')].map(c => c.value);
  }

  function getRhythmDisplay() {
    if (selectedRhythm === 'Others') {
      const oth = document.getElementById('rhythmOthers').value.trim();
      return oth ? 'Others: ' + oth : 'Others';
    }
    const labels = {
      VF:'VF (Ventricular Fibrillation)', VT:'VT (Ventricular Tachycardia)',
      PEA:'PEA (Pulseless Electrical Activity)', Asystole:'Asystole'
    };
    return labels[selectedRhythm] || selectedRhythm || '';
  }

  // ── Save ──
  function saveRecord() {
    const name = document.getElementById('patientName').value.trim();
    const rn   = document.getElementById('rnNumber').value.trim();
    const date = document.getElementById('eventDate').value;
    const timeStart = document.getElementById('timeStart').value;
    if (!name || !rn || !date || !timeStart) {
      showToast('⚠ Please fill required fields: Name, RN, Date & Start Time', '#92400e', '#fffbeb', '#fde68a');
      return;
    }
    const record = {
      id: Date.now(), name, rn,
      ic:   document.getElementById('icNumber').value.trim(),
      ward: document.getElementById('ward').value.trim(),
      announced:    selectedAnnounce,
      announceTime: selectedAnnounce === 'yes' ? document.getElementById('announceTime').value : '',
      date, timeStart,
      timeEnd:  document.getElementById('timeEnd').value,
      rhythm:   selectedRhythm,
      rhythmDisplay: getRhythmDisplay(),
      cause:    document.getElementById('cause').value,
      interventions: getInterventions(),
      ivMedications: getIVMedsData(),
      outcome:  selectedOutcome,
      officer:  document.getElementById('officer').value.trim(),
      notes:    document.getElementById('notes').value.trim(),
      savedAt:  new Date().toLocaleString('en-MY')
    };
    records.unshift(record);
    localStorage.setItem('codeBlueRecords', JSON.stringify(records));
    filteredRecords = [...records];
    renderTable(filteredRecords);
    showToast('✔ Record saved successfully');
    clearForm();
  }

  // ── Clear ──
  function clearForm() {
    ['patientName','rnNumber','icNumber','ward','timeEnd','cause','officer','notes','rhythmOthers','announceTime']
      .forEach(id => { const el = document.getElementById(id); if (el) el.value = ''; });
    const now = new Date();
    document.getElementById('eventDate').value = now.toISOString().slice(0,10);
    document.getElementById('timeStart').value = now.toTimeString().slice(0,5);
    document.querySelectorAll('#interventionList input').forEach(c => c.checked = false);
    document.querySelectorAll('.outcome-btn').forEach(b => b.className = 'outcome-btn');
    document.querySelectorAll('.rhythm-btn').forEach(b => b.className = 'rhythm-btn');
    document.getElementById('announceYes').className = 'toggle-btn';
    document.getElementById('announceNo').className  = 'toggle-btn';
    document.getElementById('announceTimeWrap').classList.remove('visible');
    document.getElementById('rhythmOthersWrap').classList.remove('visible');
    ['rhythm','outcome','announced'].forEach(id => document.getElementById(id).value = '');
    selectedOutcome = ''; selectedAnnounce = ''; selectedRhythm = '';
    // Clear IV meds
    Object.keys(ivMeds).forEach(key => {
      ivMeds[key] = [];
      toggleMed(key, false);
      renderDoseTimes(key);
    });
    const othName = document.getElementById('ivothers-name');
    if (othName) othName.value = '';
  }

  // ── Delete ──
  function deleteRecord(id) {
    if (!confirm('Delete this record?')) return;
    records = records.filter(r => r.id !== id);
    localStorage.setItem('codeBlueRecords', JSON.stringify(records));
    filteredRecords = [...records];
    renderTable(filteredRecords);
    showToast('🗑 Record deleted', '#d62839', '#fff0f1', '#ffd6da');
  }

  function filterRecords(q) {
    const lower = q.toLowerCase();
    filteredRecords = records.filter(r =>
      r.name.toLowerCase().includes(lower) ||
      r.rn.toLowerCase().includes(lower) ||
      (r.ward||'').toLowerCase().includes(lower)
    );
    renderTable(filteredRecords);
  }

  // ── Badges ──
  function outcomeBadge(outcome) {
    const map = { ROSC:['badge-rosc','✅ ROSC'], Deceased:['badge-deceased','🔴 Deceased'], Transfer:['badge-transfer','🔵 Transfer'], Ongoing:['badge-ongoing','🟡 Ongoing'] };
    const [cls, label] = map[outcome] || ['badge-unknown','—'];
    return `<span class="badge ${cls}">${label}</span>`;
  }
  function announceBadge(announced, announceTime) {
    if (announced === 'yes') return `<span class="badge badge-yes">✅ YES${announceTime ? ' · '+announceTime : ''}</span>`;
    if (announced === 'no')  return `<span class="badge badge-no">❌ NO</span>`;
    return '<span style="color:var(--text-dim)">—</span>';
  }
  function rhythmBadge(r) {
    if (!r.rhythm) return '<span style="color:var(--text-dim)">—</span>';
    const cls = {VF:'badge-vf', VT:'badge-vt', PEA:'badge-pea', Asystole:'badge-asy', Others:'badge-oth'};
    return `<span class="badge ${cls[r.rhythm]||'badge-unknown'}">${r.rhythm}</span>`;
  }

  function ivMedsHTML(ivMedications) {
    if (!ivMedications || !ivMedications.length) return '<span style="color:var(--text-dim)">—</span>';
    return ivMedications.map(m =>
      `<div style="margin-bottom:6px">
        <span class="badge" style="background:var(--purple-light);color:var(--purple);border:1px solid var(--purple-mid)">${m.med}</span>
        ${m.times && m.times.length ? m.times.map(t=>`<span class="badge" style="background:var(--blue-light);color:var(--blue);border:1px solid var(--blue-mid);margin-left:4px">💉 ${t}</span>`).join('') : '<span style="font-size:11px;color:var(--text-dim);margin-left:6px">no time recorded</span>'}
      </div>`
    ).join('');
  }

  // ── Table ──
  function renderTable(data) {
    document.getElementById('recordCount').textContent = records.length;
    const wrap = document.getElementById('tableWrap');
    if (!data.length) {
      wrap.innerHTML = '<div class="empty-state"><div>📋</div>No records found.</div>';
      return;
    }
    wrap.innerHTML = `<div style="overflow-x:auto"><table>
      <thead><tr>
        <th>#</th><th>Patient Name</th><th>RN Number</th><th>Date</th>
        <th>CPR Time</th><th>Code Announced</th><th>ECG Rhythm</th><th>Outcome</th><th>Actions</th>
      </tr></thead>
      <tbody>${data.map((r,i)=>`
        <tr>
          <td class="mono">${data.length-i}</td>
          <td class="name">${r.name}</td>
          <td class="mono">${r.rn}</td>
          <td class="mono">${r.date}</td>
          <td class="mono">${r.timeStart}${r.timeEnd?' – '+r.timeEnd:''}</td>
          <td>${announceBadge(r.announced,r.announceTime)}</td>
          <td>${rhythmBadge(r)}</td>
          <td>${outcomeBadge(r.outcome)}</td>
          <td>
            <button class="btn-view" onclick="viewRecord(${r.id})">View</button>
            <button class="btn-del"  onclick="deleteRecord(${r.id})">Delete</button>
          </td>
        </tr>`).join('')}
      </tbody>
    </table></div>`;
  }

  // ── View Modal ──
  function viewRecord(id) {
    const r = records.find(x => x.id === id);
    if (!r) return;
    document.getElementById('modalContent').innerHTML = `
      <div class="modal-title">🚨 Code Blue Record Detail</div>
      <div class="modal-row">
        <div class="modal-field"><div class="lbl">Patient Name</div><div class="val">${r.name}</div></div>
        <div class="modal-field"><div class="lbl">RN Number</div><div class="val mono">${r.rn}</div></div>
      </div>
      <div class="modal-row">
        <div class="modal-field"><div class="lbl">IC No. / Passport</div><div class="val mono">${r.ic||'—'}</div></div>
        <div class="modal-field"><div class="lbl">Ward / Location</div><div class="val">${r.ward||'—'}</div></div>
      </div>
      <div class="divider"></div>
      <div class="modal-row">
        <div class="modal-field"><div class="lbl">Code Announced</div><div class="val">${announceBadge(r.announced, r.announceTime)}</div></div>
        ${r.announced==='yes'?`<div class="modal-field"><div class="lbl">Time Announced</div><div class="val mono">${r.announceTime||'—'}</div></div>`:''}
      </div>
      <div class="divider"></div>
      <div class="modal-row">
        <div class="modal-field"><div class="lbl">Date</div><div class="val mono">${r.date}</div></div>
        <div class="modal-field"><div class="lbl">CPR Start</div><div class="val mono">${r.timeStart}</div></div>
        <div class="modal-field"><div class="lbl">CPR End</div><div class="val mono">${r.timeEnd||'—'}</div></div>
      </div>
      <div class="divider"></div>
      <div class="modal-row">
        <div class="modal-field"><div class="lbl">ECG Rhythm</div><div class="val">${rhythmBadge(r)} <span style="font-size:12px;color:var(--text-mid);font-weight:400">${r.rhythmDisplay||''}</span></div></div>
        <div class="modal-field"><div class="lbl">Suspected Cause</div><div class="val">${r.cause||'—'}</div></div>
      </div>
      <div class="modal-row">
        <div class="modal-field" style="flex:2"><div class="lbl">General Interventions</div><div class="val" style="font-weight:500">${r.interventions&&r.interventions.length?r.interventions.join(', '):'—'}</div></div>
      </div>
      <div class="divider"></div>
      <div class="modal-row">
        <div class="modal-field" style="flex:2">
          <div class="lbl">💉 IV Medications Given</div>
          <div style="margin-top:6px">${ivMedsHTML(r.ivMedications)}</div>
        </div>
      </div>
      <div class="divider"></div>
      <div class="modal-row">
        <div class="modal-field"><div class="lbl">Outcome</div><div class="val">${outcomeBadge(r.outcome)}</div></div>
        <div class="modal-field"><div class="lbl">Responsible Officer</div><div class="val">${r.officer||'—'}</div></div>
      </div>
      ${r.notes?`<div class="divider"></div><div class="modal-field"><div class="lbl">Notes</div><div class="val" style="font-weight:400;color:var(--text-mid)">${r.notes}</div></div>`:''}
      <div class="divider"></div>
      <div style="font-family:var(--mono);font-size:11px;color:var(--text-dim)">Saved: ${r.savedAt}</div>
    `;
    document.getElementById('modalOverlay').classList.add('open');
  }

  function closeModal(e) {
    if (e.target === document.getElementById('modalOverlay'))
      document.getElementById('modalOverlay').classList.remove('open');
  }

  function showToast(msg, color='#057a55', bg='#ecfdf5', border='#a7f3d0') {
    const t = document.getElementById('toast');
    t.textContent = msg; t.style.color = color;
    t.style.borderLeftColor = color; t.style.borderColor = border;
    t.classList.add('show');
    setTimeout(() => t.classList.remove('show'), 3000);
  }

  renderTable(records);
</script>
</body>
</html>
