<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>সাইকেল বাজার 🚲</title>
<link href="https://fonts.googleapis.com/css2?family=Hind+Siliguri:wght@300;400;500;600;700&family=Noto+Sans+Bengali:wght@400;600;700;900&display=swap" rel="stylesheet">
<style>
  :root {
    --primary: #1a6b3c;
    --primary-light: #2d9e5c;
    --primary-dark: #0f4024;
    --accent: #f5a623;
    --accent-dark: #e09010;
    --bg: #f0f4f0;
    --card: #ffffff;
    --text: #1a2e1a;
    --text-muted: #5a7a5a;
    --border: #c8dbc8;
    --danger: #e53935;
    --success: #2e7d32;
    --shadow: 0 4px 20px rgba(26,107,60,0.12);
    --shadow-hover: 0 8px 32px rgba(26,107,60,0.22);
    --radius: 16px;
    --radius-sm: 10px;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body {
    font-family: 'Hind Siliguri', 'Noto Sans Bengali', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
  }
  /* HEADER */
  header {
    background: linear-gradient(135deg, var(--primary-dark) 0%, var(--primary) 60%, var(--primary-light) 100%);
    color: white;
    padding: 0 20px;
    position: sticky; top: 0; z-index: 100;
    box-shadow: 0 2px 16px rgba(0,0,0,0.25);
  }
  .header-inner {
    max-width: 1100px; margin: 0 auto;
    display: flex; align-items: center; justify-content: space-between;
    height: 64px; gap: 12px;
  }
  .logo { font-size: 1.5rem; font-weight: 700; letter-spacing: -0.5px; display: flex; align-items: center; gap: 8px; }
  .logo span { font-size: 1.6rem; }
  nav { display: flex; gap: 6px; align-items: center; flex-wrap: wrap; }
  nav button {
    background: rgba(255,255,255,0.15); border: 1.5px solid rgba(255,255,255,0.3);
    color: white; padding: 7px 14px; border-radius: 25px; cursor: pointer;
    font-family: inherit; font-size: 0.85rem; font-weight: 500;
    transition: all 0.2s; white-space: nowrap;
  }
  nav button:hover, nav button.active { background: white; color: var(--primary); border-color: white; }
  nav button.accent { background: var(--accent); border-color: var(--accent-dark); color: #1a2e1a; }
  nav button.accent:hover { background: var(--accent-dark); }
  /* PAGES */
  .page { display: none; }
  .page.active { display: block; }
  .container { max-width: 1100px; margin: 0 auto; padding: 24px 16px; }
  /* HERO */
  .hero {
    background: linear-gradient(135deg, var(--primary) 0%, var(--primary-light) 100%);
    color: white; text-align: center; padding: 56px 20px 48px;
  }
  .hero h1 { font-size: 2.4rem; font-weight: 900; margin-bottom: 12px; text-shadow: 0 2px 8px rgba(0,0,0,0.2); }
  .hero p { font-size: 1.1rem; opacity: 0.9; margin-bottom: 28px; }
  .hero-btns { display: flex; gap: 12px; justify-content: center; flex-wrap: wrap; }
  .btn {
    padding: 12px 28px; border-radius: 30px; border: none; cursor: pointer;
    font-family: inherit; font-size: 1rem; font-weight: 600; transition: all 0.2s;
  }
  .btn-white { background: white; color: var(--primary); }
  .btn-white:hover { transform: translateY(-2px); box-shadow: 0 6px 20px rgba(0,0,0,0.2); }
  .btn-outline { background: transparent; color: white; border: 2px solid white; }
  .btn-outline:hover { background: white; color: var(--primary); }
  /* STATS BAR */
  .stats-bar {
    background: white; border-bottom: 2px solid var(--border);
    padding: 14px 20px;
  }
  .stats-inner {
    max-width: 1100px; margin: 0 auto;
    display: flex; gap: 24px; justify-content: center; flex-wrap: wrap;
  }
  .stat-item { text-align: center; }
  .stat-num { font-size: 1.4rem; font-weight: 700; color: var(--primary); }
  .stat-label { font-size: 0.75rem; color: var(--text-muted); }
  /* FILTERS */
  .filters {
    background: white; border-radius: var(--radius); padding: 18px 20px;
    margin-bottom: 20px; box-shadow: var(--shadow);
    display: flex; gap: 12px; align-items: center; flex-wrap: wrap;
  }
  .filters select, .filters input {
    padding: 9px 14px; border: 1.5px solid var(--border); border-radius: 25px;
    font-family: inherit; font-size: 0.9rem; background: var(--bg);
    outline: none; color: var(--text);
  }
  .filters select:focus, .filters input:focus { border-color: var(--primary); }
  .filter-label { font-weight: 600; color: var(--text-muted); font-size: 0.85rem; }
  /* AD GRID */
  .ads-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
  }
  .ad-card {
    background: white; border-radius: var(--radius); overflow: hidden;
    box-shadow: var(--shadow); transition: all 0.25s; border: 1.5px solid transparent;
    cursor: pointer;
  }
  .ad-card:hover { transform: translateY(-4px); box-shadow: var(--shadow-hover); border-color: var(--primary-light); }
  .ad-img {
    width: 100%; height: 200px; object-fit: cover;
    background: linear-gradient(135deg, #e8f5e9, #c8e6c9);
    display: flex; align-items: center; justify-content: center;
    font-size: 4rem; color: var(--primary-light);
  }
  .ad-img img { width: 100%; height: 100%; object-fit: cover; }
  .ad-body { padding: 16px; }
  .ad-title { font-size: 1.05rem; font-weight: 700; margin-bottom: 6px; color: var(--text); }
  .ad-price { font-size: 1.3rem; font-weight: 800; color: var(--primary); margin-bottom: 8px; }
  .ad-tags { display: flex; gap: 6px; flex-wrap: wrap; margin-bottom: 10px; }
  .tag {
    background: #e8f5e9; color: var(--primary); padding: 3px 10px;
    border-radius: 15px; font-size: 0.75rem; font-weight: 600;
  }
  .tag.condition-new { background: #e3f2fd; color: #1565c0; }
  .tag.condition-used { background: #fff3e0; color: #e65100; }
  .ad-meta { display: flex; justify-content: space-between; align-items: center; }
  .ad-seller { font-size: 0.82rem; color: var(--text-muted); }
  .ad-date { font-size: 0.78rem; color: var(--text-muted); }
  .ad-actions { display: flex; gap: 8px; margin-top: 12px; padding-top: 12px; border-top: 1px solid var(--border); }
  .ad-btn {
    flex: 1; padding: 9px; border-radius: 10px; border: none; cursor: pointer;
    font-family: inherit; font-size: 0.85rem; font-weight: 600; transition: all 0.2s;
  }
  .ad-btn-msg { background: var(--primary); color: white; }
  .ad-btn-msg:hover { background: var(--primary-dark); }
  .ad-btn-fav { background: var(--bg); color: var(--text-muted); border: 1.5px solid var(--border); }
  .ad-btn-fav:hover { background: #ffe0e0; color: #e53935; border-color: #e53935; }
  .badge-sold { position: absolute; top: 12px; right: 12px; background: var(--danger); color: white; padding: 4px 10px; border-radius: 8px; font-size: 0.8rem; font-weight: 700; }
  .badge-featured { position: absolute; top: 12px; left: 12px; background: var(--accent); color: #1a2e1a; padding: 4px 10px; border-radius: 8px; font-size: 0.8rem; font-weight: 700; }
  .ad-card-wrap { position: relative; }
  /* EMPTY STATE */
  .empty-state { text-align: center; padding: 60px 20px; color: var(--text-muted); }
  .empty-state .icon { font-size: 4rem; margin-bottom: 16px; }
  .empty-state h3 { font-size: 1.2rem; margin-bottom: 8px; }
  /* MODAL */
  .modal-overlay {
    display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.6);
    z-index: 1000; align-items: center; justify-content: center; padding: 16px;
    backdrop-filter: blur(3px);
  }
  .modal-overlay.active { display: flex; }
  .modal {
    background: white; border-radius: var(--radius); max-width: 560px; width: 100%;
    max-height: 90vh; overflow-y: auto; box-shadow: 0 20px 60px rgba(0,0,0,0.3);
  }
  .modal-header {
    padding: 20px 24px 16px; border-bottom: 1.5px solid var(--border);
    display: flex; justify-content: space-between; align-items: center;
    position: sticky; top: 0; background: white; z-index: 1;
  }
  .modal-header h2 { font-size: 1.2rem; font-weight: 700; }
  .modal-close { background: none; border: none; font-size: 1.5rem; cursor: pointer; color: var(--text-muted); transition: color 0.2s; }
  .modal-close:hover { color: var(--danger); }
  .modal-body { padding: 24px; }
  /* FORM */
  .form-group { margin-bottom: 18px; }
  .form-label { display: block; margin-bottom: 6px; font-weight: 600; font-size: 0.9rem; color: var(--text); }
  .form-input, .form-select, .form-textarea {
    width: 100%; padding: 11px 14px; border: 1.5px solid var(--border);
    border-radius: var(--radius-sm); font-family: inherit; font-size: 0.95rem;
    background: white; outline: none; transition: border-color 0.2s; color: var(--text);
  }
  .form-input:focus, .form-select:focus, .form-textarea:focus { border-color: var(--primary); }
  .form-textarea { resize: vertical; min-height: 90px; }
  .form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
  .submit-btn {
    width: 100%; padding: 13px; background: var(--primary); color: white;
    border: none; border-radius: var(--radius-sm); font-family: inherit;
    font-size: 1rem; font-weight: 700; cursor: pointer; transition: all 0.2s;
  }
  .submit-btn:hover { background: var(--primary-dark); transform: translateY(-1px); }
  /* IMAGE PREVIEW */
  .img-preview-wrap { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 8px; }
  .img-preview { width: 80px; height: 80px; object-fit: cover; border-radius: 8px; border: 2px solid var(--border); }
  /* LOGIN */
  .login-wrap {
    min-height: 100vh; display: flex; align-items: center; justify-content: center;
    background: linear-gradient(135deg, var(--primary-dark), var(--primary-light));
    padding: 20px;
  }
  .login-card {
    background: white; border-radius: 20px; padding: 40px 36px;
    width: 100%; max-width: 420px; box-shadow: 0 20px 60px rgba(0,0,0,0.3);
    text-align: center;
  }
  .login-card .logo-big { font-size: 2.5rem; margin-bottom: 8px; }
  .login-card h2 { font-size: 1.6rem; font-weight: 800; color: var(--primary); margin-bottom: 6px; }
  .login-card p { color: var(--text-muted); margin-bottom: 28px; font-size: 0.9rem; }
  /* MESSAGES PAGE */
  .msg-layout {
    display: grid; grid-template-columns: 320px 1fr; gap: 20px;
    height: calc(100vh - 130px); min-height: 500px;
  }
  .msg-list {
    background: white; border-radius: var(--radius); overflow-y: auto;
    box-shadow: var(--shadow); border: 1.5px solid var(--border);
  }
  .msg-list-header { padding: 16px 18px; border-bottom: 1.5px solid var(--border); font-weight: 700; font-size: 1rem; }
  .conv-item {
    padding: 14px 18px; border-bottom: 1px solid var(--border); cursor: pointer;
    transition: background 0.15s; display: flex; gap: 12px; align-items: center;
  }
  .conv-item:hover, .conv-item.active { background: #e8f5e9; }
  .conv-avatar {
    width: 44px; height: 44px; border-radius: 50%; background: var(--primary);
    color: white; display: flex; align-items: center; justify-content: center;
    font-weight: 700; font-size: 1.1rem; flex-shrink: 0;
  }
  .conv-info { flex: 1; min-width: 0; }
  .conv-name { font-weight: 600; font-size: 0.9rem; }
  .conv-preview { font-size: 0.8rem; color: var(--text-muted); white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .conv-time { font-size: 0.72rem; color: var(--text-muted); }
  .conv-unread { background: var(--primary); color: white; border-radius: 10px; padding: 2px 7px; font-size: 0.72rem; font-weight: 700; }
  .msg-chat {
    background: white; border-radius: var(--radius); box-shadow: var(--shadow);
    display: flex; flex-direction: column; border: 1.5px solid var(--border);
    overflow: hidden;
  }
  .msg-chat-header { padding: 16px 20px; border-bottom: 1.5px solid var(--border); display: flex; align-items: center; gap: 12px; }
  .msg-chat-header .conv-avatar { width: 40px; height: 40px; font-size: 1rem; }
  .chat-name { font-weight: 700; }
  .chat-ad-ref { font-size: 0.78rem; color: var(--text-muted); }
  .chat-messages { flex: 1; overflow-y: auto; padding: 20px; display: flex; flex-direction: column; gap: 12px; }
  .chat-msg { max-width: 70%; }
  .chat-msg.mine { align-self: flex-end; }
  .chat-msg.theirs { align-self: flex-start; }
  .msg-bubble {
    padding: 10px 14px; border-radius: 16px; font-size: 0.9rem; line-height: 1.5;
  }
  .chat-msg.mine .msg-bubble { background: var(--primary); color: white; border-bottom-right-radius: 4px; }
  .chat-msg.theirs .msg-bubble { background: var(--bg); color: var(--text); border-bottom-left-radius: 4px; }
  .msg-time { font-size: 0.7rem; color: var(--text-muted); margin-top: 4px; text-align: right; }
  .chat-input-wrap { padding: 16px; border-top: 1.5px solid var(--border); display: flex; gap: 10px; }
  .chat-input {
    flex: 1; padding: 11px 16px; border: 1.5px solid var(--border); border-radius: 25px;
    font-family: inherit; font-size: 0.9rem; outline: none;
  }
  .chat-input:focus { border-color: var(--primary); }
  .chat-send {
    width: 46px; height: 46px; border-radius: 50%; background: var(--primary);
    color: white; border: none; cursor: pointer; font-size: 1.2rem; transition: all 0.2s;
    display: flex; align-items: center; justify-content: center;
  }
  .chat-send:hover { background: var(--primary-dark); }
  .no-chat-selected { flex: 1; display: flex; align-items: center; justify-content: center; color: var(--text-muted); flex-direction: column; gap: 12px; font-size: 1rem; }
  /* ADMIN */
  .admin-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)); gap: 16px; margin-bottom: 28px; }
  .admin-stat {
    background: white; border-radius: var(--radius); padding: 20px; box-shadow: var(--shadow);
    border-left: 4px solid var(--primary);
  }
  .admin-stat .num { font-size: 2rem; font-weight: 800; color: var(--primary); }
  .admin-stat .lbl { font-size: 0.85rem; color: var(--text-muted); margin-top: 4px; }
  .admin-table-wrap { background: white; border-radius: var(--radius); padding: 20px; box-shadow: var(--shadow); overflow-x: auto; margin-bottom: 20px; }
  .admin-table-wrap h3 { margin-bottom: 16px; font-size: 1.1rem; }
  table { width: 100%; border-collapse: collapse; font-size: 0.9rem; }
  th { background: var(--bg); padding: 10px 14px; text-align: left; font-weight: 600; border-bottom: 2px solid var(--border); }
  td { padding: 10px 14px; border-bottom: 1px solid var(--border); vertical-align: middle; }
  tr:last-child td { border-bottom: none; }
  .status-badge {
    padding: 4px 10px; border-radius: 15px; font-size: 0.75rem; font-weight: 700;
  }
  .status-active { background: #e8f5e9; color: var(--success); }
  .status-sold { background: #ffebee; color: var(--danger); }
  .status-pending { background: #fff3e0; color: #e65100; }
  .action-btn {
    padding: 5px 12px; border-radius: 8px; border: none; cursor: pointer;
    font-family: inherit; font-size: 0.8rem; font-weight: 600; transition: all 0.2s;
  }
  .btn-approve { background: #e8f5e9; color: var(--success); }
  .btn-approve:hover { background: var(--success); color: white; }
  .btn-delete { background: #ffebee; color: var(--danger); }
  .btn-delete:hover { background: var(--danger); color: white; }
  .btn-sold { background: #fff3e0; color: #e65100; }
  /* TABS */
  .tabs { display: flex; gap: 4px; margin-bottom: 20px; background: white; padding: 6px; border-radius: 12px; box-shadow: var(--shadow); width: fit-content; }
  .tab-btn {
    padding: 9px 20px; border-radius: 9px; border: none; cursor: pointer;
    font-family: inherit; font-size: 0.9rem; font-weight: 600;
    background: transparent; color: var(--text-muted); transition: all 0.2s;
  }
  .tab-btn.active { background: var(--primary); color: white; }
  /* NOTIFICATIONS */
  .toast {
    position: fixed; bottom: 24px; right: 24px; background: var(--primary);
    color: white; padding: 14px 22px; border-radius: var(--radius-sm);
    font-weight: 600; z-index: 9999; box-shadow: var(--shadow-hover);
    animation: slideUp 0.3s ease; display: none; max-width: 300px;
  }
  .toast.error { background: var(--danger); }
  .toast.show { display: block; }
  @keyframes slideUp { from { transform: translateY(20px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
  /* AD DETAIL */
  .ad-detail-img {
    width: 100%; max-height: 340px; object-fit: cover; border-radius: var(--radius);
    margin-bottom: 20px; background: linear-gradient(135deg, #e8f5e9, #c8e6c9);
    display: flex; align-items: center; justify-content: center; font-size: 6rem;
    min-height: 200px;
  }
  .ad-detail-price { font-size: 2rem; font-weight: 800; color: var(--primary); margin: 8px 0; }
  .ad-detail-desc { line-height: 1.7; color: var(--text); margin: 12px 0; }
  .ad-detail-info { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin: 16px 0; }
  .info-item { background: var(--bg); padding: 10px 14px; border-radius: 10px; }
  .info-item label { font-size: 0.75rem; color: var(--text-muted); display: block; margin-bottom: 4px; }
  .info-item span { font-weight: 600; }
  /* PROFILE */
  .profile-header { background: white; border-radius: var(--radius); padding: 28px; margin-bottom: 20px; box-shadow: var(--shadow); display: flex; gap: 20px; align-items: center; }
  .profile-avatar { width: 80px; height: 80px; border-radius: 50%; background: var(--primary); color: white; display: flex; align-items: center; justify-content: center; font-size: 2rem; font-weight: 700; }
  .profile-info h2 { font-size: 1.4rem; font-weight: 700; }
  .profile-info p { color: var(--text-muted); font-size: 0.9rem; }
  /* RESPONSIVE */
  @media (max-width: 700px) {
    .hero h1 { font-size: 1.6rem; }
    .msg-layout { grid-template-columns: 1fr; height: auto; }
    .msg-list { height: 300px; }
    .msg-chat { height: 500px; }
    nav button { padding: 6px 10px; font-size: 0.78rem; }
    .form-row { grid-template-columns: 1fr; }
    .ad-detail-info { grid-template-columns: 1fr; }
  }
  /* LOADER */
  .loader { text-align: center; padding: 40px; color: var(--text-muted); }
  .loader::after { content: '...'; animation: dots 1.5s infinite; }
  @keyframes dots { 0%,100%{content:'...'} 33%{content:'.'} 66%{content:'...'} }
  .section-title { font-size: 1.3rem; font-weight: 700; margin-bottom: 16px; display: flex; align-items: center; gap: 8px; }
  .favorites-note { background: #fff3cd; border: 1.5px solid #ffc107; border-radius: 10px; padding: 12px 16px; margin-bottom: 16px; font-size: 0.9rem; color: #856404; }
  .user-name-badge { background: rgba(255,255,255,0.2); padding: 5px 12px; border-radius: 20px; font-size: 0.85rem; font-weight: 600; }
</style>

<!-- Firebase SDK -->
<script type="module">
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js";
  import { getDatabase, ref, push, onValue, set, update, remove, get, orderByChild, query, limitToLast } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-database.js";

  // ========== ⚙️ FIREBASE CONFIG - এখানে আপনার config বসান ==========
  const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT.firebaseapp.com",
    databaseURL: "https://YOUR_PROJECT-default-rtdb.asia-southeast1.firebasedatabase.app",
    projectId: "YOUR_PROJECT",
    storageBucket: "YOUR_PROJECT.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
  };
  // =====================================================================

  const app = initializeApp(firebaseConfig);
  const db = getDatabase(app);

  // ===== STATE =====
  let currentUser = null;
  let currentPage = 'home';
  let allAds = [];
  let conversations = {};
  let activeConvId = null;
  let favorites = JSON.parse(localStorage.getItem('cb_favs') || '[]');
  let adFilter = { type: 'all', condition: 'all', search: '' };

  // ===== AUTH =====
  window.doLogin = function() {
    const name = document.getElementById('loginName').value.trim();
    const phone = document.getElementById('loginPhone').value.trim();
    if (!name || !phone) return showToast('নাম ও ফোন নম্বর দিন', true);
    if (phone.length < 10) return showToast('সঠিক ফোন নম্বর দিন', true);
    const userId = 'user_' + phone.replace(/[^0-9]/g, '');
    const userData
