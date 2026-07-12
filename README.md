<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>预约详情 · #F-2418 小彤 · Alpha 专属</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700;900&family=Noto+Serif+SC:wght@400;700;900&family=JetBrains+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  * { margin:0; padding:0; box-sizing:border-box; }
  html { scroll-behavior:smooth; }
  body {
    font-family: 'Noto Serif SC', serif;
    background: #0A0A0F;
    color: #FAF6F0;
    line-height: 1.6;
  }
  .mono { font-family: 'JetBrains Mono', monospace; }

  /* ========== NAV ========== */
  nav {
    position: sticky; top: 0; z-index: 100;
    display: flex; justify-content: space-between; align-items: center;
    padding: 14px 40px;
    background: rgba(10,10,15,0.95);
    backdrop-filter: blur(20px);
    border-bottom: 1px solid rgba(212,165,116,0.2);
  }
  .logo {
    font-family: 'Playfair Display', serif;
    font-size: 22px; font-weight: 900;
    color: #D4A574; letter-spacing: 2px;
  }
  .logo span { color: #FF3E7F; }
  .nav-breadcrumb { color: #666; font-size: 12px; letter-spacing: 1px; }
  .nav-breadcrumb b { color: #D4A574; }
  .alpha-badge {
    display: flex; align-items: center; gap: 12px;
    padding: 8px 16px 8px 8px;
    background: linear-gradient(90deg, #000, #1a0f24);
    border: 1px solid #FF3E7F;
    border-radius: 30px;
    box-shadow: 0 0 20px rgba(255,62,127,0.3);
  }
  .alpha-avatar {
    width: 34px; height: 34px;
    background: linear-gradient(135deg, #FF3E7F, #D4A574);
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-weight: 900; color: #fff; font-size: 13px;
    font-family: 'Playfair Display', serif;
  }
  .alpha-info { display: flex; flex-direction: column; gap: 2px; }
  .alpha-name { font-size: 13px; color: #fff; font-family: 'JetBrains Mono', monospace; }
  .alpha-tier { font-size: 10px; color: #FF3E7F; letter-spacing: 2px; }

  /* ========== BANNER ========== */
  .banner {
    background: linear-gradient(135deg, #FF3E7F 0%, #D4A574 100%);
    padding: 28px 40px;
    display: flex; justify-content: space-between; align-items: center;
    flex-wrap: wrap; gap: 20px;
    position: relative;
    overflow: hidden;
  }
  .banner::before {
    content: '✓';
    position: absolute; right: -30px; top: -30px;
    font-size: 200px; color: rgba(255,255,255,0.08);
    font-weight: 900;
  }
  .banner-left { position: relative; z-index: 2; }
  .banner-title {
    font-family: 'Playfair Display', serif;
    font-size: 28px; font-weight: 900;
    color: #fff; margin-bottom: 6px;
  }
  .banner-sub { color: rgba(255,255,255,0.85); font-size: 13px; letter-spacing: 1px; }
  .banner-sub b { font-family: 'JetBrains Mono', monospace; }
  .countdown {
    display: flex; gap: 12px; position: relative; z-index: 2;
  }
  .countdown-box {
    background: rgba(0,0,0,0.35);
    backdrop-filter: blur(10px);
    padding: 10px 16px;
    border-radius: 12px;
    text-align: center;
    min-width: 70px;
  }
  .countdown-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 26px; font-weight: 700; color: #fff;
    line-height: 1;
  }
  .countdown-label { font-size: 10px; color: rgba(255,255,255,0.7); letter-spacing: 1px; margin-top: 4px; }
  .banner-share {
    padding: 12px 24px;
    background: rgba(0,0,0,0.5);
    color: #fff; border: 1px solid rgba(255,255,255,0.3);
    border-radius: 30px;
    font-size: 12px; letter-spacing: 2px;
    cursor: pointer; font-family: inherit;
    position: relative; z-index: 2;
    transition: all 0.3s;
  }
  .banner-share:hover { background: rgba(0,0,0,0.8); border-color: #fff; }

  /* ========== LAYOUT ========== */
  .wrap { max-width: 1300px; margin: 0 auto; padding: 40px; }
  .grid-2 { display: grid; grid-template-columns: 440px 1fr; gap: 40px; }
  @media (max-width: 900px) { .grid-2 { grid-template-columns: 1fr; } }

  /* ========== 主图区 ========== */
  .photo-block { position: sticky; top: 100px; align-self: start; }
  .main-photo {
    width: 100%; aspect-ratio: 3/4;
    background: linear-gradient(135deg, #3d2645, #1a0f24) center/cover no-repeat;
    border-radius: 24px;
    position: relative;
    overflow: hidden;
    border: 1px solid rgba(212,165,116,0.3);
  }
  .photo-mask {
    position: absolute; top: 20px; left: 20px;
    padding: 8px 16px;
    background: rgba(212,165,116,0.95);
    color: #0A0A0F;
    font-family: 'JetBrains Mono', monospace;
    font-size: 13px; font-weight: 700;
    border-radius: 20px;
    letter-spacing: 2px;
  }
  .photo-verified {
    position: absolute; top: 20px; right: 20px;
    padding: 6px 14px;
    background: rgba(74,222,128,0.9);
    color: #000;
    font-size: 11px; font-weight: 700;
    border-radius: 20px;
    letter-spacing: 1px;
    display: flex; align-items: center; gap: 6px;
  }
  .photo-bottom-overlay {
    position: absolute; bottom: 0; left: 0; right: 0;
    padding: 60px 20px 20px;
    background: linear-gradient(0deg, rgba(0,0,0,0.9), transparent);
  }
  .photo-status {
    display: flex; align-items: center; gap: 8px;
    color: #fff; font-size: 12px;
    margin-bottom: 8px;
  }
  .photo-status::before {
    content: ''; width: 8px; height: 8px;
    background: #FF3E7F; border-radius: 50%;
    animation: pulse 1.5s infinite;
  }
  @keyframes pulse { 50% { opacity: 0.3; } }
  .photo-subname {
    color: #fff; font-size: 22px;
    font-family: 'Playfair Display', serif;
    font-weight: 700;
  }
  .photo-thumbs { display: flex; gap: 8px; margin-top: 12px; }
  .thumb {
    flex: 1; aspect-ratio: 1;
    background: linear-gradient(135deg, #3d2645, #1a0f24);
    border-radius: 12px;
    border: 1px solid rgba(212,165,116,0.15);
    display: flex; align-items: center; justify-content: center;
    color: #666; font-size: 10px;
    font-family: 'JetBrains Mono', monospace;
    cursor: pointer;
    transition: all 0.3s;
  }
  .thumb:hover { border-color: #D4A574; color: #D4A574; }

  /* ========== 右侧 ========== */
  .title-row {
    display: flex; align-items: baseline; gap: 15px;
    margin-bottom: 8px; flex-wrap: wrap;
  }
  .main-title {
    font-family: 'Playfair Display','Noto Serif SC', serif;
    font-size: 44px; font-weight: 900;
    color: #fff;
  }
  .id-badge {
    padding: 4px 12px;
    background: rgba(212,165,116,0.15);
    color: #D4A574;
    font-family: 'JetBrains Mono', monospace;
    font-size: 14px;
    border-radius: 20px;
    letter-spacing: 1px;
  }
  .meta-line {
    color: #999; font-size: 14px;
    margin-bottom: 20px;
    display: flex; flex-wrap: wrap; gap: 8px;
  }
  .meta-line span { }
  .meta-line span + span::before { content: '·'; margin: 0 8px; color: #555; }

  .rating-row {
    display: flex; align-items: center; gap: 15px;
    padding: 14px 0;
    border-top: 1px solid rgba(255,255,255,0.06);
    border-bottom: 1px solid rgba(255,255,255,0.06);
    margin-bottom: 24px;
  }
  .rating-big {
    font-family: 'JetBrains Mono', monospace;
    font-size: 32px; font-weight: 700;
    color: #D4A574;
  }
  .rating-detail { color: #888; font-size: 13px; }
  .rating-detail b { color: #ccc; }

  /* ========== 标签 ========== */
  .tags-block {
    padding: 20px;
    background: rgba(255,62,127,0.04);
    border: 1px solid rgba(255,62,127,0.15);
    border-radius: 16px;
    margin-bottom: 24px;
  }
  .tags-title { font-size: 12px; color: #D4A574; letter-spacing: 3px; margin-bottom: 12px; }
  .tags-flex { display: flex; flex-wrap: wrap; gap: 8px; }
  .tag {
    padding: 6px 14px;
    background: rgba(255,62,127,0.15);
    color: #FF3E7F;
    font-size: 12px;
    border-radius: 20px;
    border: 1px solid rgba(255,62,127,0.3);
  }
  .tag.gold {
    background: rgba(212,165,116,0.15);
    color: #D4A574;
    border-color: rgba(212,165,116,0.3);
  }
  .tag.warn {
    background: rgba(239,68,68,0.15);
    color: #ef4444;
    border-color: rgba(239,68,68,0.3);
  }

  /* ========== 数据格子 ========== */
  .data-grid {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 12px;
    margin-bottom: 30px;
  }
  .data-cell {
    padding: 16px;
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 12px;
    text-align: center;
  }
  .data-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 22px; font-weight: 700;
    color: #D4A574;
  }
  .data-name { font-size: 10px; color: #888; letter-spacing: 2px; margin-top: 4px; }

  /* ========== BLOCK 通用 ========== */
  .block {
    padding: 30px;
    background: #14141c;
    border: 1px solid rgba(212,165,116,0.15);
    border-radius: 20px;
    margin-bottom: 24px;
  }
  .block-title {
    font-size: 14px; color: #D4A574;
    letter-spacing: 3px;
    margin-bottom: 20px;
    display: flex; align-items: center; justify-content: space-between;
    text-transform: uppercase;
  }
  .block-title small { color: #666; font-size: 11px; letter-spacing: 1px; }

  /* ========== BETA 对照 ========== */
  .compare {
    display: grid;
    grid-template-columns: 1fr auto 1fr;
    gap: 20px;
    align-items: stretch;
  }
  .compare-col {
    padding: 20px;
    border-radius: 14px;
  }
  .compare-alpha {
    background: linear-gradient(135deg, rgba(255,62,127,0.1), rgba(212,165,116,0.05));
    border: 1px solid rgba(255,62,127,0.3);
  }
  .compare-beta {
    background: rgba(80,80,80,0.08);
    border: 1px solid rgba(255,255,255,0.05);
  }
  .compare-vs {
    display: flex; align-items: center;
    font-family: 'Playfair Display', serif;
    font-size: 28px; color: #FF3E7F;
    font-style: italic;
  }
  .compare-header {
    display: flex; align-items: center; gap: 10px;
    margin-bottom: 15px;
    padding-bottom: 12px;
    border-bottom: 1px solid rgba(255,255,255,0.06);
  }
  .compare-tag {
    padding: 3px 10px;
    font-size: 10px;
    border-radius: 20px;
    letter-spacing: 2px;
  }
  .tag-alpha { background: #FF3E7F; color: #fff; }
  .tag-beta { background: #555; color: #ccc; }
  .compare-id { font-family: 'JetBrains Mono', monospace; font-size: 11px; color: #888; }
  .compare-row {
    display: flex; justify-content: space-between;
    padding: 7px 0;
    font-size: 13px;
    border-bottom: 1px dashed rgba(255,255,255,0.05);
  }
  .compare-row:last-child { border: none; }
  .compare-row .label { color: #777; font-size: 12px; }
  .compare-row .val { font-family: 'JetBrains Mono', monospace; }
  .val.good { color: #4ade80; }
  .val.bad { color: #ef4444; }
  .val.mid { color: #ccc; }
  .compare-note {
    margin-top: 12px;
    padding-top: 12px;
    border-top: 1px solid rgba(255,255,255,0.06);
    font-size: 11px;
    color: #666;
    font-style: italic;
    line-height: 1.6;
  }
  @media (max-width: 900px) {
    .compare { grid-template-columns: 1fr; }
    .compare-vs { justify-content: center; padding: 10px 0; }
  }

  /* ========== 服务清单 ========== */
  .service-list { }
  .service-item {
    display: flex; justify-content: space-between; align-items: center;
    padding: 14px 18px;
    background: rgba(74,222,128,0.05);
    border: 1px solid rgba(74,222,128,0.2);
    border-radius: 10px;
    margin-bottom: 8px;
    font-size: 13px;
  }
  .service-left { display: flex; align-items: center; gap: 12px; }
  .service-check {
    width: 22px; height: 22px;
    background: #4ade80;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    color: #000; font-weight: 900; font-size: 13px;
  }
  .service-title { color: #eee; }
  .service-note { color: #666; font-size: 11px; margin-left: 6px; }
  .service-price {
    font-family: 'JetBrains Mono', monospace;
    color: #D4A574; font-size: 14px;
  }
  .service-total {
    margin-top: 20px; padding: 20px 24px;
    background: linear-gradient(135deg, rgba(255,62,127,0.15), rgba(212,165,116,0.08));
    border: 1px solid #FF3E7F;
    border-radius: 14px;
    display: flex; justify-content: space-between; align-items: center;
  }
  .service-total-left { font-size: 13px; color: #ccc; }
  .service-total-left small { color: #666; display: block; margin-top: 3px; font-size: 11px; }
  .service-total-num {
    font-family: 'JetBrains Mono', monospace;
    font-size: 32px; font-weight: 700; color: #FF3E7F;
  }
  .paid-badge {
    display: inline-block;
    padding: 3px 10px;
    background: #4ade80;
    color: #000;
    font-size: 10px; font-weight: 700;
    letter-spacing: 2px;
    border-radius: 4px;
    margin-left: 10px;
  }

  /* ========== 地图 ========== */
  .map-block {
    padding: 24px;
    background: linear-gradient(135deg, #1a1a2a, #0f0f1a);
    border: 1px solid rgba(212,165,116,0.2);
    border-radius: 20px;
    margin-bottom: 24px;
    position: relative;
    overflow: hidden;
  }
  .map-fake {
    height: 200px;
    background:
      linear-gradient(0deg, rgba(20,20,28,0.7), transparent),
      repeating-linear-gradient(45deg, rgba(212,165,116,0.05) 0px, rgba(212,165,116,0.05) 2px, transparent 2px, transparent 20px),
      repeating-linear-gradient(-45deg, rgba(212,165,116,0.05) 0px, rgba(212,165,116,0.05) 2px, transparent 2px, transparent 20px),
      #0a0a12;
    border-radius: 12px;
    position: relative;
    margin-bottom: 15px;
  }
  .map-pin {
    position: absolute; top: 50%; left: 50%;
    transform: translate(-50%, -50%);
    display: flex; flex-direction: column; align-items: center;
  }
  .pin-dot {
    width: 20px; height: 20px;
    background: #FF3E7F; border-radius: 50%;
    box-shadow: 0 0 0 8px rgba(255,62,127,0.2), 0 0 0 16px rgba(255,62,127,0.1);
    animation: pinPulse 2s infinite;
  }
  @keyframes pinPulse {
    0%, 100% { box-shadow: 0 0 0 8px rgba(255,62,127,0.3), 0 0 0 16px rgba(255,62,127,0.15); }
    50% { box-shadow: 0 0 0 14px rgba(255,62,127,0.15), 0 0 0 28px rgba(255,62,127,0.05); }
  }
  .pin-label {
    margin-top: 8px;
    padding: 4px 10px;
    background: rgba(0,0,0,0.85);
    color: #FF3E7F;
    font-size: 11px;
    font-family: 'JetBrains Mono', monospace;
    border-radius: 4px;
    white-space: nowrap;
  }
  .map-info { display: flex; justify-content: space-between; font-size: 13px; }
  .map-address { color: #ccc; }
  .map-address b { color: #D4A574; }
  .map-distance {
    font-family: 'JetBrains Mono', monospace;
    color: #888; font-size: 12px;
  }

  /* ========== 历史记录 ========== */
  .history-item {
    display: grid;
    grid-template-columns: 100px 1fr auto;
    gap: 15px; align-items: center;
    padding: 14px 0;
    border-bottom: 1px dashed rgba(255,255,255,0.06);
    font-size: 13px;
  }
  .history-item:last-child { border: none; }
  .history-date {
    font-family: 'JetBrains Mono', monospace;
    color: #888; font-size: 12px;
  }
  .history-alpha { color: #ccc; }
  .history-alpha b { color: #FF3E7F; font-family: 'JetBrains Mono', monospace; }
  .history-service { color: #666; font-size: 11px; margin-top: 3px; }
  .history-rating { color: #D4A574; font-size: 12px; }

  /* ========== 闺蜜留言 ========== */
  .msg-item {
    padding: 15px;
    background: rgba(255,62,127,0.05);
    border-left: 3px solid #FF3E7F;
    border-radius: 4px;
    margin-bottom: 10px;
  }
  .msg-head {
    display: flex; justify-content: space-between;
    margin-bottom: 8px;
    font-size: 12px;
  }
  .msg-user { color: #FF3E7F; font-weight: 700; }
  .msg-time { color: #555; font-family: 'JetBrains Mono', monospace; font-size: 11px; }
  .msg-text { color: #ccc; font-size: 13px; line-height: 1.7; }

  /* ========== 私信 ========== */
  .chat-window {
    background: #0a0a12;
    border-radius: 14px;
    padding: 20px;
    max-height: 400px;
    overflow-y: auto;
  }
  .chat-msg {
    max-width: 75%;
    padding: 10px 14px;
    border-radius: 16px;
    margin-bottom: 10px;
    font-size: 13px;
    line-height: 1.5;
  }
  .chat-from-her {
    background: rgba(255,255,255,0.06);
    color: #eee;
    align-self: flex-start;
    border-top-left-radius: 4px;
  }
  .chat-from-me {
    background: linear-gradient(135deg, #FF3E7F, #D4A574);
    color: #fff;
    align-self: flex-end;
    margin-left: auto;
    border-top-right-radius: 4px;
  }
  .chat-flex { display: flex; flex-direction: column; }
  .chat-time { font-size: 10px; color: #555; margin-top: 4px; }
  .chat-input {
    display: flex; gap: 10px;
    margin-top: 15px;
  }
  .chat-input input {
    flex: 1; padding: 12px 16px;
    background: rgba(255,255,255,0.04);
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 25px;
    color: #fff;
    font-family: inherit;
    outline: none;
  }
  .chat-input input:focus { border-color: #D4A574; }
  .chat-input button {
    padding: 12px 24px;
    background: #FF3E7F;
    color: #fff;
    border: none; border-radius: 25px;
    cursor: pointer;
    font-family: inherit;
    font-size: 13px;
  }

  /* ========== Beta 通知记录 ========== */
  .notice-item {
    display: flex; justify-content: space-between; align-items: center;
    padding: 12px 15px;
    background: rgba(80,80,80,0.05);
    border-left: 3px solid #666;
    border-radius: 4px;
    margin-bottom: 6px;
    font-size: 12px;
  }
  .notice-info { color: #999; }
  .notice-info b { color: #D4A574; font-family: 'JetBrains Mono', monospace; }
  .notice-time { color: #555; font-family: 'JetBrains Mono', monospace; font-size: 11px; }
  .notice-status {
    padding: 3px 8px;
    font-size: 10px;
    border-radius: 4px;
    font-weight: 700;
    letter-spacing: 1px;
  }
  .status-read { background: rgba(239,68,68,0.15); color: #ef4444; }
  .status-unread { background: rgba(74,222,128,0.15); color: #4ade80; }

  /* ========== 留言区 ========== */
  .leave-msg {
    padding: 20px;
    background: rgba(255,255,255,0.03);
    border: 1px solid rgba(212,165,116,0.15);
    border-radius: 14px;
  }
  .leave-msg textarea {
    width: 100%; min-height: 100px;
    padding: 12px;
    background: #0a0a12;
    border: 1px solid rgba(255,255,255,0.08);
    border-radius: 10px;
    color: #fff;
    font-family: inherit;
    font-size: 13px;
    resize: vertical;
    outline: none;
    line-height: 1.6;
  }
  .leave-msg textarea:focus { border-color: #D4A574; }
  .leave-msg-actions {
    display: flex; justify-content: space-between; align-items: center;
    margin-top: 12px;
  }
  .leave-msg-hint { color: #666; font-size: 11px; }
  .leave-msg button {
    padding: 10px 24px;
    background: #FF3E7F;
    color: #fff;
    border: none; border-radius: 25px;
    cursor: pointer;
    font-family: inherit;
    font-size: 12px;
    letter-spacing: 2px;
  }

  /* ========== 底部 ========== */
  .footer-actions {
    padding: 40px;
    background: linear-gradient(180deg, #14141c, #050508);
    border-top: 1px solid rgba(212,165,116,0.15);
    text-align: center;
  }
  .footer-title {
    font-family: 'Playfair Display', serif;
    font-size: 20px; color: #D4A574;
    margin-bottom: 20px;
    font-style: italic;
  }
  .footer-buttons {
    display: flex; justify-content: center; gap: 15px;
    flex-wrap: wrap;
  }
  .fbtn {
    padding: 14px 28px;
    border-radius: 30px;
    font-size: 12px;
    letter-spacing: 2px;
    cursor: pointer;
    font-family: inherit;
    transition: all 0.3s;
    text-decoration: none;
    display: inline-block;
  }
  .fbtn-primary {
    background: #FF3E7F; color: #fff;
    border: none;
    box-shadow: 0 0 20px rgba(255,62,127,0.4);
  }
  .fbtn-primary:hover { transform: scale(1.05); }
  .fbtn-secondary {
    background: transparent; color: #ccc;
    border: 1px solid rgba(212,165,116,0.3);
  }
  .fbtn-secondary:hover { border-color: #D4A574; color: #D4A574; }
  .footer-note { color: #444; font-size: 11px; margin-top: 25px; font-family: 'JetBrains Mono', monospace; }

  /* ========== TOAST ========== */
  .toast {
    position: fixed; top: 80px; right: 20px; z-index: 300;
    padding: 14px 22px;
    background: #14141c;
    border: 1px solid #D4A574;
    border-left: 4px solid #FF3E7F;
    border-radius: 12px;
    color: #fff; font-size: 13px;
    max-width: 320px;
    transform: translateX(400px);
    transition: transform 0.4s;
  }
  .toast.show { transform: translateX(0); }
  .toast-t { color: #D4A574; font-size: 11px; letter-spacing: 2px; margin-bottom: 4px; }

</style>
</head>
<body>

<!-- ============ NAV ============ -->
<nav>
  <div class="logo">RAG<span>·</span></div>
  <div class="nav-breadcrumb">订单详情 &nbsp;/&nbsp; <b>#F-2418 · 小彤</b> &nbsp;/&nbsp; 已确认</div>
  <div class="alpha-badge">
    <div class="alpha-avatar">K</div>
    <div class="alpha-info">
      <div class="alpha-name">KAI · #A-0007</div>
      <div class="alpha-tier">★ BLACK CARD · S+</div>
    </div>
  </div>
</nav>

<!-- ============ BANNER ============ -->
<div class="banner">
  <div class="banner-left">
    <div class="banner-title">✓ 预约已确认</div>
    <div class="banner-sub">
      订单号 <b>#RAG-20250712-A0007-F2418</b> &nbsp;·&nbsp;
      服务开始: <b>今晚 20:00 · 扬州</b> &nbsp;·&nbsp;
      支付状态: <b style="color:#fff">已支付 ✓</b>
    </div>
  </div>
  <div class="countdown" id="countdown">
    <div class="countdown-box"><div class="countdown-num" id="cd-h">--</div><div class="countdown-label">HOURS</div></div>
    <div class="countdown-box"><div class="countdown-num" id="cd-m">--</div><div class="countdown-label">MINUTES</div></div>
    <div class="countdown-box"><div class="countdown-num" id="cd-s">--</div><div class="countdown-label">SECONDS</div></div>
  </div>
  <button class="banner-share" onclick="showToast('已发送','剪辑将于服务结束后 · 自动发送至 #B-0620')">📤 一键分享给 Beta #B-0620</button>
</div>

<!-- ============ MAIN CONTENT ============ -->
<div class="wrap">
  <div class="grid-2">

    <!-- 左侧 · 图片 -->
    <div class="photo-block">
      <div class="main-photo" style="background-image:url('IMG_6174.jpeg')">
        <div class="photo-mask">#F-2418</div>
        <div class="photo-verified">✓ 已认证</div>
        <div class="photo-bottom-overlay">
          <div class="photo-status">当前状态: 待命中 · 已开始准备</div>
          <div class="photo-subname">TONG · 小 彤</div>
        </div>
      </div>
      <div class="photo-thumbs">
        <div class="thumb">+3 私照</div>
        <div class="thumb">+5 视频</div>
        <div class="thumb">校服照</div>
        <div class="thumb">全裸</div>
      </div>
    </div>

    <!-- 右侧 · 信息 -->
    <div>
      <div class="title-row">
        <div class="main-title">小彤</div>
        <div class="id-badge">#F-2418</div>
        <div class="id-badge" style="background:rgba(255,62,127,0.15);color:#FF3E7F">🔥 本周TOP</div>
      </div>
      <div class="meta-line">
        <span>18 岁</span>
        <span>163 cm</span>
        <span>50 kg</span>
        <span>少女型 · B罩杯</span>
        <span>腰细·臀翘度中</span>
        <span>天秤座</span>
        <span>扬州</span>
        <span>职高在读</span>
      </div>

      <div class="rating-row">
        <div class="rating-big">4.98</div>
        <div class="rating-detail">
          ★★★★★ &nbsp;·&nbsp; <b>1,247</b> 条评价 &nbsp;·&nbsp; 好评率 <b style="color:#4ade80">99.6%</b> &nbsp;·&nbsp; 回头客 <b style="color:#4ade80">94%</b>
        </div>
      </div>

      <!-- 标签 -->
      <div class="tags-block">
        <div class="tags-title">— PROFILE TAGS —</div>
        <div class="tags-flex">
          <span class="tag gold">🔥 热门</span>
          <span class="tag gold">✨ 新人爆款</span>
          <span class="tag">处女感</span>
          <span class="tag">学生装</span>
          <span class="tag">JK制服</span>
          <span class="tag warn">内射可</span>
          <span class="tag warn">无套服务</span>
          <span class="tag warn">多人服务</span>
          <span class="tag">拍摄可</span>
          <span class="tag">SM可</span>
          <span class="tag">深喉专家</span>
          <span class="tag">叫床甜</span>
          <span class="tag">会说老公</span>
          <span class="tag">脚控友好</span>
          <span class="tag">会主动</span>
          <span class="tag">不拒绝</span>
          <span class="tag warn">双穴开发</span>
          <span class="tag">颜射可</span>
          <span class="tag">吞精可</span>
          <span class="tag">中出后续摄</span>
          <span class="tag">口爆</span>
          <span class="tag">调教配合</span>
          <span class="tag">戴项圈</span>
          <span class="tag">被绑</span>
          <span class="tag">被扇耳光</span>
          <span class="tag">羞辱play</span>
          <span class="tag">校服角色扮演</span>
          <span class="tag">称"叔叔"</span>
          <span class="tag warn">Beta同居中</span>
          <span class="tag warn">男友完全不知情</span>
        </div>
      </div>

      <!-- 数据 -->
      <div class="data-grid">
        <div class="data-cell"><div class="data-num">6</div><div class="data-name">上架月数</div></div>
        <div class="data-cell"><div class="data-num">347</div><div class="data-name">累计服务</div></div>
        <div class="data-cell"><div class="data-num">89</div><div class="data-name">本月次数</div></div>
        <div class="data-cell"><div class="data-num">89</div><div class="data-name">戴绿帽次数</div></div>
      </div>
    </div>
  </div>

  <!-- ========== BETA 对照 ========== -->
  <div class="block">
    <div class="block-title">— ALPHA vs BETA · 差距对比 — <small>数据由平台自动生成</small></div>
    <div class="compare">
      <div class="compare-col compare-alpha">
        <div class="compare-header">
          <span class="compare-tag tag-alpha">ALPHA</span>
          <span class="compare-id">#A-0007 · KAI</span>
        </div>
        <div class="compare-row"><span class="label">身高</span><span class="val good">190 cm</span></div>
        <div class="compare-row"><span class="label">体重</span><span class="val mid">82 kg</span></div>
        <div class="compare-row"><span class="label">月收入</span><span class="val good">¥ 280,000</span></div>
        <div class="compare-row"><span class="label">职业</span><span class="val mid">投行 VP</span></div>
        <div class="compare-row"><span class="label">学历</span><span class="val mid">常春藤 MBA</span></div>
        <div class="compare-row"><span class="label">外貌评分</span><span class="val good">9.4 / 10</span></div>
        <div class="compare-row"><span class="label">私处长度</span><span class="val good">22 cm</span></div>
        <div class="compare-row"><span class="label">睾酮水平</span><span class="val good">9.8 nmol/L</span></div>
        <div class="compare-row"><span class="label">认证等级</span><span class="val good">S+ 级</span></div>
        <div class="compare-note">✓ 已通过 DNA / 外貌 / 收入 / 体格 四项 Alpha 认证</div>
      </div>

      <div class="compare-vs">VS</div>

      <div class="compare-col compare-beta">
        <div class="compare-header">
          <span class="compare-tag tag-beta">BETA</span>
          <span class="compare-id">#B-0620 · 男友</span>
        </div>
        <div class="compare-row"><span class="label">身高</span><span class="val bad">180 cm ↓</span></div>
        <div class="compare-row"><span class="label">体重</span><span class="val mid">70 kg</span></div>
        <div class="compare-row"><span class="label">月收入</span><span class="val bad">¥ 0（学生）</span></div>
        <div class="compare-row"><span class="label">职业</span><span class="val bad">高中在读</span></div>
        <div class="compare-row"><span class="label">学历</span><span class="val bad">高中未毕业</span></div>
        <div class="compare-row"><span class="label">外貌评分</span><span class="val bad">7.0 / 10（自评）</span></div>
        <div class="compare-row"><span class="label">私处长度</span><span class="val bad">6 cm（低于均值 47%）</span></div>
        <div class="compare-row"><span class="label">睾酮水平</span><span class="val bad">3.2 nmol/L</span></div>
        <div class="compare-row"><span class="label">认证等级</span><span class="val bad">Beta · 劣质</span></div>
        <div class="compare-note">
          备注：痴情。每天早安晚安。以为自己是她初恋。<br>
          以为自己是她第一个男人。<br>
          与她恋爱 <b style="color:#ef4444">500 天</b>（约 1 年 4 个月）。<br>
          期间被戴绿帽 <b style="color:#ef4444">89 次</b>。<br>
          察觉状态：<b style="color:#4ade80">完全不知情</b> ✓
        </div>
      </div>
    </div>
  </div>

  <!-- ========== 已选服务 ========== -->
  <div class="block">
    <div class="block-title">— 已选服务清单 · FULL PACKAGE — <small>共 12 项 · 已支付</small></div>
    <div class="service-list">
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">过夜服务</span><span class="service-note">12小时 · 无限次数</span></div></div><div class="service-price">¥ 6,880</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">深喉练习</span><span class="service-note">她是专家</span></div></div><div class="service-price">¥ 380</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">JK 校服着装</span><span class="service-note">她自己的校服</span></div></div><div class="service-price">¥ 500</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">高跟鞋 + 白袜</span></div></div><div class="service-price">¥ 200</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">无套内射</span><span class="service-note">怀孕风险自担</span></div></div><div class="service-price">¥ 1,200</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">双穴开发</span><span class="service-note">首次尝试</span></div></div><div class="service-price">¥ 1,800</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">SM 调教</span><span class="service-note">项圈+皮带+扇耳光</span></div></div><div class="service-price">¥ 800</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">多人服务预约</span><span class="service-note">+2 位 Alpha 助阵</span></div></div><div class="service-price">¥ 2,000</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">全程拍摄留档</span><span class="service-note">4K · 多机位</span></div></div><div class="service-price">¥ 500</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">发送剪辑给 Beta 男</span><span class="service-note">目标: #B-0620</span></div></div><div class="service-price">¥ 800</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">闺蜜旁白定制</span><span class="service-note">由 #F-2419 录制</span></div></div><div class="service-price">¥ 1,500</div></div>
      <div class="service-item"><div class="service-left"><div class="service-check">✓</div><div><span class="service-title">羞辱台词 Pack</span><span class="service-note">"叫叔叔"·"骂男友"</span></div></div><div class="service-price">¥ 500</div></div>
    </div>
    <div class="service-total">
      <div class="service-total-left">
        订单总额（本次预约）
        <small>Beta #B-0620 月收入的 ∞ 倍 · 因为他月入 ¥0</small>
      </div>
      <div class="service-total-num">¥ 17,060 <span class="paid-badge">已支付</span></div>
    </div>
  </div>

  <!-- ========== 地图 ========== -->
  <div class="map-block">
    <div class="block-title">— 服务地点 · LOCATION —</div>
    <div class="map-fake">
      <div class="map-pin">
        <div class="pin-dot"></div>
        <div class="pin-label">#F-2418 已就位</div>
      </div>
    </div>
    <div class="map-info">
      <div class="map-address">
        📍 <b>扬州 · 江都区 · ****大酒店</b> · 3208 房<br>
        <span style="font-size:11px;color:#666">距离 Beta #B-0620 居住地约 4.2 公里 · 步行 52 分钟</span>
      </div>
      <div class="map-distance">
        LAT: 32.****<br>LNG: 119.****
      </div>
    </div>
  </div>

  <!-- ========== 倒计时详细 & 历史记录 ========== -->
  <div class="grid-2" style="grid-template-columns: 1fr 1fr;">
    <div class="block">
      <div class="block-title">— 历史租借记录 — <small>近 10 次</small></div>
      <div class="history-item">
        <div class="history-date">2025-07-11<br><span style="font-size:10px">昨晚</span></div>
        <div>
          <div class="history-alpha">Alpha <b>#A-0089</b> · 金卡</div>
          <div class="history-service">深度练习 3h · 无套内射 ×2</div>
        </div>
        <div class="history-rating">★ 5.0</div>
      </div>
      <div class="history-item">
        <div class="history-date">2025-07-09</div>
        <div>
          <div class="history-alpha">Alpha <b>#A-0417</b> · 银卡</div>
          <div class="history-service">过夜 · 双穴开发首次尝试</div>
        </div>
        <div class="history-rating">★ 4.9</div>
      </div>
      <div class="history-item">
        <div class="history-date">2025-07-07</div>
        <div>
          <div class="history-alpha">Alpha <b>#A-0231</b> · 铜卡</div>
          <div class="history-service">基础配种 1h · 内射</div>
        </div>
        <div class="history-rating">★ 5.0</div>
      </div>
      <div class="history-item">
        <div class="history-date">2025-07-05</div>
        <div>
          <div class="history-alpha">Alpha <b>#A-0512</b> · 金卡</div>
          <div class="history-service">多人服务 · 3 位 Alpha</div>
        </div>
        <div class="history-rating">★ 4.98</div>
      </div>
      <div class="history-item">
        <div class="history-date">2025-07-03</div>
        <div>
          <div class="history-alpha">Alpha <b>#A-0089</b> · 金卡 (回头客)</div>
          <div class="history-service">SM调教 · 项圈+扇耳光</div>
        </div>
        <div class="history-rating">★ 5.0</div>
      </div>
      <div class="history-item">
        <div class="history-date">2025-07-01</div>
        <div>
          <div class="history-alpha">Alpha <b>#A-0733</b> · 黑卡</div>
          <div class="history-service">过夜 · 校服Play · 拍摄</div>
        </div>
        <div class="history-rating">★ 5.0</div>
      </div>
      <div class="history-item">
        <div class="history-date">2025-06-28</div>
        <div>
          <div class="history-alpha">Alpha <b>#A-0417</b> · 银卡 (回头客)</div>
          <div class="history-service">深喉 + 颜射</div>
        </div>
        <div class="history-rating">★ 4.95</div>
      </div>
      <div class="history-item" style="opacity:0.6">
        <div class="history-date">......</div>
        <div><div class="history-alpha">还有 340 次记录</div><div class="history-service">点击查看完整历史</div></div>
        <div class="history-rating">→</div>
      </div>
    </div>

    <div class="block">
      <div class="block-title">— 闺蜜留言板 — <small>#F-2419 · 语晴</small></div>
      <div class="msg-item">
        <div class="msg-head"><span class="msg-user">💕 语晴（闺蜜）</span><span class="msg-time">2小时前</span></div>
        <div class="msg-text">"小彤加油❤ 今晚是黑卡Alpha哦，好好表现！我下班了过来给你拍视频～ 那个憨憨男朋友的份我也帮你剪一版哈哈哈"</div>
      </div>
      <div class="msg-item">
        <div class="msg-head"><span class="msg-user">💕 语晴（闺蜜）</span><span class="msg-time">昨天</span></div>
        <div class="msg-text">"你男朋友今天又给你发'宝宝晚安我爱你'的短信了嘛？哈哈哈他要是知道你昨晚被 #A-0089 内射两次...🤫"</div>
      </div>
      <div class="msg-item">
        <div class="msg-head"><span class="msg-user">💋 甜甜（#F-1892）</span><span class="msg-time">3天前</span></div>
        <div class="msg-text">"姐妹你评分冲到 4.98 啦！我羡慕死了。听说 KAI 大哥要来找你？他可是 S+ 啊，我上次接他给了 3 万小费"</div>
      </div>
      <div class="msg-item">
        <div class="msg-head"><span class="msg-user">💕 语晴（闺蜜）</span><span class="msg-time">1周前</span></div>
        <div class="msg-text">"我说小彤，你男朋友是不是傻的呀，你每周消失两三个晚上他都不问？他真的以为你在'补习'？😂"</div>
      </div>
    </div>
  </div>

  <!-- ========== 私信 & Beta 通知 ========== -->
  <div class="grid-2" style="grid-template-columns: 1fr 1fr;">
    <div class="block">
      <div class="block-title">— 与 KAI 的私信 — <small>本次预约前沟通</small></div>
      <div class="chat-window">
        <div class="chat-flex">
          <div class="chat-msg chat-from-me">小彤宝贝，晚上让你男朋友滚远点。今晚我要玩一整晚。</div>
          <div class="chat-time" style="text-align:right">今天 15:32</div>

          <div class="chat-msg chat-from-her">好呀叔叔❤ 我已经跟他说要跟同学去补习了 他相信了 每次都相信 🤭</div>
          <div class="chat-time">今天 15:34</div>

          <div class="chat-msg chat-from-me">今晚不戴套。要给你灌满。</div>
          <div class="chat-time" style="text-align:right">今天 15:35</div>

          <div class="chat-msg chat-from-her">嗯...好嘛 反正吃药就行～ 我不能怀孕 会被我男朋友发现 但是叔叔如果想让我怀 我也...可以考虑😳</div>
          <div class="chat-time">今天 15:36</div>

          <div class="chat-msg chat-from-me">乖。JK校服穿好，跟上次一样。</div>
          <div class="chat-time" style="text-align:right">今天 15:38</div>

          <div class="chat-msg chat-from-her">好嘛！那件校服还是我男朋友帮我熨的呢 他不知道我穿它接过 27 次客了 🤣</div>
          <div class="chat-time">今天 15:40</div>

          <div class="chat-msg chat-from-me">这次把视频剪一份发给他。让他也开开眼。</div>
          <div class="chat-time" style="text-align:right">今天 15:42</div>

          <div class="chat-msg chat-from-her">哈哈哈好啊 让他知道知道 什么才叫男人 💋</div>
          <div class="chat-time">今天 15:43</div>
        </div>
      </div>
      <div class="chat-input">
        <input type="text" placeholder="给小彤发消息..." id="chatInput">
        <button onclick="sendChat()">发送</button>
      </div>
    </div>

    <div class="block">
      <div class="block-title">— Beta 男通知记录 — <small>已向 #B-0620 发送</small></div>
      <div class="notice-item">
        <div>
          <div class="notice-info">📩 剪辑视频包 · 与 <b>#A-0089</b> 的过夜服务</div>
          <div class="notice-time">2025-07-12 08:23 · 邮箱送达</div>
        </div>
        <div class="notice-status status-read">已阅 · 查看6次</div>
      </div>
      <div class="notice-item">
        <div>
          <div class="notice-info">📩 剪辑视频包 · 与 <b>#A-0417</b> 的双穴开发</div>
          <div class="notice-time">2025-07-10 09:15 · 邮箱送达</div>
        </div>
        <div class="notice-status status-read">已阅 · 查看12次</div>
      </div>
      <div class="notice-item">
        <div>
          <div class="notice-info">📞 实时直播链接 · 多人服务场</div>
          <div class="notice-time">2025-07-05 22:00 · 短信送达</div>
        </div>
        <div class="notice-status status-read">已观看 · 全程4小时</div>
      </div>
      <div class="notice-item">
        <div>
          <div class="notice-info">🎤 闺蜜旁白包 · 语晴录制</div>
          <div class="notice-time">2025-07-03 14:00 · 邮箱送达</div>
        </div>
        <div class="notice-status status-read">已听 · 循环7次</div>
      </div>
      <div class="notice-item">
        <div>
          <div class="notice-info">🍼 育儿准备包（备用）</div>
          <div class="notice-time">2025-07-01 已寄出</div>
        </div>
        <div class="notice-status status-unread">未拆封</div>
      </div>
      <div class="notice-item">
        <div>
          <div class="notice-info">📩 本次预约通知 · 与 <b>#A-0007 KAI</b></div>
          <div class="notice-time">刚刚 · 邮箱送达</div>
        </div>
        <div class="notice-status status-unread">未读</div>
      </div>
      <div style="text-align:center;margin-top:15px;padding-top:15px;border-top:1px dashed rgba(255,255,255,0.06);color:#666;font-size:12px">
        累计通知次数: <b style="color:#FF3E7F;font-family:'JetBrains Mono',monospace">89</b> · 已阅率: <b style="color:#4ade80">100%</b>
      </div>
    </div>
  </div>

  <!-- ========== 留言给她 ========== -->
  <div class="block">
    <div class="block-title">— 服务前留言 · 给小彤 —</div>
    <div class="leave-msg">
      <textarea placeholder="给小彤留下您希望的特别要求..." id="leaveMsg">今晚JK校服，戴项圈。见面第一句话说"叔叔今天好想你"。全程叫我叔叔，禁止叫任何别的称呼——包括你男朋友的名字。做完之后，帮我给你男朋友发条'晚安宝宝，我爱你'。</textarea>
      <div class="leave-msg-actions">
        <span class="leave-msg-hint">✓ 已确认 · 此留言将同步发给她的手机</span>
        <button onclick="showToast('已发送','小彤已回复：好嘛叔叔❤')">发 送 →</button>
      </div>
    </div>
  </div>

</div>

<!-- ============ FOOTER ============ -->
<div class="footer-actions">
  <div class="footer-title">"她的男朋友配不上她。但你可以。"</div>
  <div class="footer-buttons">
    <button class="fbtn fbtn-primary" onclick="showToast('已锁定','该时段已被您独占')">🔒 锁定后续 7 天</button>
    <button class="fbtn fbtn-secondary" onclick="showToast('已添加','小彤已加入您的专属收藏')">⭐ 加入专属收藏</button>
    <button class="fbtn fbtn-secondary" onclick="showToast('已购买','育儿准备包将寄至 Beta #B-0620')">🍼 购买育儿准备包 · ¥3,000</button>
    <button class="fbtn fbtn-secondary" onclick="showToast('已购买','DNA意外揭示已排期')">🧬 预约 DNA 意外揭示 · ¥5,000</button>
  </div>
  <div class="footer-note">© 2021—2025 RENT-A-GIRLFRIEND · ORDER #RAG-20250712-A0007-F2418 · CONFIDENTIAL</div>
</div>

<!-- ============ TOAST ============ -->
<div class="toast" id="toast">
  <div class="toast-t" id="toastT">通知</div>
  <div id="toastM">操作成功</div>
</div>

<script>
  // 倒计时（到今晚 20:00）
  function updateCountdown() {
    const now = new Date();
    const target = new Date();
    target.setHours(20, 0, 0, 0);
    if (target < now) target.setDate(target.getDate() + 1);
    const diff = target - now;
    const h = Math.floor(diff / 3600000);
    const m = Math.floor((diff % 3600000) / 60000);
    const s = Math.floor((diff % 60000) / 1000);
    document.getElementById('cd-h').textContent = String(h).padStart(2,'0');
    document.getElementById('cd-m').textContent = String(m).padStart(2,'0');
    document.getElementById('cd-s').textContent = String(s).padStart(2,'0');
  }
  updateCountdown();
  setInterval(updateCountdown, 1000);

  // Toast
  let toastTimer;
  function showToast(t, m) {
    document.getElementById('toastT').textContent = t;
    document.getElementById('toastM').textContent = m;
    const el = document.getElementById('toast');
    el.classList.add('show');
    clearTimeout(toastTimer);
    toastTimer = setTimeout(() => el.classList.remove('show'), 3500);
  }

  // 聊天发送
  function sendChat() {
    const input = document.getElementById('chatInput');
    const val = input.value.trim();
    if (!val) return;
    const win = document.querySelector('.chat-window .chat-flex');
    const now = new Date();
    const time = now.getHours().toString().padStart(2,'0') + ':' + now.getMinutes().toString().padStart(2,'0');

    const msg = document.createElement('div');
    msg.className = 'chat-msg chat-from-me';
    msg.textContent = val;
    win.appendChild(msg);

    const t = document.createElement('div');
    t.className = 'chat-time';
    t.style.textAlign = 'right';
    t.textContent = '刚刚 ' + time;
    win.appendChild(t);

    input.value = '';
    win.parentElement.scrollTop = win.parentElement.scrollHeight;

    // 女友自动回复
    setTimeout(() => {
      const replies = ['好呀叔叔❤','嗯...听叔叔的🥺','我知道啦～','好嘛好嘛😽','叔叔说什么都对💋'];
      const reply = document.createElement('div');
      reply.className = 'chat-msg chat-from-her';
      reply.textContent = replies[Math.floor(Math.random()*replies.length)];
      win.appendChild(reply);

      const rt = document.createElement('div');
      rt.className = 'chat-time';
      rt.textContent = '刚刚';
      win.appendChild(rt);
      win.parentElement.scrollTop = win.parentElement.scrollHeight;
    }, 800);
  }
  document.getElementById('chatInput').addEventListener('keypress', e => { if (e.key === 'Enter') sendChat(); });
</script>

</body>
</html>
