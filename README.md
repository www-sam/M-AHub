<!DOCTYPE html>
<html lang="en">
<head><meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0"><title>M&A Hub - Global M&A Intelligence Platform</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&family=JetBrains+Mono:wght@400;500;600&family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
* { margin:0; padding:0; box-sizing:border-box; }
:root {
    --bg-primary:#ffffff; --bg-secondary:#f8f9fa; --bg-tertiary:#f0f2f5;
    --text-primary:#1a1a2e; --text-secondary:#4a4a6a; --text-tertiary:#7a7a8a;
    --border-color:#e0e0e0; --accent-gold:#c9a84c; --accent-gold-dim:#8b7a3a;
    --accent-green:#4caf7d; --accent-red:#cf4444; --accent-blue:#4a8fc1;
    --accent-purple:#7c3aed;
    --shadow-sm:0 2px 8px rgba(0,0,0,0.08); --shadow-md:0 4px 16px rgba(0,0,0,0.12); --shadow-lg:0 8px 32px rgba(0,0,0,0.15);
}
:root.dark-mode {
    --bg-primary:#0a0a0f; --bg-secondary:#15151d; --bg-tertiary:#1f1f2a;
    --text-primary:#e8e8f0; --text-secondary:#b8b8c8; --text-tertiary:#7a7a8a;
    --border-color:#2a2a35;
    --shadow-sm:0 2px 8px rgba(0,0,0,0.3); --shadow-md:0 4px 16px rgba(0,0,0,0.4); --shadow-lg:0 8px 32px rgba(0,0,0,0.5);
}
html,body{width:100%;height:100%;}
body{background:var(--bg-primary);color:var(--text-primary);font-family:'Poppins',-apple-system,BlinkMacSystemFont,'Segoe UI',sans-serif;line-height:1.6;overflow-x:hidden;transition:background-color .3s ease,color .3s ease;}

/* ─ Skeleton Loading States ─ */
@keyframes shimmer{0%{background-position:-400px 0}100%{background-position:400px 0}}
.skeleton-row{height:48px;border-radius:8px;margin-bottom:.75rem;background:linear-gradient(90deg,var(--bg-secondary) 25%,var(--bg-tertiary) 50%,var(--bg-secondary) 75%);background-size:800px 100%;animation:shimmer 1.5s infinite linear;}
.skeleton-card{height:140px;border-radius:12px;background:linear-gradient(90deg,var(--bg-secondary) 25%,var(--bg-tertiary) 50%,var(--bg-secondary) 75%);background-size:800px 100%;animation:shimmer 1.5s infinite linear;}
.skeleton-table-rows .skeleton-row{height:52px;}

/* ─ Data Source Tags ─ */
.data-source-tag{display:inline-flex;align-items:center;gap:.5rem;font-size:.72rem;color:var(--text-secondary);background:var(--bg-secondary);border:1px solid var(--border-color);padding:.5rem 1rem;border-radius:20px;margin-top:1rem;font-weight:500;}
.data-source-inline{font-size:.72rem;color:var(--text-secondary);margin-bottom:.5rem;font-style:italic;}
.section-label-gold{font-size:.75rem;letter-spacing:.15em;text-transform:uppercase;color:var(--accent-gold);margin-bottom:1.25rem;font-weight:700;}
.footer-disclaimer{font-size:.7rem;color:var(--text-tertiary);margin-top:.35rem;font-style:italic;}

/* ─ Nav ─ */
nav{position:fixed;top:0;left:0;right:0;background:rgba(255,255,255,.95);backdrop-filter:blur(10px);border-bottom:1px solid var(--border-color);padding:1rem 2rem;display:flex;justify-content:space-between;align-items:center;z-index:1000;height:70px;box-shadow:var(--shadow-sm);transition:all .3s ease;}
.dark-mode nav{background:rgba(10,10,15,.95);}
.nav-left{display:flex;align-items:center;gap:1.5rem;}
.nav-back-btn{display:none;background:none;border:none;color:var(--text-primary);font-size:1.5rem;cursor:pointer;transition:color .2s;padding:.5rem;}
.nav-back-btn:hover{color:var(--accent-gold);}
.nav-back-btn.visible{display:block;}
.nav-logo{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.5rem;font-weight:800;color:var(--text-primary);letter-spacing:-.02em;text-decoration:none;cursor:pointer;}
.nav-logo span{color:var(--accent-gold);}
.nav-center{display:flex;gap:2.5rem;list-style:none;}
.nav-center a{color:var(--text-secondary);text-decoration:none;font-size:.9rem;font-weight:500;transition:color .2s;cursor:pointer;}
.nav-center a:hover,.nav-center a.active{color:var(--accent-gold);}
.nav-right{display:flex;gap:1.5rem;align-items:center;}
.theme-toggle{background:var(--bg-secondary);border:1px solid var(--border-color);color:var(--text-primary);border-radius:50%;width:40px;height:40px;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:1.2rem;transition:all .2s;}
.theme-toggle:hover{background:var(--accent-gold);color:white;border-color:var(--accent-gold);}
.btn-access{background:linear-gradient(135deg,var(--accent-gold) 0%,#d4af57 100%);color:white;border:none;padding:.7rem 1.5rem;border-radius:6px;font-weight:600;font-size:.9rem;cursor:pointer;transition:all .3s;box-shadow:var(--shadow-sm);}
.btn-access:hover{transform:translateY(-2px);box-shadow:var(--shadow-md);}

/* ─ Ticker ─ */
.ticker{position:fixed;top:70px;left:0;right:0;background:var(--bg-secondary);border-bottom:2px solid var(--accent-gold);padding:.75rem 0;overflow:hidden;z-index:999;height:50px;display:flex;align-items:center;box-shadow:var(--shadow-sm);}
.ticker-label{padding:0 1.5rem;color:var(--accent-gold);font-weight:700;font-size:.75rem;letter-spacing:.15em;white-space:nowrap;border-right:2px solid var(--accent-gold);font-family:'JetBrains Mono',monospace;background:var(--bg-secondary);position:relative;z-index:10;height:100%;display:flex;align-items:center;}
.ticker-content{display:flex;gap:3rem;animation:scroll 60s linear infinite;padding:0 1.5rem;white-space:nowrap;}
@keyframes scroll{0%{transform:translateX(0);}100%{transform:translateX(-50%);}}
.ticker-item{display:flex;gap:.75rem;font-size:.8rem;font-family:'JetBrains Mono',monospace;font-weight:500;}
.ticker-item .symbol{color:var(--accent-gold);font-weight:700;}
.ticker-item .price{color:var(--text-primary);}
.ticker-item.up .change{color:var(--accent-green);}
.ticker-item.dn .change{color:var(--accent-red);}

/* ─ Main ─ */
main{margin-top:120px;min-height:calc(100vh - 120px);}
.section{display:none;animation:fadeSection .4s ease;}
.section.active{display:block;}
@keyframes fadeSection{from{opacity:0;transform:translateY(10px);}to{opacity:1;transform:translateY(0);}}

/* ─ Landing ─ */
.landing-page{min-height:100vh;display:flex;flex-direction:column;justify-content:center;align-items:center;padding:2rem;background:linear-gradient(135deg,var(--bg-primary) 0%,var(--bg-secondary) 100%);}
.landing-hero{text-align:center;margin-bottom:4rem;animation:slideUp .6s ease;}
@keyframes slideUp{from{opacity:0;transform:translateY(30px);}to{opacity:1;transform:translateY(0);}}
.landing-hero h1{font-family:'Plus Jakarta Sans',sans-serif;font-size:4rem;font-weight:800;color:var(--text-primary);margin-bottom:1rem;letter-spacing:-.03em;line-height:1.2;}
.landing-hero h1 span{background:linear-gradient(135deg,var(--accent-gold) 0%,var(--accent-purple) 100%);-webkit-background-clip:text;-webkit-text-fill-color:transparent;background-clip:text;}
.landing-hero p{font-size:1.2rem;color:var(--text-secondary);margin-bottom:1rem;max-width:600px;margin-left:auto;margin-right:auto;line-height:1.8;}
.landing-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:2rem;margin-bottom:4rem;max-width:900px;margin-left:auto;margin-right:auto;}
.stat-card{background:var(--bg-secondary);padding:2rem;border-radius:12px;border:1px solid var(--border-color);text-align:center;transition:all .3s;}
.stat-card:hover{transform:translateY(-5px);box-shadow:var(--shadow-md);border-color:var(--accent-gold);}
.stat-card-num{font-family:'Plus Jakarta Sans',sans-serif;font-size:2.5rem;font-weight:800;color:var(--accent-gold);margin-bottom:.5rem;}
.stat-card-label{font-size:.9rem;color:var(--text-secondary);font-weight:500;}
.landing-cta{display:grid;grid-template-columns:repeat(2,1fr);gap:2rem;max-width:900px;margin-left:auto;margin-right:auto;}
.cta-card{background:var(--bg-secondary);border:2px solid var(--border-color);border-radius:12px;padding:3rem 2rem;text-align:center;cursor:pointer;transition:all .3s;position:relative;overflow:hidden;}
.cta-card::before{content:'';position:absolute;top:0;left:-100%;width:100%;height:100%;background:linear-gradient(90deg,transparent,rgba(201,168,76,.1),transparent);transition:left .5s;}
.cta-card:hover::before{left:100%;}
.cta-card:hover{border-color:var(--accent-gold);transform:translateY(-8px);box-shadow:var(--shadow-lg);}
.cta-icon{font-size:4rem;margin-bottom:1rem;}
.cta-title{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.8rem;font-weight:800;color:var(--text-primary);margin-bottom:.75rem;}
.cta-desc{color:var(--text-secondary);font-size:.95rem;line-height:1.7;margin-bottom:1.5rem;}
.cta-btn{background:linear-gradient(135deg,var(--accent-gold) 0%,#d4af57 100%);color:white;border:none;padding:1rem 2rem;border-radius:8px;font-weight:700;font-size:1rem;cursor:pointer;transition:all .3s;width:100%;}
.cta-btn:hover{transform:scale(1.05);box-shadow:var(--shadow-lg);}
/* ─ Section Content ─ */
.section-content{padding:2rem 4rem 4rem;max-width:1400px;margin:0 auto;}
.sec-eyebrow{font-size:.75rem;letter-spacing:.2em;text-transform:uppercase;color:var(--accent-gold);margin-bottom:.75rem;font-weight:700;}
.sec-title{font-family:'Plus Jakarta Sans',sans-serif;font-size:3.5rem;font-weight:800;color:var(--text-primary);letter-spacing:-.02em;margin-bottom:.75rem;}
.sec-title em{color:var(--accent-gold);font-style:normal;}
.sec-desc{color:var(--text-secondary);font-size:1rem;margin-bottom:2rem;max-width:700px;line-height:1.8;}
.divider{height:2px;background:linear-gradient(90deg,var(--border-color) 0%,transparent 100%);margin:2.5rem 0;}

/* ─ Stats Grid ─ */
.stats-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1.5rem;margin-bottom:2.5rem;}
.stat-box{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:12px;padding:2rem;display:flex;flex-direction:column;transition:all .3s;box-shadow:var(--shadow-sm);}
.stat-box:hover{border-color:var(--accent-gold);box-shadow:var(--shadow-md);transform:translateY(-4px);}
.stat-num{font-family:'Plus Jakarta Sans',sans-serif;font-size:2.5rem;font-weight:800;color:var(--accent-gold);letter-spacing:-.02em;}
.stat-label{font-size:.75rem;text-transform:uppercase;letter-spacing:.1em;color:var(--text-secondary);margin-top:.75rem;font-weight:600;}
.stat-change{font-size:.8rem;margin-top:.75rem;font-weight:600;}
.stat-change.up{color:var(--accent-green);}
.stat-change.dn{color:var(--accent-red);}

/* ─ Filter Bar ─ */
.filter-bar{display:flex;gap:1rem;margin-bottom:2rem;flex-wrap:wrap;}
.filter-bar input,.filter-bar select{background:var(--bg-secondary);border:1px solid var(--border-color);color:var(--text-primary);padding:.75rem 1rem;font-family:'JetBrains Mono',monospace;font-size:.85rem;outline:none;border-radius:6px;transition:all .2s;}
.filter-bar input:focus,.filter-bar select:focus{border-color:var(--accent-gold);box-shadow:0 0 0 3px rgba(201,168,76,.1);}
.filter-bar input{flex:1;min-width:250px;}

/* ─ Deals Table ─ */
.table-wrapper{border:1px solid var(--border-color);border-radius:12px;overflow:hidden;box-shadow:var(--shadow-sm);}
.deals-table{width:100%;border-collapse:collapse;font-size:.9rem;}
.deals-table thead{background:var(--bg-secondary);border-bottom:2px solid var(--border-color);}
.deals-table th{text-align:left;padding:1.25rem;font-weight:700;color:var(--text-primary);font-size:.8rem;letter-spacing:.08em;text-transform:uppercase;}
.deals-table td{padding:1.25rem;border-bottom:1px solid var(--border-color);}
.deals-table tbody tr{transition:all .2s;}
.deals-table tbody tr:hover{background:var(--bg-secondary);}
.deal-value{font-family:'JetBrains Mono',monospace;color:var(--accent-gold);font-weight:700;}
.deal-status{display:inline-block;padding:.4rem .8rem;font-size:.7rem;font-weight:700;border-radius:6px;letter-spacing:.05em;text-transform:uppercase;}
.deal-status.status-pending{background:rgba(201,168,76,.15);color:var(--accent-gold);}
.deal-status.status-closed{background:rgba(76,175,125,.15);color:var(--accent-green);}
.deal-status.status-rumored{background:rgba(122,122,138,.15);color:var(--text-secondary);}

/* ─ Deal Era Tabs ─ */
.deal-era-tabs{display:flex;gap:0;margin-bottom:2rem;border-bottom:2px solid var(--border-color);}
.deal-era-btn{background:none;border:none;color:var(--text-secondary);padding:1.25rem 1.75rem;font-size:.95rem;cursor:pointer;border-bottom:3px solid transparent;transition:all .2s;display:flex;align-items:center;gap:.75rem;font-weight:600;}
.deal-era-btn.active{color:var(--accent-gold);border-bottom-color:var(--accent-gold);}
.era-dot{width:10px;height:10px;border-radius:50%;}
.era-dot.present-dot{background:var(--accent-gold);}
.era-dot.past-dot{background:var(--accent-green);}
.era-dot.future-dot{background:var(--accent-blue);}

/* ─ Sector Tabs ─ */
.sector-tabs{display:flex;gap:.75rem;margin-bottom:2rem;flex-wrap:wrap;}
.sector-tab{background:var(--bg-secondary);border:1px solid var(--border-color);color:var(--text-secondary);padding:.7rem 1.25rem;font-size:.85rem;cursor:pointer;transition:all .2s;border-radius:8px;font-weight:600;}
.sector-tab:hover{border-color:var(--accent-gold);color:var(--accent-gold);}
.sector-tab.active{background:linear-gradient(135deg,var(--accent-gold) 0%,#d4af57 100%);color:white;border-color:var(--accent-gold);}

/* ─ Company Cards ─ */
.company-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(330px,1fr));gap:1.25rem;margin-bottom:2.5rem;}
.company-card{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:14px;padding:0;transition:all .28s cubic-bezier(.4,0,.2,1);position:relative;overflow:hidden;box-shadow:var(--shadow-sm);display:flex;flex-direction:column;}
.company-card:hover{border-color:var(--accent-gold);box-shadow:0 8px 32px rgba(201,168,76,.18);transform:translateY(-4px);}
.card-top-bar{height:3px;background:linear-gradient(90deg,var(--accent-gold),var(--accent-purple));width:0;transition:width .35s ease;}
.company-card:hover .card-top-bar{width:100%;}
.co-header{display:flex;justify-content:space-between;align-items:flex-start;padding:1.25rem 1.5rem .75rem;}
.co-identity{flex:1;min-width:0;}
.co-ticker-row{display:flex;align-items:center;gap:.5rem;margin-bottom:.3rem;}
.co-ticker{font-family:'JetBrains Mono',monospace;font-size:.72rem;font-weight:700;color:var(--accent-gold);background:rgba(201,168,76,.12);padding:.18rem .55rem;border-radius:5px;letter-spacing:.06em;}
.co-exchange{font-family:'JetBrains Mono',monospace;font-size:.65rem;color:var(--text-secondary);}
.co-name{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.05rem;font-weight:800;color:var(--text-primary);line-height:1.2;}
.co-country{font-size:.72rem;color:var(--text-secondary);margin-top:.2rem;}
.co-price-block{text-align:right;flex-shrink:0;}
.co-price-val{font-family:'JetBrains Mono',monospace;font-size:1.45rem;font-weight:700;line-height:1;transition:color .3s;}
.co-price-val.up{color:var(--accent-green);}
.co-price-val.dn{color:var(--accent-red);}
.co-price-chg{display:inline-flex;align-items:center;gap:.25rem;font-size:.75rem;font-weight:700;margin-top:.3rem;padding:.18rem .55rem;border-radius:20px;}
.co-price-chg.up{background:rgba(76,175,125,.15);color:var(--accent-green);}
.co-price-chg.dn{background:rgba(239,68,68,.15);color:var(--accent-red);}
@keyframes priceFlash{0%,100%{opacity:1}50%{opacity:.3}}
.co-price-flash{animation:priceFlash .4s ease;}
.co-sparkline{padding:0 1.5rem;height:52px;}
.co-sparkline svg{width:100%;height:52px;display:block;}
.co-stats-row{display:grid;grid-template-columns:1fr 1fr 1fr;gap:0;margin:0;padding:.75rem 0;border-top:1px solid var(--border-color);border-bottom:1px solid var(--border-color);}
.co-stat{text-align:center;padding:.4rem .5rem;border-right:1px solid var(--border-color);}
.co-stat:last-child{border-right:none;}
.co-stat-val{font-family:'JetBrains Mono',monospace;font-size:.82rem;font-weight:700;color:var(--text-primary);}
.co-stat-lbl{font-size:.58rem;text-transform:uppercase;letter-spacing:.09em;color:var(--text-secondary);margin-top:.15rem;font-weight:700;}
.co-week-range{padding:.75rem 1.5rem 0;}
.co-week-labels{display:flex;justify-content:space-between;font-size:.62rem;color:var(--text-secondary);margin-bottom:.35rem;font-family:'JetBrains Mono',monospace;}
.co-week-bar{height:4px;background:var(--bg-tertiary);border-radius:2px;position:relative;}
.co-week-fill{height:100%;background:linear-gradient(90deg,rgba(201,168,76,.4),var(--accent-gold));border-radius:2px;}
.co-week-dot{position:absolute;top:50%;transform:translate(-50%,-50%);width:10px;height:10px;background:var(--accent-gold);border:2px solid var(--bg-primary);border-radius:50%;box-shadow:0 0 6px rgba(201,168,76,.7);}
.co-badges{display:flex;gap:.4rem;flex-wrap:wrap;padding:.75rem 1.5rem;}
.badge{display:inline-block;background:rgba(201,168,76,.12);color:var(--accent-gold);padding:.25rem .6rem;font-size:.65rem;border-radius:5px;font-weight:700;letter-spacing:.04em;}
.badge-dim{background:rgba(122,122,138,.1);color:var(--text-secondary);}
.co-desc{font-size:.8rem;color:var(--text-secondary);line-height:1.65;padding:0 1.5rem 1rem;flex:1;}
.co-cta{display:flex;align-items:center;justify-content:space-between;padding:.85rem 1.5rem;border-top:1px solid var(--border-color);font-size:.72rem;color:var(--accent-gold);font-weight:700;cursor:pointer;transition:all .2s;text-transform:uppercase;letter-spacing:.08em;}
.co-cta:hover{background:rgba(201,168,76,.06);}
.co-cta-live{display:flex;align-items:center;gap:.35rem;font-size:.65rem;font-weight:700;color:var(--accent-green);}
.live-dot{width:6px;height:6px;background:var(--accent-green);border-radius:50%;animation:pulse 1.5s infinite;}

/* ─ Region Cards ─ */
.three-col{display:grid;grid-template-columns:repeat(3,1fr);gap:1.5rem;margin-bottom:2.5rem;}
.region-card{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:12px;padding:1.75rem;position:relative;overflow:hidden;transition:all .3s;box-shadow:var(--shadow-sm);}
.region-card:hover{border-color:var(--accent-gold);box-shadow:var(--shadow-md);transform:translateY(-6px);}
.region-header{display:flex;align-items:flex-start;gap:1rem;margin-bottom:1rem;}
.region-flag{font-size:2.5rem;flex-shrink:0;}
.region-header-body{flex:1;}
.region-name{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.2rem;font-weight:800;color:var(--text-primary);margin-bottom:.2rem;}
.region-vol{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.5rem;font-weight:800;color:var(--accent-gold);}
.region-yoy{font-size:.8rem;font-weight:700;margin-top:.25rem;}
.region-stats{display:flex;align-items:center;justify-content:space-between;margin-bottom:1rem;}
.region-deals{font-size:.8rem;color:var(--text-secondary);font-weight:600;}
.region-tags{display:flex;gap:.4rem;flex-wrap:wrap;}
.region-desc{font-size:.8rem;color:var(--text-secondary);line-height:1.65;}

/* ─ Alerts ─ */
.alerts-container{display:flex;flex-direction:column;gap:.75rem;margin-bottom:2.5rem;}
.alert-item{display:flex;gap:1rem;align-items:flex-start;padding:1rem 1.25rem;background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:8px;font-size:.85rem;transition:all .2s;}
.alert-item:hover{border-color:var(--accent-gold);box-shadow:var(--shadow-sm);}
.alert-tag{font-weight:700;font-size:.75rem;white-space:nowrap;background:rgba(201,168,76,.15);color:var(--accent-gold);padding:.35rem .75rem;border-radius:4px;text-transform:uppercase;letter-spacing:.05em;}
.alert-text{color:var(--text-secondary);line-height:1.6;}

/* ─ Signal Cards ─ */
.signal-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:1.5rem;}
.signal-card{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:12px;padding:2rem;position:relative;overflow:hidden;transition:all .3s;box-shadow:var(--shadow-sm);}
.signal-card:hover{border-color:var(--accent-gold);box-shadow:var(--shadow-md);transform:translateY(-6px);}

/* ─ Analysis / Chat ─ */
.analysis-layout{display:grid;grid-template-columns:1fr 380px;gap:1.5rem;}
.chat-container{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:12px;display:flex;flex-direction:column;height:600px;box-shadow:var(--shadow-sm);overflow:hidden;}
.chat-header{padding:1.5rem;border-bottom:1px solid var(--border-color);display:flex;justify-content:space-between;align-items:center;background:var(--bg-tertiary);}
.chat-header-title{font-size:.75rem;letter-spacing:.15em;text-transform:uppercase;color:var(--text-secondary);font-weight:700;}
.chat-status{font-size:.75rem;color:var(--accent-green);font-weight:700;display:flex;align-items:center;gap:.5rem;}
.chat-status::before{content:'';width:8px;height:8px;background:var(--accent-green);border-radius:50%;animation:pulse 2s infinite;}
@keyframes pulse{0%,100%{opacity:1;}50%{opacity:.5;}}
.chat-messages{flex:1;overflow-y:auto;padding:1.5rem;display:flex;flex-direction:column;gap:1rem;}
.msg{display:flex;flex-direction:column;gap:.5rem;font-size:.85rem;line-height:1.6;}
.msg-ai{align-items:flex-start;}
.msg-user{align-items:flex-end;}
.msg-label{font-size:.7rem;letter-spacing:.08em;text-transform:uppercase;font-weight:700;color:var(--text-secondary);}
.msg-ai .msg-label{color:var(--accent-gold);}
.msg-ai>div:not(.msg-label){background:var(--bg-tertiary);padding:1rem;border-radius:8px;max-width:90%;color:var(--text-secondary);}
.msg-user>div:not(.msg-label){background:linear-gradient(135deg,var(--accent-gold) 0%,#d4af57 100%);padding:1rem;border-radius:8px;max-width:90%;color:white;}
.typing-indicator span{display:inline-block;width:6px;height:6px;background:var(--accent-gold);border-radius:50%;margin:0 2px;animation:typingBounce 1.2s infinite;}
.typing-indicator span:nth-child(2){animation-delay:.2s;}
.typing-indicator span:nth-child(3){animation-delay:.4s;}
@keyframes typingBounce{0%,80%,100%{transform:translateY(0);}40%{transform:translateY(-8px);}}
.chat-input-row{display:flex;gap:.75rem;padding:1.25rem;border-top:1px solid var(--border-color);background:var(--bg-tertiary);}
.chat-input{flex:1;background:var(--bg-secondary);border:1px solid var(--border-color);color:var(--text-primary);padding:.75rem 1rem;font-family:'Poppins',sans-serif;font-size:.85rem;outline:none;border-radius:6px;transition:all .2s;}
.chat-input:focus{border-color:var(--accent-gold);box-shadow:0 0 0 3px rgba(201,168,76,.1);}
.chat-send{background:linear-gradient(135deg,var(--accent-gold) 0%,#d4af57 100%);color:white;border:none;padding:.75rem 1.5rem;font-weight:700;font-size:.8rem;cursor:pointer;transition:all .2s;border-radius:6px;text-transform:uppercase;letter-spacing:.05em;}
.chat-send:hover{transform:translateY(-2px);box-shadow:var(--shadow-md);}
.chat-send:disabled{opacity:.5;cursor:not-allowed;transform:none;}
.quick-queries{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:12px;padding:1.5rem;box-shadow:var(--shadow-sm);}
.quick-label{font-size:.75rem;letter-spacing:.15em;text-transform:uppercase;color:var(--accent-gold);margin-bottom:1rem;font-weight:700;}
.quick-btns{display:flex;flex-direction:column;gap:.75rem;}
.quick-btn{background:var(--bg-tertiary);border:1px solid var(--border-color);color:var(--text-secondary);padding:.75rem 1rem;font-size:.75rem;text-align:left;cursor:pointer;transition:all .2s;border-radius:6px;line-height:1.5;font-weight:500;}
.quick-btn:hover{border-color:var(--accent-gold);background:var(--bg-secondary);color:var(--accent-gold);}
.card{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:12px;padding:1.5rem;box-shadow:var(--shadow-sm);}

/* ─ Make Deals Sectors ─ */
.md-sector-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(280px,1fr));gap:1.5rem;margin-bottom:2.5rem;}
.md-sector-card{background:var(--bg-secondary);border:2px solid var(--border-color);border-radius:12px;padding:2rem;cursor:pointer;position:relative;overflow:hidden;transition:all .3s;box-shadow:var(--shadow-sm);}
.md-sector-card:hover{border-color:var(--accent-gold);background:var(--bg-tertiary);box-shadow:var(--shadow-md);transform:translateY(-6px);}
.md-sector-icon{font-size:3rem;margin-bottom:1rem;}
.md-sector-title{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.3rem;font-weight:800;color:var(--text-primary);margin-bottom:.35rem;}
.md-sector-sub{font-size:.8rem;color:var(--text-secondary);margin-bottom:1.25rem;line-height:1.6;}
.md-sector-stats{display:grid;grid-template-columns:1fr 1fr;gap:1rem;padding-top:1.25rem;border-top:1px solid var(--border-color);}
.md-sector-stat-num{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.2rem;font-weight:800;}
.md-sector-stat-lbl{font-size:.7rem;text-transform:uppercase;letter-spacing:.08em;color:var(--text-secondary);margin-top:.35rem;font-weight:600;}

/* ─ Deal Type Buttons ─ */
.deal-type-row{display:flex;gap:1.5rem;margin-bottom:3rem;justify-content:center;flex-wrap:wrap;}
.deal-type-btn{display:flex;flex-direction:column;align-items:center;gap:.75rem;padding:2rem 3.5rem;border-radius:16px;font-family:'Plus Jakarta Sans',sans-serif;font-size:1.5rem;font-weight:800;cursor:pointer;transition:all .35s cubic-bezier(.34,1.56,.64,1);letter-spacing:-.01em;position:relative;overflow:hidden;min-width:240px;border:none;}
.deal-type-btn:hover{transform:translateY(-8px) scale(1.03);}
.deal-type-btn .btn-icon{font-size:2.8rem;}
.deal-type-btn .btn-sub{font-size:.8rem;font-weight:500;letter-spacing:.05em;opacity:.85;font-family:'Poppins',sans-serif;}
.btn-merger{background:linear-gradient(135deg,#c9a84c 0%,#e8c96a 50%,#b8932e 100%);color:#1a1200;box-shadow:0 8px 32px rgba(201,168,76,.45);}
.btn-merger:hover{box-shadow:0 16px 48px rgba(201,168,76,.6);}
.btn-acquisition{background:var(--bg-primary);color:var(--text-primary);border:2.5px solid var(--accent-gold)!important;box-shadow:0 4px 20px rgba(201,168,76,.2);}
.btn-acquisition:hover{background:var(--bg-secondary);box-shadow:0 12px 40px rgba(201,168,76,.35);}

/* ─ Modals ─ */
.modal-overlay{position:fixed;inset:0;background:rgba(0,0,0,.65);backdrop-filter:blur(6px);z-index:9000;display:flex;align-items:center;justify-content:center;opacity:0;pointer-events:none;transition:opacity .3s;}
.modal-overlay.open{opacity:1;pointer-events:all;}
.modal-box{background:var(--bg-primary);border:1px solid var(--border-color);border-radius:20px;width:92%;max-width:680px;max-height:88vh;overflow-y:auto;box-shadow:0 24px 80px rgba(0,0,0,.35);transform:translateY(30px) scale(.97);transition:transform .35s cubic-bezier(.34,1.56,.64,1);position:relative;}
.modal-overlay.open .modal-box{transform:translateY(0) scale(1);}
.modal-header{padding:2rem 2rem 1.25rem;border-bottom:1px solid var(--border-color);display:flex;justify-content:space-between;align-items:flex-start;position:sticky;top:0;background:var(--bg-primary);border-radius:20px 20px 0 0;z-index:2;}
.modal-close{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:50%;width:38px;height:38px;cursor:pointer;display:flex;align-items:center;justify-content:center;font-size:1.1rem;color:var(--text-secondary);transition:all .2s;flex-shrink:0;}
.modal-close:hover{background:var(--accent-red);color:white;border-color:var(--accent-red);}
.modal-badge{display:inline-block;font-size:.65rem;font-weight:800;letter-spacing:.15em;text-transform:uppercase;padding:.35rem .8rem;border-radius:20px;margin-bottom:.6rem;}
.badge-merger{background:linear-gradient(135deg,#c9a84c,#e8c96a);color:#1a1200;}
.badge-acquisition{background:rgba(201,168,76,.15);color:var(--accent-gold);border:1px solid var(--accent-gold);}
.modal-title{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.6rem;font-weight:800;color:var(--text-primary);letter-spacing:-.02em;}
.modal-subtitle{font-size:.85rem;color:var(--text-secondary);margin-top:.3rem;}
.modal-body{padding:1.75rem 2rem;}
.modal-step{display:none;}
.modal-step.active{display:block;animation:fadeSection .3s ease;}
.step-indicator{display:flex;gap:.5rem;margin-bottom:1.75rem;align-items:center;}
.step-dot{width:32px;height:6px;border-radius:3px;background:var(--border-color);transition:background .3s;}
.step-dot.done{background:var(--accent-gold);}
.step-label{font-size:.75rem;color:var(--text-secondary);margin-left:.5rem;font-weight:600;}
.form-group{margin-bottom:1.5rem;}
.form-label{display:block;font-size:.8rem;font-weight:700;text-transform:uppercase;letter-spacing:.1em;color:var(--text-secondary);margin-bottom:.6rem;}
.form-question{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.15rem;font-weight:700;color:var(--text-primary);margin-bottom:1rem;line-height:1.4;}
.option-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(145px,1fr));gap:.75rem;}
.option-pill{padding:.7rem .9rem;border:2px solid var(--border-color);border-radius:10px;text-align:center;cursor:pointer;font-size:.82rem;font-weight:600;color:var(--text-secondary);background:var(--bg-secondary);transition:all .2s;display:flex;flex-direction:column;align-items:center;gap:.35rem;}
.option-pill:hover{border-color:var(--accent-gold);color:var(--accent-gold);background:var(--bg-tertiary);}
.option-pill.selected{border-color:var(--accent-gold);background:rgba(201,168,76,.12);color:var(--accent-gold);}
.option-pill .pill-icon{font-size:1.5rem;}
.value-display{font-family:'Plus Jakarta Sans',sans-serif;font-size:2.2rem;font-weight:800;color:var(--accent-gold);text-align:center;margin-bottom:1rem;}
input[type=range]{-webkit-appearance:none;width:100%;height:6px;border-radius:3px;background:var(--border-color);outline:none;cursor:pointer;}
input[type=range]::-webkit-slider-thumb{-webkit-appearance:none;width:22px;height:22px;border-radius:50%;background:linear-gradient(135deg,#c9a84c,#e8c96a);cursor:pointer;box-shadow:0 2px 8px rgba(201,168,76,.5);}
.goal-grid{display:grid;grid-template-columns:1fr 1fr;gap:.75rem;}
.goal-card{padding:1rem;border:2px solid var(--border-color);border-radius:10px;cursor:pointer;transition:all .2s;background:var(--bg-secondary);}
.goal-card:hover{border-color:var(--accent-gold);}
.goal-card.selected{border-color:var(--accent-gold);background:rgba(201,168,76,.1);}
.goal-card-icon{font-size:1.6rem;margin-bottom:.4rem;}
.goal-card-title{font-size:.82rem;font-weight:700;color:var(--text-primary);}
.goal-card-desc{font-size:.72rem;color:var(--text-secondary);margin-top:.2rem;line-height:1.4;}
.modal-footer{padding:1.25rem 2rem 2rem;display:flex;gap:1rem;justify-content:flex-end;align-items:center;}
.modal-btn-back{background:none;border:1px solid var(--border-color);color:var(--text-secondary);padding:.85rem 1.75rem;border-radius:10px;font-weight:600;font-size:.9rem;cursor:pointer;transition:all .2s;}
.modal-btn-back:hover{border-color:var(--accent-gold);color:var(--accent-gold);}
.modal-btn-next{background:linear-gradient(135deg,#c9a84c 0%,#d4af57 100%);color:white;border:none;padding:.85rem 2rem;border-radius:10px;font-weight:700;font-size:.9rem;cursor:pointer;transition:all .25s;box-shadow:0 4px 16px rgba(201,168,76,.4);}
.modal-btn-next:hover{transform:translateY(-2px);box-shadow:0 8px 24px rgba(201,168,76,.5);}
.modal-btn-next:disabled{opacity:.4;cursor:not-allowed;transform:none;}

/* ─ Results ─ */
.results-header{background:linear-gradient(135deg,rgba(201,168,76,.12) 0%,rgba(124,58,237,.08) 100%);border:1px solid rgba(201,168,76,.3);border-radius:12px;padding:1.25rem 1.5rem;margin-bottom:1.5rem;display:flex;gap:1rem;align-items:center;}
.results-header-icon{font-size:2.2rem;}
.results-header-title{font-family:'Plus Jakarta Sans',sans-serif;font-size:1rem;font-weight:800;color:var(--text-primary);}
.results-header-sub{font-size:.78rem;color:var(--text-secondary);margin-top:.2rem;}
.result-card{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:12px;padding:1.25rem 1.5rem 1.25rem 2rem;margin-bottom:1rem;transition:all .25s;position:relative;overflow:hidden;}
.result-card::before{content:'';position:absolute;left:0;top:0;bottom:0;width:4px;}
.result-card.rank-1::before{background:linear-gradient(180deg,#c9a84c,#e8c96a);}
.result-card.rank-2::before{background:linear-gradient(180deg,#9ca3af,#d1d5db);}
.result-card.rank-3::before{background:linear-gradient(180deg,#b45309,#d97706);}
.result-card:hover{border-color:var(--accent-gold);transform:translateX(4px);box-shadow:var(--shadow-md);}
.result-rank{position:absolute;top:1rem;right:1.25rem;font-family:'JetBrains Mono',monospace;font-size:.7rem;font-weight:700;color:var(--text-secondary);}
.result-company{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.05rem;font-weight:800;color:var(--text-primary);}
.result-meta{font-size:.75rem;color:var(--text-secondary);margin-top:.2rem;margin-bottom:.75rem;}
.result-tags{display:flex;gap:.4rem;flex-wrap:wrap;margin-bottom:.75rem;}
.result-tag{font-size:.65rem;font-weight:700;padding:.2rem .6rem;border-radius:4px;}
.result-tag.fit{background:rgba(76,175,125,.15);color:var(--accent-green);}
.result-tag.value{background:rgba(201,168,76,.15);color:var(--accent-gold);}
.result-desc{font-size:.78rem;color:var(--text-secondary);line-height:1.65;}

/* ─ Sector Summary Bar ─ */
.sector-summary-bar{display:grid;grid-template-columns:repeat(4,1fr);gap:1rem;margin-bottom:2rem;}
.sector-sum-box{background:var(--bg-secondary);border:1px solid var(--border-color);border-radius:10px;padding:1rem 1.25rem;text-align:center;}
.sector-sum-val{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.3rem;font-weight:800;color:var(--accent-gold);}
.sector-sum-lbl{font-size:.67rem;text-transform:uppercase;letter-spacing:.08em;color:var(--text-secondary);margin-top:.25rem;font-weight:600;}
.live-badge{display:inline-flex;align-items:center;gap:.35rem;font-size:.65rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--accent-green);background:rgba(76,175,125,.12);border:1px solid rgba(76,175,125,.3);padding:.25rem .6rem;border-radius:20px;}
.live-badge::before{content:'';width:6px;height:6px;background:var(--accent-green);border-radius:50%;animation:pulse 1.5s infinite;}

/* ─ Footer ─ */
footer{background:var(--bg-secondary);border-top:1px solid var(--border-color);padding:3rem 4rem;margin-top:4rem;display:grid;grid-template-columns:1fr auto 1fr;gap:2rem;align-items:center;box-shadow:var(--shadow-sm);}
.footer-logo{font-family:'Plus Jakarta Sans',sans-serif;font-size:1.3rem;font-weight:800;color:var(--text-primary);}
.footer-logo span{color:var(--accent-gold);}
.footer-text{font-size:.85rem;color:var(--text-secondary);margin-top:.35rem;}
.footer-links{display:flex;gap:2.5rem;justify-content:center;}
.footer-links a{color:var(--text-secondary);text-decoration:none;font-size:.85rem;transition:color .2s;cursor:pointer;font-weight:500;}
.footer-links a:hover{color:var(--accent-gold);}

/* ─ Responsive ─ */
@media(max-width:1024px){.section-content{padding:2rem;}.stats-grid{grid-template-columns:repeat(2,1fr);}.three-col{grid-template-columns:1fr;}.analysis-layout{grid-template-columns:1fr;}.landing-cta{grid-template-columns:1fr;}.landing-stats{grid-template-columns:1fr;}footer{grid-template-columns:1fr;text-align:center;}.footer-links{flex-wrap:wrap;justify-content:center;}}
@media(max-width:768px){nav{padding:.75rem 1rem;height:auto;flex-wrap:wrap;gap:.5rem;}.nav-center{display:none;}.nav-logo{font-size:1.2rem;}.sec-title{font-size:2rem;}.landing-hero h1{font-size:2.5rem;}.stats-grid{grid-template-columns:1fr;}.company-grid{grid-template-columns:1fr;}.md-sector-grid{grid-template-columns:1fr;}.section-content{padding:1.5rem;}.deal-type-row{flex-direction:column;align-items:stretch;}.deal-type-btn{min-width:auto;}.sector-summary-bar{grid-template-columns:repeat(2,1fr);}.modal-box{width:98%;max-height:95vh;border-radius:12px;}.goal-grid{grid-template-columns:1fr;}}

</style>
</head>
<body>
<nav>
    <div class="nav-left">
        <button class="nav-back-btn" id="backBtn" onclick="goHome()">← Back</button>
        <a class="nav-logo" onclick="goHome()">M&A <span>Hub</span></a>
    </div>
    <ul class="nav-center" id="navLinks">
        <li><a onclick="showSection('deals')" class="active">Live Deals</a></li>
        <li><a onclick="showSection('sectors')">Sectors</a></li>
        <li><a onclick="showSection('regions')">Regions</a></li>
        <li><a onclick="showSection('analysis')">Analysis</a></li>
        <li><a onclick="showSection('intelligence')">Intelligence</a></li>
    </ul>
    <div class="nav-right">
        <button class="theme-toggle" id="themeToggle" onclick="toggleTheme()">🌙</button>
        <button class="btn-access">Get Access</button>
    </div>
</nav>
<div class="ticker">
    <div class="ticker-label">LIVE M&A</div>
    <div class="ticker-content" id="tickerContent"></div>
</div>

<main>
    <!-- LANDING -->
    <div id="landing" class="section active">
        <div class="landing-page">
        <div class="landing-hero">
            <h1>Global <span>M&A Intelligence</span> Platform</h1>
                <p>Real-time deal flow, sector analysis, and AI-powered market intelligence for institutional investors and M&A professionals.</p>
                <div class="data-source-tag"><span class="live-dot"></span> Data sourced from public filings, SEC EDGAR, Bloomberg & Refinitiv · Last updated <span id="lastUpdated"></span></div>
            </div>
            <div class="landing-stats">
                <div class="stat-card"><div class="stat-card-num" id="animStat1">$2.1T</div><div class="stat-card-label">YTD Deal Volume 2025</div></div>
                <div class="stat-card"><div class="stat-card-num" id="animStat2">4,847</div><div class="stat-card-label">Deals This Quarter</div></div>
                <div class="stat-card"><div class="stat-card-num" id="animStat3">78</div><div class="stat-card-label">Mega-Deals (&gt;$5B)</div></div>
            </div>
            <div class="landing-cta">
                <div class="cta-card" onclick="showSection('deals')">
                    <div class="cta-icon">📊</div>
                    <div class="cta-title">Live Deals</div>
                    <p class="cta-desc">Explore real-time M&A transactions with advanced filtering by sector, region, and deal status.</p>
                    <button class="cta-btn">Explore Deals →</button>
                </div>
                <div class="cta-card" onclick="showSection('makedeals')">
                    <div class="cta-icon">🎯</div>
                    <div class="cta-title">Make Deals</div>
                    <p class="cta-desc">Build custom M&A transactions, analyze targets, and model acquisition scenarios.</p>
                    <button class="cta-btn">Start Building →</button>
                </div>
            </div>
            <div style="margin-top:2.5rem;">
                <div class="section-label-gold">Market Alerts</div>
                <div id="alertsList">
                    <div class="skeleton-row"></div><div class="skeleton-row"></div><div class="skeleton-row"></div>
                </div>
            </div>
            <div style="margin-top:2.5rem;">
                <div class="section-label-gold">M&amp;A Signals</div>
                <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:1.25rem;" id="signalCards">
                    <div class="skeleton-card"></div><div class="skeleton-card"></div><div class="skeleton-card"></div>
                </div>
            </div>
        </div>
    </div>

    <!-- DEALS -->
    <div id="deals" class="section">
        <div class="section-content">
            <div class="sec-eyebrow">Live Deal Flow</div>
            <h2 class="sec-title">Global <em>M&A Deals</em></h2>
            <p class="sec-desc">Complete coverage of past, present, and future mergers &amp; acquisitions across every sector and region worldwide.</p>
            <div class="data-source-inline">Data sourced from SEC, Bloomberg, Refinitiv &amp; public filings · Updated daily</div>
            <div class="divider"></div>
            <div class="stats-grid" id="statsGrid">
                <div class="skeleton-card"></div><div class="skeleton-card"></div><div class="skeleton-card"></div><div class="skeleton-card"></div>
            </div>
            <div class="deal-era-tabs">
                <button class="deal-era-btn active" onclick="switchEra(event,'present')"><span class="era-dot present-dot"></span> Present Deals</button>
                <button class="deal-era-btn" onclick="switchEra(event,'past')"><span class="era-dot past-dot"></span> Past Deals</button>
                <button class="deal-era-btn" onclick="switchEra(event,'future')"><span class="era-dot future-dot"></span> Future Deals</button>
            </div>
            <div class="filter-bar">
                <input type="text" id="dealSearch" placeholder="Search acquirer, target or sector..." onkeyup="filterDeals()">
                <select id="sectorFilter" onchange="filterDeals()">
                    <option value="">All Sectors</option>
                    <option>Technology</option><option>Healthcare</option><option>Energy</option>
                    <option>Finance</option><option>Consumer</option><option>Industrials</option>
                    <option>Real Estate</option><option>Media</option><option>Telecoms</option>
                    <option>Defense</option><option>Mining</option><option>Logistics</option>
                </select>
                <select id="regionFilter" onchange="filterDeals()">
                    <option value="">All Regions</option>
                    <option>North America</option><option>Europe</option><option>Asia Pacific</option>
                    <option>Middle East</option><option>Latin America</option><option>Africa</option><option>Global</option>
                </select>
            </div>
            <div class="table-wrapper">
                <table class="deals-table" id="dealsTable">
                    <thead><tr><th>#</th><th>Acquirer</th><th>Target</th><th>Deal Value</th><th>Sector</th><th>Region</th><th>Date</th><th>Type</th><th>Status</th></tr></thead>
                    <tbody id="dealsBody">
                        <tr><td colspan="9"><div class="skeleton-table-rows"><div class="skeleton-row"></div><div class="skeleton-row"></div><div class="skeleton-row"></div><div class="skeleton-row"></div><div class="skeleton-row"></div></div></td></tr>
                    </tbody>
                </table>
            </div>
            <div style="font-size:.8rem;color:var(--text-secondary);margin-top:1rem;text-align:right;" id="dealCount"></div>
        </div>
    </div>

    <!-- SECTORS -->
    <div id="sectors" class="section">
        <div class="section-content">
            <div class="sec-eyebrow">Sector Intelligence</div>
            <h2 class="sec-title">Live Market <em>Data</em></h2>
            <p class="sec-desc">Simulated prices and M&A profiles - updated live every few seconds for demonstration purposes.</p>
            <div class="data-source-inline">Share prices are simulated for demo · Sector data from public filings &amp; estimates</div>
            <div class="divider"></div>
            <div class="sector-tabs" id="sectorTabs"></div>
            <div id="sectorSummaryBar" class="sector-summary-bar" style="margin-top:1.5rem;"></div>
            <div class="company-grid" id="companyGrid"></div>
        </div>
    </div>

    <!-- REGIONS -->
    <div id="regions" class="section">
        <div class="section-content">
            <div class="sec-eyebrow">Regional Intelligence</div>
            <h2 class="sec-title">M&A by <em>Region</em></h2>
            <p class="sec-desc">Geographic breakdown of global M&A activity - deal volumes, regulatory environments, and strategic trends by region.</p>
            <div class="divider"></div>
            <div class="three-col" id="regionsGrid">
                <div class="skeleton-card" style="height:200px"></div><div class="skeleton-card" style="height:200px"></div><div class="skeleton-card" style="height:200px"></div>
            </div>
            <div style="margin-bottom:2.5rem;">
                <div class="section-label-gold">Live Alerts &amp; Updates</div>
                <div class="alerts-container" id="alertsContainer">
                    <div class="skeleton-row"></div><div class="skeleton-row"></div>
                </div>
            </div>
            <div class="signal-grid" id="signalsGrid">
                <div class="skeleton-card"></div><div class="skeleton-card"></div>
            </div>
        </div>
    </div>

    <!-- ANALYSIS -->
    <div id="analysis" class="section">
        <div class="section-content">
            <div class="sec-eyebrow">AI Deal Intelligence</div>
            <h2 class="sec-title">M&A <em>Analysis</em></h2>
            <p class="sec-desc">AI-powered M&A analysis assistant - ask anything about global deal flow, valuations, regulatory risk, or sector trends.</p>
            <div class="divider"></div>
            <div class="analysis-layout">
                <div class="chat-container">
                    <div class="chat-header">
                        <div class="chat-header-title">M&A INTELLIGENCE ENGINE · AI ASSISTANT</div>
                        <div class="chat-status">Online</div>
                    </div>
                    <div class="chat-messages" id="chatMessages"></div>
                    <div class="chat-input-row">
                        <input type="text" class="chat-input" id="chatInput" placeholder="Ask about deals, sectors, valuations..." onkeydown="if(event.key==='Enter')sendMessage()">
                        <button class="chat-send" id="sendBtn" onclick="sendMessage()">SEND</button>
                    </div>
                </div>
                <div>
                    <div class="quick-queries">
                        <div class="quick-label">Quick Queries</div>
                        <div class="quick-btns" id="quickBtns"></div>
                    </div>
                    <div class="card" style="margin-top:1rem;">
                        <div class="section-label-gold" style="margin-bottom:1rem;">Intelligence Capabilities</div>
                        <div style="display:flex;gap:.75rem;padding:.75rem 0;border-bottom:1px solid var(--border-color);"><span style="font-size:1.2rem;">📊</span><div><div style="font-size:.85rem;font-weight:700;color:var(--text-primary);">Deal Screening</div><div style="font-size:.75rem;color:var(--text-secondary);margin-top:.2rem;">Filter by sector, region, size, and status</div></div></div>
                        <div style="display:flex;gap:.75rem;padding:.75rem 0;border-bottom:1px solid var(--border-color);"><span style="font-size:1.2rem;">⚖️</span><div><div style="font-size:.85rem;font-weight:700;color:var(--text-primary);">Regulatory Analysis</div><div style="font-size:.75rem;color:var(--text-secondary);margin-top:.2rem;">DOJ, FTC, EU CMA risk assessment</div></div></div>
                        <div style="display:flex;gap:.75rem;padding:.75rem 0;border-bottom:1px solid var(--border-color);"><span style="font-size:1.2rem;">💰</span><div><div style="font-size:.85rem;font-weight:700;color:var(--text-primary);">Valuation Multiples</div><div style="font-size:.75rem;color:var(--text-secondary);margin-top:.2rem;">EV/EBITDA, P/E, and premium analysis</div></div></div>
                        <div style="display:flex;gap:.75rem;padding:.75rem 0;"><span style="font-size:1.2rem;">🔮</span><div><div style="font-size:.85rem;font-weight:700;color:var(--text-primary);">Deal Prediction</div><div style="font-size:.75rem;color:var(--text-secondary);margin-top:.2rem;">AI-powered likelihood scoring</div></div></div>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- INTELLIGENCE -->
    <div id="intelligence" class="section">
        <div class="section-content">
            <div class="sec-eyebrow">Market Intelligence</div>
            <h2 class="sec-title">Deal Flow <em>Intelligence</em></h2>
            <p class="sec-desc">Analytics and market intelligence across global M&A activity, sector trends, and deal flow metrics.</p>
            <div class="divider"></div>
            <div style="display:grid;grid-template-columns:repeat(auto-fit,minmax(250px,1fr));gap:1.5rem;margin-bottom:2.5rem;" id="kpiGrid"></div>
            <div style="display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;margin-bottom:2.5rem;">
                <div class="card">
                    <div class="section-label-gold" style="margin-bottom:1rem;">Market Commentary</div>
                    <div style="font-family:'Plus Jakarta Sans',sans-serif;font-size:1.1rem;font-weight:800;color:var(--text-primary);margin-bottom:1rem;">Q1–Q2 2025 M&A Outlook</div>
                    <p style="font-size:.8rem;color:var(--text-secondary);line-height:1.8;">Global M&A has roared back in 2025, with first-half volumes surpassing $2.1T - the strongest start since 2021. Technology sector consolidation is the defining theme, with AI infrastructure, semiconductors, and data center REITs attracting the most strategic capital. The Federal Reserve's pivot to lower rates has materially reduced deal financing costs, unlocking a wave of buyout activity across private equity. Meanwhile, energy transition M&A is accelerating as oil majors diversify into battery metals, hydrogen, and renewables. Regulatory environments in the US and EU remain elevated for mega-deals exceeding $10B, with antitrust scrutiny adding 6-18 months to cross-border timelines.</p>
                </div>
                <div class="card">
                    <div class="section-label-gold" style="margin-bottom:1rem;">2025–2026 Deal Forecast</div>
                    <div style="font-family:'Plus Jakarta Sans',sans-serif;font-size:1.1rem;font-weight:800;color:var(--text-primary);margin-bottom:1rem;">Projected $4.8T Full-Year Global Volume</div>
                    <p style="font-size:.8rem;color:var(--text-secondary);line-height:1.8;">Goldman Sachs and Morgan Stanley project full-year 2025 global M&A volume to hit $4.8T, driven by PE deployment of record $3.9T dry powder, hyperscaler AI acquisitions, and healthcare biotech consolidation. The pipeline entering H2 2025 includes over 120 deals in regulatory review valued at over $800B. Key themes for 2026 include: defence technology M&A as NATO members increase procurement spend, critical minerals consolidation as the EV battery supply chain tightens, and financial services digitisation where fintechs remain prime acquisition targets for incumbent banks.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- MAKE DEALS -->
    <div id="makedeals" class="section">
        <div class="section-content">
            <div class="sec-eyebrow">Deal Creation Suite</div>
            <h2 class="sec-title">Make <em>Deals</em></h2>
            <p class="sec-desc">Explore acquisition targets by sector, analyse share price and valuation, and model your own M&A transaction.</p>
            <div class="divider"></div>
            <div id="mdContent"></div>
        </div>
    </div>

    <!-- MERGER MODAL -->
    <div class="modal-overlay" id="mergerModal">
      <div class="modal-box">
        <div class="modal-header">
          <div>
            <div class="modal-badge badge-merger">⚡ MERGER</div>
            <div class="modal-title">Find Your Merger Partner</div>
            <div class="modal-subtitle">Answer 3 quick questions - we'll match your ideal strategic partners</div>
          </div>
          <button class="modal-close" onclick="closeModal('mergerModal')">✕</button>
        </div>
        <div class="modal-body">
          <div class="step-indicator">
            <div class="step-dot done" id="mstep-dot-1"></div>
            <div class="step-dot" id="mstep-dot-2"></div>
            <div class="step-dot" id="mstep-dot-3"></div>
            <div class="step-dot" id="mstep-dot-4"></div>
            <span class="step-label" id="mstep-label">Step 1 of 3</span>
          </div>
          <div class="modal-step active" id="mstep-1">
            <div class="form-group">
              <div class="form-label">Step 1 — Your Company</div>
              <div class="form-question">Which sector does your company operate in?</div>
              <div class="option-grid" id="m-sector-grid"></div>
            </div>
          </div>
          <div class="modal-step" id="mstep-2">
            <div class="form-group">
              <div class="form-label">Step 2 - Company Valuation</div>
              <div class="form-question">What is your company's approximate enterprise value?</div>
              <div class="value-display" id="m-value-display">$500M</div>
              <input type="range" id="m-value-slider" min="0" max="100" value="25" oninput="updateValueDisplay('m-value-display',this.value,'m')">
              <div style="display:flex;justify-content:space-between;font-size:.72rem;color:var(--text-secondary);margin-top:.5rem;"><span>$50M</span><span>$500M</span><span>$2B</span><span>$10B</span><span>$50B+</span></div>
            </div>
          </div>
          <div class="modal-step" id="mstep-3">
            <div class="form-group">
              <div class="form-label">Step 3 - Merger Objective</div>
              <div class="form-question">What is the primary goal of this merger?</div>
              <div class="goal-grid" id="m-goal-grid"></div>
            </div>
          </div>
          <div class="modal-step" id="mstep-4">
            <div id="merger-results"></div>
          </div>
        </div>
        <div class="modal-footer">
          <button class="modal-btn-back" id="m-back-btn" onclick="modalBack('m')" style="display:none">← Back</button>
          <button class="modal-btn-next" id="m-next-btn" onclick="modalNext('m')">Continue →</button>
        </div>
      </div>
    </div>

    <!-- ACQUISITION MODAL -->
    <div class="modal-overlay" id="acquisitionModal">
      <div class="modal-box">
        <div class="modal-header">
          <div>
            <div class="modal-badge badge-acquisition">🎯 ACQUISITION</div>
            <div class="modal-title">Find Acquisition Targets</div>
            <div class="modal-subtitle">Tell us about yourself - we'll identify the best companies to acquire</div>
          </div>
          <button class="modal-close" onclick="closeModal('acquisitionModal')">✕</button>
        </div>
        <div class="modal-body">
          <div class="step-indicator">
            <div class="step-dot done" id="astep-dot-1"></div>
            <div class="step-dot" id="astep-dot-2"></div>
            <div class="step-dot" id="astep-dot-3"></div>
            <div class="step-dot" id="astep-dot-4"></div>
            <span class="step-label" id="astep-label">Step 1 of 3</span>
          </div>
          <div class="modal-step active" id="astep-1">
            <div class="form-group">
              <div class="form-label">Step 1 — Your Company</div>
              <div class="form-question">Which sector does your company operate in?</div>
              <div class="option-grid" id="a-sector-grid"></div>
            </div>
          </div>
          <div class="modal-step" id="astep-2">
            <div class="form-group">
              <div class="form-label">Step 2 — Acquisition Budget</div>
              <div class="form-question">What is your acquisition budget / purchasing power?</div>
              <div class="value-display" id="a-value-display">$500M</div>
              <input type="range" id="a-value-slider" min="0" max="100" value="25" oninput="updateValueDisplay('a-value-display',this.value,'a')">
              <div style="display:flex;justify-content:space-between;font-size:.72rem;color:var(--text-secondary);margin-top:.5rem;"><span>$50M</span><span>$500M</span><span>$2B</span><span>$10B</span><span>$50B+</span></div>
            </div>
          </div>
          <div class="modal-step" id="astep-3">
            <div class="form-group">
              <div class="form-label">Step 3 - Acquisition Strategy</div>
              <div class="form-question">What type of acquisition are you pursuing?</div>
              <div class="goal-grid" id="a-goal-grid"></div>
            </div>
          </div>
          <div class="modal-step" id="astep-4">
            <div id="acquisition-results"></div>
          </div>
        </div>
        <div class="modal-footer">
          <button class="modal-btn-back" id="a-back-btn" onclick="modalBack('a')" style="display:none">← Back</button>
          <button class="modal-btn-next" id="a-next-btn" onclick="modalNext('a')">Continue →</button>
        </div>
      </div>
    </div>
</main>

<footer>
    <div>
        <div class="footer-logo">M&A <span>Hub</span></div>
        <div class="footer-text">Global M&A Intelligence Platform</div>
    </div>
    <div class="footer-links">
        <a onclick="showSection('deals')">Live Deals</a>
        <a onclick="showSection('sectors')">Sectors</a>
        <a onclick="showSection('regions')">Regions</a>
        <a onclick="showSection('analysis')">Analysis</a>
        <a onclick="showSection('intelligence')">Intelligence</a>
        <a onclick="showSection('makedeals')">Make Deals</a>
    </div>
    <div>
        <div class="footer-text">© 2025 M&A Hub. For informational purposes only.</div>
        <div class="footer-disclaimer">Data sourced from public filings, SEC EDGAR, Bloomberg &amp; Refinitiv. Simulated pricing for demonstration. Not investment advice.</div>
    </div>
</footer>

<script>
// ─── SAFE STORAGE ────────────────────────────────────────────────────────────
function safeGetItem(k){try{return localStorage.getItem(k);}catch(e){return null;}}
function safeSetItem(k,v){try{localStorage.setItem(k,v);}catch(e){}}

// ─── THEME ───────────────────────────────────────────────────────────────────
function toggleTheme(){
    var html=document.documentElement;
    var btn=document.getElementById('themeToggle');
    if(html.classList.contains('dark-mode')){
        html.classList.remove('dark-mode');btn.textContent='🌙';safeSetItem('theme','light');
    } else {
        html.classList.add('dark-mode');btn.textContent='☀️';safeSetItem('theme','dark');
    }
}

// ─── NAVIGATION ──────────────────────────────────────────────────────────────
function showSection(id){
    document.querySelectorAll('.section').forEach(function(s){s.classList.remove('active');});
    document.getElementById(id).classList.add('active');
    var backBtn=document.getElementById('backBtn');
    if(id==='landing') backBtn.classList.remove('visible');
    else backBtn.classList.add('visible');
    document.querySelectorAll('.nav-center a').forEach(function(a){a.classList.remove('active');});
    if(id!=='landing'){
        var al=document.querySelector('.nav-center a[onclick*="\''+id+'\'"]');
        if(al) al.classList.add('active');
    }
    window.scrollTo(0,0);
}
function goHome(){showSection('landing');}

// ─── DEALS DATA ──────────────────────────────────────────────────────────────
var DEALS_DATA={
    present:[
        {acquirer:'Capital One Financial',target:'Discover Financial Services',value:'$35.3B',sector:'Finance',region:'North America',date:'Feb 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'Synopsys',target:'Ansys Inc.',value:'$35.0B',sector:'Technology',region:'North America',date:'Jan 2024',type:'Merger',status:'PENDING'},
        {acquirer:'Mars Inc.',target:'Kellanova (Kellogg)',value:'$36.0B',sector:'Consumer',region:'North America',date:'Aug 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'Chevron',target:'Hess Corporation',value:'$53.0B',sector:'Energy',region:'North America',date:'Oct 2023',type:'Acquisition',status:'PENDING'},
        {acquirer:'Nippon Steel',target:'U.S. Steel Corporation',value:'$14.9B',sector:'Industrials',region:'North America',date:'Dec 2023',type:'Acquisition',status:'PENDING'},
        {acquirer:'Rio Tinto',target:'Arcadium Lithium',value:'$6.7B',sector:'Mining',region:'Global',date:'Oct 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'Hewlett Packard Enterprise',target:'Juniper Networks',value:'$14.0B',sector:'Technology',region:'North America',date:'Jan 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'Sony Group',target:'Kadokawa Corporation',value:'$1.8B',sector:'Media',region:'Asia Pacific',date:'Jan 2025',type:'Acquisition',status:'PENDING'},
        {acquirer:'SoftBank Group',target:'Ampere Computing',value:'$4.5B',sector:'Technology',region:'North America',date:'Dec 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'Alphabet (Google)',target:'Wiz Inc.',value:'$23.0B',sector:'Technology',region:'Global',date:'Jul 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'Saudi Aramco',target:'Rabigh Refining & Petrochem',value:'$3.3B',sector:'Energy',region:'Middle East',date:'Nov 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'Sanofi',target:'Blueprint Medicines',value:'$7.0B',sector:'Healthcare',region:'North America',date:'Oct 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'AstraZeneca',target:'Fusion Pharmaceuticals',value:'$2.4B',sector:'Healthcare',region:'North America',date:'Mar 2024',type:'Acquisition',status:'PENDING'},
        {acquirer:'Blackstone',target:'Retail Property Trust REIT',value:'$4.2B',sector:'Real Estate',region:'North America',date:'Feb 2025',type:'Buyout',status:'PENDING'},
        {acquirer:'Thermo Fisher Scientific',target:'Solventum Life Sciences',value:'$6.1B',sector:'Healthcare',region:'North America',date:'Jan 2025',type:'Acquisition',status:'PENDING'},
        {acquirer:'Comcast',target:'Charter Communications (merger talks)',value:'$18.0B',sector:'Telecoms',region:'North America',date:'Mar 2025',type:'Merger',status:'RUMORED'},
        {acquirer:'Saudi PIF',target:'Heathrow Airport (10% stake)',value:'$3.2B',sector:'Logistics',region:'Europe',date:'Dec 2024',type:'Minority Stake',status:'PENDING'},
        {acquirer:'Mubadala Investment',target:'Fortress Investment Group',value:'$2.4B',sector:'Finance',region:'Global',date:'Jan 2025',type:'Acquisition',status:'PENDING'},
        {acquirer:'Silver Lake Partners',target:'Endeavor Group Holdings',value:'$13.0B',sector:'Media',region:'North America',date:'Apr 2024',type:'Buyout',status:'PENDING'},
        {acquirer:'KKR & Co.',target:'Fuji Soft (Japanese IT firm)',value:'$3.7B',sector:'Technology',region:'Asia Pacific',date:'Aug 2024',type:'Buyout',status:'PENDING'},
    ],
    past:[
        {acquirer:'Microsoft',target:'Activision Blizzard',value:'$68.7B',sector:'Technology',region:'North America',date:'Oct 2023',type:'Acquisition',status:'CLOSED'},
        {acquirer:'ExxonMobil',target:'Pioneer Natural Resources',value:'$59.5B',sector:'Energy',region:'North America',date:'May 2024',type:'Acquisition',status:'CLOSED'},
        {acquirer:'Broadcom',target:'VMware',value:'$61.0B',sector:'Technology',region:'North America',date:'Nov 2023',type:'Acquisition',status:'CLOSED'},
        {acquirer:'Pfizer',target:'Seagen Inc.',value:'$43.0B',sector:'Healthcare',region:'North America',date:'Dec 2023',type:'Acquisition',status:'CLOSED'},
        {acquirer:'Amazon',target:'MGM Holdings',value:'$8.45B',sector:'Media',region:'North America',date:'Mar 2022',type:'Acquisition',status:'CLOSED'},
        {acquirer:'JPMorgan Chase',target:'First Republic Bank',value:'$10.6B',sector:'Finance',region:'North America',date:'May 2023',type:'Acquisition',status:'CLOSED'},
        {acquirer:'Cisco Systems',target:'Splunk Inc.',value:'$28.0B',sector:'Technology',region:'North America',date:'Mar 2024',type:'Acquisition',status:'CLOSED'},
        {acquirer:'Novo Nordisk',target:'Catalent Inc.',value:'$11.0B',sector:'Healthcare',region:'North America',date:'Feb 2024',type:'Acquisition',status:'CLOSED'},
        {acquirer:'UBS Group',target:'Credit Suisse',value:'$3.25B',sector:'Finance',region:'Europe',date:'Jun 2023',type:'Merger',status:'CLOSED'},
        {acquirer:'BlackRock',target:'Global Infrastructure Partners',value:'$12.5B',sector:'Finance',region:'Global',date:'Jan 2024',type:'Acquisition',status:'CLOSED'},
        {acquirer:'ConocoPhillips',target:'Marathon Oil Corporation',value:'$22.5B',sector:'Energy',region:'North America',date:'Aug 2024',type:'Acquisition',status:'CLOSED'},
        {acquirer:'Newmont Corporation',target:'Newcrest Mining',value:'$17.5B',sector:'Mining',region:'Asia Pacific',date:'Nov 2023',type:'Acquisition',status:'CLOSED'},
        {acquirer:'Diamondback Energy',target:'Endeavor Energy Resources',value:'$26.0B',sector:'Energy',region:'North America',date:'Sep 2024',type:'Merger',status:'CLOSED'},
        {acquirer:'Mastercard',target:'Recorded Future',value:'$2.65B',sector:'Technology',region:'North America',date:'Sep 2024',type:'Acquisition',status:'CLOSED'},
        {acquirer:'Volkswagen Group',target:'Rivian Automotive (25% stake)',value:'$5.8B',sector:'Consumer',region:'North America',date:'Nov 2024',type:'JV / Investment',status:'CLOSED'},
    ],
    future:[
        {acquirer:'Tesla Inc.',target:'Redwood Materials',value:'$5.0B',sector:'Energy',region:'North America',date:'Q2 2025',type:'Acquisition',status:'RUMORED'},
        {acquirer:'Apple Inc.',target:'SoundHound AI',value:'$2.5B',sector:'Technology',region:'North America',date:'Q3 2025',type:'Acquisition',status:'RUMORED'},
        {acquirer:'Meta Platforms',target:'Hugging Face',value:'$4.0B',sector:'Technology',region:'Global',date:'Q2 2025',type:'Acquisition',status:'RUMORED'},
        {acquirer:'SoftBank Group',target:'OpenAI (additional tranche)',value:'$40.0B',sector:'Technology',region:'North America',date:'Q2 2025',type:'Investment',status:'RUMORED'},
        {acquirer:'Shell plc',target:'BP (merger talks)',value:'$100.0B+',sector:'Energy',region:'Europe',date:'H2 2025',type:'Merger',status:'RUMORED'},
        {acquirer:'JPMorgan Chase',target:'Robinhood Markets',value:'$12.0B',sector:'Finance',region:'North America',date:'Q4 2025',type:'Acquisition',status:'RUMORED'},
        {acquirer:'Nvidia',target:'Recursion Pharmaceuticals',value:'$2.1B',sector:'Healthcare',region:'North America',date:'Q2 2025',type:'Acquisition',status:'RUMORED'},
        {acquirer:'BHP Group',target:'Vale Base Metals (full control)',value:'$22.0B',sector:'Mining',region:'Latin America',date:'Q4 2025',type:'Acquisition',status:'RUMORED'},
        {acquirer:'Microsoft',target:'CrowdStrike (partial stake)',value:'$10.0B',sector:'Technology',region:'North America',date:'Q3 2025',type:'Minority Stake',status:'RUMORED'},
        {acquirer:'Apple Inc.',target:'Peloton Interactive',value:'$1.2B',sector:'Consumer',region:'North America',date:'Q3 2025',type:'Acquisition',status:'RUMORED'},
        {acquirer:'Comcast / NBCUniversal',target:'Paramount Global (remainder)',value:'$9.5B',sector:'Media',region:'North America',date:'Q3 2025',type:'Acquisition',status:'RUMORED'},
        {acquirer:'Berkshire Hathaway',target:'Chubb Limited (increase stake)',value:'$15.0B',sector:'Finance',region:'Global',date:'H2 2025',type:'Acquisition',status:'RUMORED'},
    ]
};

// ─── SECTORS DATA ────────────────────────────────────────────────────────────
var SECTORS_DATA={
    Technology:[
        {name:'Apple Inc.',ticker:'AAPL',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:213.49,marketcap:'$3.28T',pe:'33.2x',week52low:164.08,week52high:237.23,volume:'52.1M',badges:['Consumer Electronics','AI','Services','Acquirer'],desc:"World's most valuable company. iPhone, Mac, iPad, Vision Pro. Services $90B+ revenue. $165B+ cash war chest."},
        {name:'Microsoft',ticker:'MSFT',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:415.32,marketcap:'$3.09T',pe:'35.8x',week52low:309.45,week52high:467.00,volume:'18.4M',badges:['Cloud','AI','Enterprise','Active Acquirer'],desc:'Azure cloud growing 31% YoY. $68.7B Activision closed. OpenAI $13B+ powers Copilot.'},
        {name:'Nvidia',ticker:'NVDA',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:875.40,marketcap:'$2.15T',pe:'72.1x',week52low:461.28,week52high:974.00,volume:'38.7M',badges:['AI Chips','Data Centers','Networking'],desc:'H100/B200 GPUs power 85%+ of global AI training. Data center revenue $47B growing 220% YoY.'},
        {name:'Alphabet',ticker:'GOOGL',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:175.98,marketcap:'$2.17T',pe:'24.3x',week52low:130.67,week52high:207.05,volume:'24.6M',badges:['Search','Cloud','AI','Active Acquirer'],desc:'Search 92% global share. YouTube $36B revenue. Pending $23B Wiz acquisition.'},
        {name:'Meta Platforms',ticker:'META',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:562.10,marketcap:'$1.42T',pe:'28.6x',week52low:353.96,week52high:611.72,volume:'12.9M',badges:['Social Media','AR/VR','AI'],desc:'3.07B DAU across family of apps. Llama 4 open-source AI. $60B+ annual AI capex.'},
        {name:'Broadcom',ticker:'AVGO',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:182.45,marketcap:'$854B',pe:'51.2x',week52low:118.85,week52high:251.88,volume:'9.3M',badges:['Semiconductors','VMware','AI Accelerators'],desc:'$61B VMware acquisition transformed into diversified tech giant. Custom AI XPUs for Google/Meta.'},
        {name:'AMD',ticker:'AMD',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:162.37,marketcap:'$262B',pe:'46.8x',week52low:141.12,week52high:227.30,volume:'33.5M',badges:['AI Chips','CPU','GPU'],desc:'EPYC CPUs 25%+ server share. MI300X AI GPU $3.5B+ revenue growing 200% YoY.'},
        {name:'ServiceNow',ticker:'NOW',exchange:'NYSE',country:'🇺🇸 USA',basePrice:998.75,marketcap:'$207B',pe:'62.4x',week52low:612.77,week52high:1198.09,volume:'1.7M',badges:['IT Workflows','AI Platform','Enterprise'],desc:'$10B+ ARR growing 25%+ YoY. Now Platform AI agents automating IT, HR, finance workflows.'},
    ],
    Healthcare:[
        {name:'Eli Lilly',ticker:'LLY',exchange:'NYSE',country:'🇺🇸 USA',basePrice:820.45,marketcap:'$778B',pe:'62.8x',week52low:649.13,week52high:972.53,volume:'2.1M',badges:['GLP-1','Obesity','Diabetes'],desc:"Tirzepatide (Mounjaro/Zepbound) $10B+ revenue growing 200%+ YoY. World's most valuable pharma by EV."},
        {name:'Novo Nordisk',ticker:'NVO',exchange:'NYSE',country:'🇩🇰 Denmark',basePrice:89.12,marketcap:'$396B',pe:'27.4x',week52low:67.82,week52high:148.88,volume:'8.2M',badges:['GLP-1','Semaglutide','Active Acquirer'],desc:"Semaglutide (Ozempic/Wegovy) pioneer. $11B Catalent acquisition. Europe's most valuable listed company."},
        {name:'Johnson & Johnson',ticker:'JNJ',exchange:'NYSE',country:'🇺🇸 USA',basePrice:157.33,marketcap:'$378B',pe:'16.2x',week52low:144.95,week52high:168.85,volume:'7.3M',badges:['Pharma','MedTech','Active Acquirer'],desc:'Post-Kenvue: Innovative Medicine $57B + MedTech $34B. Shockwave Medical $13.1B acquisition.'},
        {name:'Pfizer Inc.',ticker:'PFE',exchange:'NYSE',country:'🇺🇸 USA',basePrice:27.14,marketcap:'$153B',pe:'12.3x',week52low:25.20,week52high:31.54,volume:'35.8M',badges:['Pharma','Oncology','ADC'],desc:'$43B Seagen creates ADC oncology leader. Danuglipron oral GLP-1 Phase 3.'},
        {name:'Merck & Co.',ticker:'MRK',exchange:'NYSE',country:'🇺🇸 USA',basePrice:130.56,marketcap:'$331B',pe:'21.7x',week52low:96.49,week52high:134.63,volume:'9.1M',badges:['Oncology','Keytruda','Active Acquirer'],desc:"Keytruda $25B+ annual sales — world's best-selling drug. 2028 patent cliff urgency."},
        {name:'AstraZeneca',ticker:'AZN',exchange:'NASDAQ',country:'🇬🇧 UK',basePrice:69.82,marketcap:'$218B',pe:'23.1x',week52low:57.46,week52high:89.01,volume:'5.6M',badges:['Oncology','Rare Disease','Active Acquirer'],desc:'$2.4B Fusion Pharma radiopharmaceuticals. Fastest-growing top-5 pharma.'},
        {name:'Intuitive Surgical',ticker:'ISRG',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:490.21,marketcap:'$175B',pe:'68.4x',week52low:306.29,week52high:556.52,volume:'1.8M',badges:['Surgical Robotics','Monopoly','Recurring'],desc:'da Vinci in 9,500+ hospitals. Near-monopoly soft-tissue robotics. 75%+ recurring revenue.'},
    ],
    Energy:[
        {name:'ExxonMobil',ticker:'XOM',exchange:'NYSE',country:'🇺🇸 USA',basePrice:113.42,marketcap:'$452B',pe:'14.1x',week52low:100.12,week52high:123.75,volume:'14.8M',badges:['Oil & Gas','Permian','Active Acquirer'],desc:'Pioneer $59.5B doubles Permian. $20B+ annual shareholder returns.'},
        {name:'Chevron',ticker:'CVX',exchange:'NYSE',country:'🇺🇸 USA',basePrice:155.67,marketcap:'$287B',pe:'13.8x',week52low:138.45,week52high:172.28,volume:'10.6M',badges:['Oil & Gas','LNG','Active Acquirer'],desc:'$53B Hess pending ICC arbitration. 50%+ FCF returned to shareholders.'},
        {name:'ConocoPhillips',ticker:'COP',exchange:'NYSE',country:'🇺🇸 USA',basePrice:108.23,marketcap:'$147B',pe:'13.2x',week52low:99.43,week52high:133.06,volume:'8.4M',badges:['E&P Leader','Permian','Active Acquirer'],desc:'Marathon Oil $22.5B (Aug 2024). $45/bbl breakeven — lowest in the industry.'},
        {name:'NextEra Energy',ticker:'NEE',exchange:'NYSE',country:'🇺🇸 USA',basePrice:75.40,marketcap:'$154B',pe:'22.8x',week52low:52.88,week52high:86.10,volume:'11.2M',badges:['Renewables','Wind','Solar'],desc:"World's largest renewable energy generator. 36GW+ capacity."},
        {name:'Diamondback Energy',ticker:'FANG',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:178.32,marketcap:'$49B',pe:'10.4x',week52low:156.22,week52high:211.56,volume:'2.3M',badges:['Permian Pure-Play','Low Cost','Active Acquirer'],desc:'Endeavor Energy $26B (Sep 2024). Sub-$40/bbl breakeven.'},
    ],
    Finance:[
        {name:'JPMorgan Chase',ticker:'JPM',exchange:'NYSE',country:'🇺🇸 USA',basePrice:242.18,marketcap:'$694B',pe:'13.1x',week52low:178.37,week52high:280.25,volume:'8.6M',badges:['Banking','Investment Banking','Active Acquirer'],desc:'Most profitable US bank. First Republic $10.6B. IB fees +58% Q1 2025.'},
        {name:'BlackRock',ticker:'BLK',exchange:'NYSE',country:'🇺🇸 USA',basePrice:1004.33,marketcap:'$152B',pe:'22.7x',week52low:751.57,week52high:1084.22,volume:'0.7M',badges:['Asset Management','ETFs','Active Acquirer'],desc:"$10.5T AUM — world's largest. $12.5B GIP + $12B HPS acquisitions."},
        {name:'Goldman Sachs',ticker:'GS',exchange:'NYSE',country:'🇺🇸 USA',basePrice:556.87,marketcap:'$184B',pe:'15.8x',week52low:386.37,week52high:620.37,volume:'2.4M',badges:['Investment Banking','Trading','Advisory'],desc:'#1 global M&A advisory 15 years. Q1 2025 advisory revenue $3.5B +58% YoY.'},
        {name:'Visa Inc.',ticker:'V',exchange:'NYSE',country:'🇺🇸 USA',basePrice:348.92,marketcap:'$712B',pe:'32.4x',week52low:271.99,week52high:368.51,volume:'4.2M',badges:['Payments','Network','High Margin'],desc:'160M+ merchant acceptance, 4.3B cards. 80%+ gross margins.'},
        {name:'Apollo Global Mgmt',ticker:'APO',exchange:'NYSE',country:'🇺🇸 USA',basePrice:148.62,marketcap:'$93B',pe:'24.5x',week52low:92.34,week52high:185.49,volume:'2.7M',badges:['Private Equity','Credit','Active Acquirer'],desc:'$696B AUM credit-focused. Athene insurance $280B+ liabilities.'},
        {name:'KKR & Co.',ticker:'KKR',exchange:'NYSE',country:'🇺🇸 USA',basePrice:132.48,marketcap:'$118B',pe:'28.9x',week52low:77.38,week52high:167.21,volume:'3.9M',badges:['Private Equity','Infrastructure','Active Acquirer'],desc:'$600B+ AUM. Fuji Soft $3.7B Japan buyout. Global Atlantic $160B+ insurance.'},
    ],
    Consumer:[
        {name:'Amazon',ticker:'AMZN',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:215.87,marketcap:'$2.27T',pe:'46.2x',week52low:151.61,week52high:242.52,volume:'33.4M',badges:['E-commerce','AWS','Streaming','Active Acquirer'],desc:'AWS $100B run rate +31% YoY. 38% US online retail. FY2024 revenue $620B+.'},
        {name:'Walmart',ticker:'WMT',exchange:'NYSE',country:'🇺🇸 USA',basePrice:95.34,marketcap:'$766B',pe:'38.6x',week52low:60.41,week52high:105.30,volume:'25.7M',badges:['Retail','E-commerce','Advertising'],desc:'Vizio $2.3B for advertising tech. FY2025 revenue $680B+.'},
        {name:'Tesla Inc.',ticker:'TSLA',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:248.73,marketcap:'$797B',pe:'85.1x',week52low:138.80,week52high:488.54,volume:'68.3M',badges:['EV','Energy Storage','AI Vehicles'],desc:'FSD and Robotaxi key catalysts. Megapack $3B+ revenue growing 150%+.'},
        {name:'Costco Wholesale',ticker:'COST',exchange:'NASDAQ',country:'🇺🇸 USA',basePrice:967.18,marketcap:'$428B',pe:'55.4x',week52low:716.45,week52high:1078.23,volume:'1.4M',badges:['Warehouse Retail','Membership','Recession-Proof'],desc:'Membership fee $4.6B annual revenue. 135M+ cardholders 92%+ renewal.'},
        {name:'LVMH',ticker:'MC.PA',exchange:'EPA',country:'🇫🇷 France',basePrice:590.40,marketcap:'$291B',pe:'19.2x',week52low:547.50,week52high:855.00,volume:'1.1M',badges:['Luxury','Fashion','Active Acquirer'],desc:"75 luxury houses. Louis Vuitton, Dior, Moët Hennessy. €86B revenue 2024."},
    ],
    Industrials:[
        {name:'GE Aerospace',ticker:'GE',exchange:'NYSE',country:'🇺🇸 USA',basePrice:198.43,marketcap:'$216B',pe:'43.2x',week52low:119.40,week52high:217.11,volume:'8.1M',badges:['Aerospace Engines','Defense','Pure-Play'],desc:'LEAP and GE9X engines. $165B+ order backlog. 30%+ EBIT margins.'},
        {name:'RTX Corporation',ticker:'RTX',exchange:'NYSE',country:'🇺🇸 USA',basePrice:126.78,marketcap:'$170B',pe:'32.1x',week52low:91.76,week52high:135.44,volume:'7.3M',badges:['Missiles','Aerospace','Defense','NATO'],desc:'Pratt & Whitney GTF + Raytheon missiles. Defense backlog $202B+.'},
        {name:'Caterpillar',ticker:'CAT',exchange:'NYSE',country:'🇺🇸 USA',basePrice:348.25,marketcap:'$168B',pe:'16.8x',week52low:306.19,week52high:418.99,volume:'2.6M',badges:['Heavy Equipment','Mining','Infrastructure'],desc:'IRA, CHIPS Act, reshoring infrastructure super-cycle.'},
        {name:'Lockheed Martin',ticker:'LMT',exchange:'NYSE',country:'🇺🇸 USA',basePrice:522.18,marketcap:'$121B',pe:'18.2x',week52low:412.08,week52high:578.22,volume:'1.6M',badges:['F-35','Hypersonics','Space'],desc:'F-35 program $400B+ lifetime value. $110B backlog.'},
    ],
    Mining:[
        {name:'BHP Group',ticker:'BHP',exchange:'NYSE',country:'🇦🇺 Australia',basePrice:55.23,marketcap:'$278B',pe:'12.4x',week52low:48.71,week52high:66.23,volume:'4.8M',badges:['Copper','Iron Ore','Potash','Active Acquirer'],desc:"World's largest miner by cap. Iron ore Pilbara $30B revenue."},
        {name:'Rio Tinto',ticker:'RIO',exchange:'NYSE',country:'🇦🇺🇬🇧 Aus/UK',basePrice:65.48,marketcap:'$104B',pe:'10.8x',week52low:58.72,week52high:82.71,volume:'4.1M',badges:['Lithium','Copper','Iron Ore','Active Acquirer'],desc:'Arcadium Lithium $6.7B (2024) → 3rd largest lithium producer.'},
        {name:'Freeport-McMoRan',ticker:'FCX',exchange:'NYSE',country:'🇺🇸 USA',basePrice:42.87,marketcap:'$62B',pe:'20.3x',week52low:35.53,week52high:57.45,volume:'18.9M',badges:['Copper','Gold','Grasberg'],desc:"Grasberg — world's 2nd largest copper + largest gold mine."},
        {name:'Barrick Gold',ticker:'GOLD',exchange:'NYSE',country:'🇨🇦 Canada',basePrice:17.32,marketcap:'$29B',pe:'19.8x',week52low:13.56,week52high:22.65,volume:'19.6M',badges:['Gold','Copper','Tier-1 Assets'],desc:'Tier-1 mines: Carlin, Cortez, Kibali DRC. $3B+ FCF at $2,000/oz gold.'},
    ],
    Defense:[
        {name:'Lockheed Martin',ticker:'LMT2',exchange:'NYSE',country:'🇺🇸 USA',basePrice:522.18,marketcap:'$121B',pe:'18.2x',week52low:412.08,week52high:578.22,volume:'1.6M',badges:['F-35','Hypersonics','Space'],desc:'F-35 $400B+ lifetime value. Sikorsky Black Hawk.'},
        {name:'RTX Corporation',ticker:'RTX2',exchange:'NYSE',country:'🇺🇸 USA',basePrice:126.78,marketcap:'$170B',pe:'32.1x',week52low:91.76,week52high:135.44,volume:'7.3M',badges:['Missiles','Engines','NATO'],desc:'Pratt & Whitney + Raytheon missiles. Patriot $20B+. Defense backlog $202B+.'},
        {name:'Northrop Grumman',ticker:'NOC',exchange:'NYSE',country:'🇺🇸 USA',basePrice:503.42,marketcap:'$29B',pe:'19.8x',week52low:420.14,week52high:548.20,volume:'1.0M',badges:['B-21 Bomber','Space','Cyber'],desc:'B-21 Raider — sole manufacturer next-gen stealth bomber.'},
        {name:'Palantir Technologies',ticker:'PLTR',exchange:'NYSE',country:'🇺🇸 USA',basePrice:82.35,marketcap:'$174B',pe:'195.4x',week52low:15.66,week52high:125.41,volume:'68.4M',badges:['AI Defense','AIP Platform','High Growth'],desc:'AIP integrates LLMs into defense and commercial. Gov revenue +40% YoY.'},
        {name:'General Dynamics',ticker:'GD',exchange:'NYSE',country:'🇺🇸 USA',basePrice:318.74,marketcap:'$86B',pe:'19.4x',week52low:263.58,week52high:337.14,volume:'1.5M',badges:['Submarines','Gulfstream','Vehicles'],desc:'Virginia-class nuclear submarines. Gulfstream jets $10B+ revenue.'},
    ]
};

// ─── TICKER ──────────────────────────────────────────────────────────────────
function initTicker(){
    var tickers=[
        {symbol:'CAPONE/DFS',price:'$35.3B',change:'PENDING',up:false},
        {symbol:'SNPS/ANSS',price:'$35.0B',change:'PENDING',up:false},
        {symbol:'GOOGL/WIZ',price:'$23.0B',change:'PENDING',up:false},
        {symbol:'MSFT/ATVI',price:'$68.7B',change:'CLOSED',up:true},
        {symbol:'XOM/PXD',price:'$59.5B',change:'CLOSED',up:true},
        {symbol:'AVGO/VMW',price:'$61.0B',change:'CLOSED',up:true},
        {symbol:'PFE/SGEN',price:'$43.0B',change:'CLOSED',up:true},
        {symbol:'COP/MRO',price:'$22.5B',change:'CLOSED',up:true},
        {symbol:'CSCO/SPLK',price:'$28.0B',change:'CLOSED',up:true},
        {symbol:'BLK/GIP',price:'$12.5B',change:'CLOSED',up:true},
        {symbol:'SBF/OAI',price:'$40.0B',change:'RUMORED',up:false},
        {symbol:'SHEL/BP',price:'$100B+',change:'RUMORED',up:false},
        {symbol:'NVO/CTLT',price:'$11.0B',change:'CLOSED',up:true},
        {symbol:'RIO/ALTM',price:'$6.7B',change:'CLOSED',up:true},
        {symbol:'AAPL/SOUN',price:'$2.5B',change:'RUMORED',up:false},
    ];
    var html='';
    tickers.forEach(function(t){
        html+='<div class="ticker-item '+(t.up?'up':'dn')+'"><span class="symbol">'+t.symbol+'</span><span class="price">'+t.price+'</span><span class="change">'+t.change+'</span></div>';
    });
    html+=html;
    document.getElementById('tickerContent').innerHTML=html;
}

// ─── LIVE PRICE ENGINE ───────────────────────────────────────────────────────
var liveState={};
var liveInterval=null;
var currentSector='Technology';

function formatPrice(p){
    if(p>=1000) return '$'+p.toLocaleString('en-US',{minimumFractionDigits:2,maximumFractionDigits:2});
    if(p>=1) return '$'+p.toFixed(2);
    return '$'+p.toFixed(4);
}

function initLiveState(companies){
    companies.forEach(function(c){
        if(!liveState[c.ticker]){
            var history=[];var p=c.basePrice;
            for(var i=0;i<30;i++){p=p*(1+(Math.random()-.497)*.006);history.push(+p.toFixed(2));}
            liveState[c.ticker]={price:+p.toFixed(2),open:+c.basePrice.toFixed(2),changeAbs:+(p-c.basePrice).toFixed(2),changePct:+((p-c.basePrice)/c.basePrice*100).toFixed(2),history:history};
        }
    });
}

function buildSparkline(history,isUp){
    var W=300,H=52,pad=4;
    if(!history||history.length<2) return '';
    var mn=Math.min.apply(null,history),mx=Math.max.apply(null,history);
    var range=mx-mn||1;
    var pts=history.map(function(v,i){
        var x=pad+(i/(history.length-1))*(W-pad*2);
        var y=H-pad-((v-mn)/range)*(H-pad*2);
        return x.toFixed(1)+','+y.toFixed(1);
    }).join(' ');
    var lastX=pad+(W-pad*2);
    var lastY=H-pad-((history[history.length-1]-mn)/range)*(H-pad*2);
    var color=isUp?'#4caf7d':'#ef4444';
    var fill=isUp?'rgba(76,175,125,0.08)':'rgba(239,68,68,0.08)';
    var areaPoints=pad+','+H+' '+pts+' '+lastX+','+H;
    return '<svg viewBox="0 0 '+W+' '+H+'" preserveAspectRatio="none">'
        +'<polygon points="'+areaPoints+'" fill="'+fill+'"/>'
        +'<polyline points="'+pts+'" fill="none" stroke="'+color+'" stroke-width="1.8" stroke-linejoin="round" stroke-linecap="round"/>'
        +'<circle cx="'+lastX+'" cy="'+lastY.toFixed(1)+'" r="3" fill="'+color+'"/>'
        +'</svg>';
}

function tickLivePrices(sector){
    var companies=SECTORS_DATA[sector]||[];
    companies.forEach(function(c){
        var st=liveState[c.ticker];if(!st) return;
        var drift=(Math.random()-.496)*.0035;
        st.price=+(st.price*(1+drift)).toFixed(2);
        st.changeAbs=+(st.price-st.open).toFixed(2);
        st.changePct=+(st.changeAbs/st.open*100).toFixed(2);
        st.history.push(st.price);
        if(st.history.length>40) st.history.shift();
        var priceEl=document.getElementById('price-'+c.ticker);
        var chgEl=document.getElementById('chg-'+c.ticker);
        if(priceEl){
            var up=st.changeAbs>=0;
            priceEl.textContent=formatPrice(st.price);
            priceEl.className='co-price-val '+(up?'up':'dn')+' co-price-flash';
            setTimeout(function(){if(priceEl) priceEl.classList.remove('co-price-flash');},450);
            chgEl.innerHTML=(up?'▲':'▼')+' '+Math.abs(st.changePct).toFixed(2)+'%';
            chgEl.className='co-price-chg '+(up?'up':'dn');
        }
        var sparkEl=document.getElementById('spark-'+c.ticker);
        if(sparkEl) sparkEl.innerHTML=buildSparkline(st.history,st.changeAbs>=0);
    });
}

function renderSectorSummary(sector){
    var companies=SECTORS_DATA[sector]||[];
    var gainers=0,losers=0,totalChgPct=0;
    companies.forEach(function(c){
        var st=liveState[c.ticker];if(!st) return;
        totalChgPct+=st.changePct;
        if(st.changeAbs>=0) gainers++; else losers++;
    });
    var avgChg=companies.length?(totalChgPct/companies.length).toFixed(2):'0.00';
    var avgUp=parseFloat(avgChg)>=0;
    var bar=document.getElementById('sectorSummaryBar');if(!bar) return;
    bar.innerHTML='<div class="sector-sum-box"><div class="sector-sum-val">'+companies.length+'</div><div class="sector-sum-lbl">Companies Tracked</div></div>'
        +'<div class="sector-sum-box"><div class="sector-sum-val" style="color:'+(avgUp?'var(--accent-green)':'var(--accent-red)')+'"> '+(avgUp?'▲':'▼')+' '+Math.abs(avgChg)+'%</div><div class="sector-sum-lbl">Avg Daily Change</div></div>'
        +'<div class="sector-sum-box"><div class="sector-sum-val" style="color:var(--accent-green)">'+gainers+' ▲</div><div class="sector-sum-lbl">Gainers</div></div>'
        +'<div class="sector-sum-box"><div class="sector-sum-val" style="color:var(--accent-red)">'+losers+' ▼</div><div class="sector-sum-lbl">Losers</div></div>';
}

function renderSectorCompanies(sector){
    currentSector=sector;
    if(liveInterval) clearInterval(liveInterval);
    var companies=SECTORS_DATA[sector]||[];
    initLiveState(companies);
    var html='';
    companies.forEach(function(c){
        var st=liveState[c.ticker];var up=st.changeAbs>=0;
        var pct=Math.abs(st.changePct).toFixed(2);
        var rangePos=Math.max(2,Math.min(98,((c.basePrice-c.week52low)/(c.week52high-c.week52low)*100))).toFixed(1);
        html+='<div class="company-card"><div class="card-top-bar"></div>'
            +'<div class="co-header"><div class="co-identity"><div class="co-ticker-row"><span class="co-ticker">'+c.ticker+'</span><span class="co-exchange">'+c.exchange+'</span></div>'
            +'<div class="co-name">'+c.name+'</div><div class="co-country">'+c.country+'</div></div>'
            +'<div class="co-price-block"><div class="co-price-val '+(up?'up':'dn')+'" id="price-'+c.ticker+'">'+formatPrice(st.price)+'</div>'
            +'<div class="co-price-chg '+(up?'up':'dn')+'" id="chg-'+c.ticker+'">'+(up?'▲':'▼')+' '+pct+'%</div></div></div>'
            +'<div class="co-sparkline" id="spark-'+c.ticker+'">'+buildSparkline(st.history,up)+'</div>'
            +'<div class="co-stats-row">'
            +'<div class="co-stat"><div class="co-stat-val">'+c.marketcap+'</div><div class="co-stat-lbl">Market Cap</div></div>'
            +'<div class="co-stat"><div class="co-stat-val">'+c.pe+'</div><div class="co-stat-lbl">P/E Ratio</div></div>'
            +'<div class="co-stat"><div class="co-stat-val">'+c.volume+'</div><div class="co-stat-lbl">Avg Volume</div></div></div>'
            +'<div class="co-week-range"><div class="co-week-labels"><span>52W Low: '+formatPrice(c.week52low)+'</span><span style="color:var(--accent-gold);font-weight:700;">'+formatPrice(st.price)+'</span><span>52W High: '+formatPrice(c.week52high)+'</span></div>'
            +'<div class="co-week-bar"><div class="co-week-fill" style="width:'+rangePos+'%"></div><div class="co-week-dot" style="left:'+rangePos+'%"></div></div></div>'
            +'<div class="co-badges">'+c.badges.map(function(b){return '<span class="badge badge-dim">'+b+'</span>';}).join('')+'</div>'
            +'<div class="co-desc">'+c.desc+'</div>'
            +'<div class="co-cta"><span>View M&amp;A Profile →</span><span class="co-cta-live"><span class="live-dot"></span> SIMULATED</span></div></div>';
    });
    document.getElementById('companyGrid').innerHTML=html;
    renderSectorSummary(sector);
    liveInterval=setInterval(function(){tickLivePrices(currentSector);renderSectorSummary(currentSector);},2800);
}

function loadSectors(){
    var sectors=Object.keys(SECTORS_DATA);
    var icons={Technology:'💻',Healthcare:'🏥',Energy:'⚡',Finance:'🏦',Consumer:'🛍️',Industrials:'⚙️',Mining:'⛏️',Defense:'🛡️'};
    var html='';
    sectors.forEach(function(sector,i){
        html+='<button class="sector-tab '+(i===0?'active':'')+'" onclick="switchSector(event,\''+sector+'\')">'+(icons[sector]||'📊')+' '+sector+'</button>';
    });
    document.getElementById('sectorTabs').innerHTML=html;
    renderSectorCompanies('Technology');
}

function switchSector(event,sector){
    document.querySelectorAll('.sector-tab').forEach(function(t){t.classList.remove('active');});
    event.target.closest('.sector-tab').classList.add('active');
    renderSectorCompanies(sector);
}

// ─── STATS GRID (FIX: was missing) ──────────────────────────────────────────
function renderStatsGrid(era){
    var data=DEALS_DATA[era]||[];
    var totalValue=0;
    data.forEach(function(d){
        var v=d.value.replace(/[^0-9.]/g,'');
        totalValue+=parseFloat(v)||0;
    });
    var pending=data.filter(function(d){return d.status==='PENDING';}).length;
    var closed=data.filter(function(d){return d.status==='CLOSED';}).length;
    var rumored=data.filter(function(d){return d.status==='RUMORED';}).length;
    var eraLabels={present:'Active Pipeline',past:'Completed Deals',future:'Rumored Pipeline'};
    var el=document.getElementById('statsGrid');if(!el) return;
    el.innerHTML='<div class="stat-box"><div class="stat-num">'+data.length+'</div><div class="stat-label">Total Deals</div><div class="stat-change up">'+eraLabels[era]+'</div></div>'
        +'<div class="stat-box"><div class="stat-num">$'+totalValue.toFixed(0)+'B</div><div class="stat-label">Combined Value</div><div class="stat-change up">Across all sectors</div></div>'
        +'<div class="stat-box"><div class="stat-num">'+(pending||closed||rumored)+'</div><div class="stat-label">'+(era==='past'?'Closed':'Pending / Rumored')+'</div><div class="stat-change '+(era==='past'?'up':'')+'">'+( era==='past'?'Successfully completed':'Under review / discussion')+'</div></div>'
        +'<div class="stat-box"><div class="stat-num">'+new Set(data.map(function(d){return d.sector;})).size+'</div><div class="stat-label">Sectors Active</div><div class="stat-change up">Cross-sector activity</div></div>';
}

// ─── REGIONS ─────────────────────────────────────────────────────────────────
var REGIONS_DATA=[
    {name:'North America',flag:'🌎',vol:'$890B',deals:2847,yoy:'+12%',top:['Technology','Energy','Finance'],desc:'Dominant global M&A hub. US megadeals in AI, energy, and healthcare drive volume. Canada oil sands consolidation and mining M&A active.'},
    {name:'Europe',flag:'🌍',vol:'$310B',deals:1432,yoy:'+8%',top:['Healthcare','Industrials','Finance'],desc:'Defense spending surge post-Ukraine driving industrial M&A. ECB rate normalisation unlocking PE deals. UK life sciences active.'},
    {name:'Asia Pacific',flag:'🌏',vol:'$245B',deals:1876,yoy:'-4%',top:['Technology','Consumer','Mining'],desc:'Japan PE buyouts at record high. China outbound M&A constrained by CFIUS. India tech and fintech M&A accelerating.'},
    {name:'Middle East',flag:'🏜️',vol:'$68B',deals:312,yoy:'+31%',top:['Infrastructure','Finance','Energy'],desc:'Saudi PIF, Mubadala, ADIA deploying capital globally. Heathrow airport stake ($3.2B). Vision 2030 diversification.'},
    {name:'Latin America',flag:'🌎',vol:'$38B',deals:287,yoy:'+5%',top:['Mining','Energy','Consumer'],desc:'Brazil fintech and agritech active. Chile lithium and copper M&A. Mexico nearshoring industrial.'},
    {name:'Africa',flag:'🌍',vol:'$28B',deals:198,yoy:'+18%',top:['Mining','Telecom','Finance'],desc:'Critical minerals (lithium, cobalt, copper) driving mining M&A. Pan-African fintech consolidation.'},
];

function loadRegions(){
    var html='';
    REGIONS_DATA.forEach(function(r){
        var yoyColor=r.yoy.startsWith('+')?'var(--accent-green)':'var(--accent-red)';
        html+='<div class="region-card"><div class="region-header"><span class="region-flag">'+r.flag+'</span>'
            +'<div class="region-header-body"><div class="region-name">'+r.name+'</div><div class="region-vol">'+r.vol+' YTD 2025</div>'
            +'<div class="region-yoy" style="color:'+yoyColor+'">'+r.yoy+' YoY</div></div></div>'
            +'<div class="region-stats"><span class="region-deals">'+r.deals.toLocaleString()+' deals</span>'
            +'<div class="region-tags">'+r.top.map(function(t){return '<span class="badge badge-dim">'+t+'</span>';}).join('')+'</div></div>'
            +'<div class="region-desc">'+r.desc+'</div></div>';
    });
    var el=document.getElementById('regionsGrid');if(el) el.innerHTML=html;
}

// ─── ALERTS ──────────────────────────────────────────────────────────────────
var ALERTS_DATA=[
    {type:'hot',icon:'🔥',title:'Shell/BP Mega-Merger',body:'Sources confirm preliminary discussions. Combined entity would be $350B+ and the largest energy company globally.'},
    {type:'new',icon:'🆕',title:'SoftBank/OpenAI $40B',body:'SoftBank Vision Fund 3 leading $40B OpenAI funding round. Values OpenAI at $300B pre-money.'},
    {type:'alert',icon:'⚠️',title:'CFIUS Review: Nippon/US Steel',body:'CFIUS review of $14.9B Nippon Steel/US Steel deal in final stage. National security concerns cited.'},
    {type:'closed',icon:'✅',title:'ConocoPhillips/Marathon Closed',body:'$22.5B deal closed August 2024. Creates pure-play E&P giant with 2M+ boe/day production.'},
    {type:'hot',icon:'🔥',title:'JPMorgan/Robinhood Rumor',body:'Multiple sources cite JPMorgan exploring $12B acquisition of Robinhood to accelerate retail wealth management.'},
    {type:'new',icon:'🆕',title:'Apple/Peloton $1.2B',body:'Apple in preliminary talks with Peloton. Hardware integrates with Apple Fitness+ subscription.'},
    {type:'closed',icon:'✅',title:'Broadcom/VMware $61B Closed',body:'Completed November 2023. Broadcom aggressively converting VMware to subscription model.'},
];

function renderAlerts(containerId){
    var html='';
    ALERTS_DATA.forEach(function(a){
        var colors={hot:'var(--accent-red)',new:'var(--accent-gold)',alert:'var(--accent-purple)',closed:'var(--accent-green)'};
        var col=colors[a.type]||'var(--accent-gold)';
        html+='<div class="alert-item"><div class="alert-tag" style="background:'+col+'20;color:'+col+'">'+a.icon+' '+a.type.toUpperCase()+'</div>'
            +'<div style="flex:1"><div style="font-weight:700;color:var(--text-primary);margin-bottom:.3rem;">'+a.title+'</div>'
            +'<div class="alert-text">'+a.body+'</div></div></div>';
    });
    var el=document.getElementById(containerId);if(el) el.innerHTML=html;
}

// ─── SIGNALS ─────────────────────────────────────────────────────────────────
var SIGNAL_CARDS_DATA=[
    {icon:'🤖',title:'AI Infrastructure Wave',signal:'STRONG BUY',color:'var(--accent-green)',body:'Data center, cooling, power, networking — $500B+ capex cycle 2024-2027. Vertiv, Eaton, Arista are M&A targets.'},
    {icon:'💊',title:'GLP-1 Pharma M&A',signal:'ACTIVE',color:'var(--accent-gold)',body:'GLP-1 weight loss drugs creating $100B+ addressable market. Lilly and Novo hunting pipeline assets.'},
    {icon:'⚡',title:'Energy Transition M&A',signal:'ACCELERATING',color:'var(--accent-gold)',body:'IRA $369B incentives catalysing renewable M&A. Lithium, copper, nickel critical mineral consolidation.'},
    {icon:'🛡️',title:'Defense Tech Surge',signal:'STRONG BUY',color:'var(--accent-green)',body:'NATO 2% GDP commitment + Ukraine + Taiwan risk = multi-year defense super-cycle.'},
    {icon:'🏦',title:'PE Dry Powder Deploy',signal:'BUILDING',color:'var(--accent-purple)',body:'$3.9T PE dry powder seeking deployment. Rate normalisation unlocking LBO market.'},
    {icon:'🌏',title:'Japan PE Opportunity',signal:'EMERGING',color:'var(--accent-purple)',body:'TSE pressure on book-value reform, weak yen, aging conglomerates = Japan PE golden era.'},
];

function renderSignals(containerId){
    var html='';
    SIGNAL_CARDS_DATA.forEach(function(s){
        html+='<div class="signal-card"><div style="font-size:2rem;margin-bottom:.75rem">'+s.icon+'</div>'
            +'<div style="margin-bottom:.5rem"><span style="font-size:.65rem;font-weight:800;letter-spacing:.1em;text-transform:uppercase;padding:.2rem .6rem;border-radius:4px;background:'+s.color+'20;color:'+s.color+'">'+s.signal+'</span></div>'
            +'<div style="font-family:\'Plus Jakarta Sans\',sans-serif;font-weight:800;font-size:1rem;color:var(--text-primary);margin-bottom:.6rem">'+s.title+'</div>'
            +'<div style="font-size:.8rem;color:var(--text-secondary);line-height:1.65">'+s.body+'</div></div>';
    });
    var el=document.getElementById(containerId);if(el) el.innerHTML=html;
}

// ─── DEALS TABLE ─────────────────────────────────────────────────────────────
var currentEra='present';

function renderDealsTable(data){
    var html='';
    data.forEach(function(d,i){
        var s=(d.status||'').toUpperCase();
        var sc=s==='CLOSED'?'status-closed':s==='PENDING'?'status-pending':'status-rumored';
        var sl=s==='CLOSED'?'Closed':s==='PENDING'?'Pending':'Rumored';
        html+='<tr><td style="color:var(--text-secondary);font-size:.75rem;">'+(i+1)+'</td>'
            +'<td>'+d.acquirer+'</td><td>'+d.target+'</td>'
            +'<td><div class="deal-value">'+d.value+'</div></td>'
            +'<td><span class="badge badge-dim" style="font-size:.68rem;">'+d.sector+'</span></td>'
            +'<td style="font-size:.78rem;color:var(--text-secondary);">'+(d.region||'')+'</td>'
            +'<td style="font-size:.78rem;color:var(--text-secondary);">'+(d.date||'')+'</td>'
            +'<td style="font-size:.78rem;color:var(--text-secondary);">'+(d.type||'')+'</td>'
            +'<td><span class="deal-status '+sc+'">'+sl+'</span></td></tr>';
    });
    var tbody=document.getElementById('dealsBody');
    if(tbody) tbody.innerHTML=html||'<tr><td colspan="9" style="text-align:center;color:var(--text-secondary);padding:2rem;">No deals found</td></tr>';
    var countEl=document.getElementById('dealCount');
    if(countEl) countEl.textContent=data.length+' deals';
}

function switchEra(event,era){
    currentEra=era;
    document.querySelectorAll('.deal-era-btn').forEach(function(t){t.classList.remove('active');});
    event.target.closest('.deal-era-btn').classList.add('active');
    renderStatsGrid(era);
    filterDeals();
}

function filterDeals(){
    var search=(document.getElementById('dealSearch')||{}).value||'';
    var sector=(document.getElementById('sectorFilter')||{}).value||'';
    var region=(document.getElementById('regionFilter')||{}).value||'';
    var data=(DEALS_DATA[currentEra]||[]).filter(function(d){
        var q=search.toLowerCase();
        var ms=!q||d.acquirer.toLowerCase().includes(q)||d.target.toLowerCase().includes(q)||(d.sector||'').toLowerCase().includes(q);
        var mc=!sector||d.sector===sector;
        var mr=!region||(d.region||'')===region;
        return ms&&mc&&mr;
    });
    renderDealsTable(data);
}

// ─── KPI / INTELLIGENCE ─────────────────────────────────────────────────────
var KPI_DATA=[
    {label:'Global M&A Volume YTD',value:'$2.1T',sub:'+18% vs 2024',up:true},
    {label:'Deals Tracked',value:'6,840',sub:'Active pipeline',up:true},
    {label:'Avg Deal Premium',value:'36%',sub:'+4pts vs 2024',up:true},
    {label:'Deals in Reg Review',value:'120+',sub:'$800B+ value',up:false},
    {label:'PE Dry Powder',value:'$3.9T',sub:'Record high',up:true},
    {label:'Avg EV/EBITDA Multiple',value:'14.2x',sub:'+0.8x YoY',up:true},
    {label:'Cross-Border Deals',value:'38%',sub:'Of total volume',up:true},
    {label:'Tech Sector Share',value:'31%',sub:'of all M&A value',up:true},
];

function loadIntelligence(){
    var html='';
    KPI_DATA.forEach(function(k){
        html+='<div class="card" style="text-align:center;padding:1.5rem;">'
            +'<div style="font-size:.65rem;text-transform:uppercase;letter-spacing:.12em;color:var(--text-secondary);font-weight:700;margin-bottom:.5rem">'+k.label+'</div>'
            +'<div style="font-size:1.8rem;font-weight:900;color:var(--text-primary)">'+k.value+'</div>'
            +'<div style="font-size:.72rem;color:'+(k.up?'var(--accent-green)':'var(--accent-red)')+';margin-top:.35rem;font-weight:600">'+k.sub+'</div></div>';
    });
    var el=document.getElementById('kpiGrid');if(el) el.innerHTML=html;
    renderAlerts('alertsList');
    renderSignals('signalCards');
}


// ─── CHAT / ANALYSIS (Local AI responses — no API key needed) ────────────────
var chatHistory=[];

var QUICK_QUERIES=[
    'What are the largest pending M&A deals right now?',
    'Analyze regulatory risk for tech mega-mergers in 2025',
    'Which sectors have the highest M&A activity this year?',
    'What is a typical EV/EBITDA multiple for healthcare acquisitions?',
    'Explain the Shell/BP merger rumor and its implications',
    'What PE dry powder is available and where is it being deployed?',
];

var AI_RESPONSES={
    'What are the largest pending M&A deals right now?':
        '<strong>Top 5 Pending M&A Deals (by value):</strong><br><br>'
        +'1. <strong>Chevron → Hess Corporation</strong> — $53.0B (Energy, pending ICC arbitration with ExxonMobil over Guyana JV pre-emption rights)<br>'
        +'2. <strong>Mars Inc. → Kellanova</strong> — $36.0B (Consumer, largest food sector deal in over a decade)<br>'
        +'3. <strong>Capital One → Discover Financial</strong> — $35.3B (Finance, DOJ antitrust review ongoing, combined entity would be largest US card issuer by volume)<br>'
        +'4. <strong>Synopsys → Ansys</strong> — $35.0B (Technology, EU Phase II review, creates EDA+simulation monopoly concern)<br>'
        +'5. <strong>Alphabet → Wiz</strong> — $23.0B (Technology, largest cybersecurity acquisition ever, DOJ scrutiny given Google\'s market position)<br><br>'
        +'<em>Combined pending pipeline: $200B+ across these 5 deals alone. Average time to close: 12–18 months due to regulatory complexity.</em>',

    'Analyze regulatory risk for tech mega-mergers in 2025':
        '<strong>Tech M&A Regulatory Landscape — 2025:</strong><br><br>'
        +'<strong>🇺🇸 US (DOJ/FTC):</strong> The Biden-era antitrust framework persists. DOJ has challenged or deeply scrutinized every tech deal >$10B since 2022. Key risk areas: AI compute concentration (Nvidia acquisitions), cloud market share (Google, Microsoft), and data aggregation (Meta).<br><br>'
        +'<strong>🇪🇺 EU (DG COMP):</strong> The Digital Markets Act (DMA) creates additional scrutiny for "gatekeepers." Phase II reviews now standard for any deal involving GAFAM. Average review timeline: 14 months.<br><br>'
        +'<strong>🇬🇧 UK (CMA):</strong> Post-Brexit, CMA has emerged as the most aggressive global regulator. Blocked Microsoft/Activision initially, forced concessions on Adobe/Figma withdrawal.<br><br>'
        +'<strong>Assessment:</strong> Regulatory risk is at a 20-year high for tech mega-deals. Expect 6–18 month delays, behavioral remedies, and potential divestitures. Deals under $5B face significantly less scrutiny.',

    'Which sectors have the highest M&A activity this year?':
        '<strong>2025 YTD M&A by Sector (ranked by deal volume):</strong><br><br>'
        +'1. <strong>Technology — $714B</strong> (31% of global volume): AI infrastructure, cybersecurity, and semiconductor consolidation driving activity. Key deals: Alphabet/Wiz $23B, Synopsys/Ansys $35B<br>'
        +'2. <strong>Energy — $540B</strong> (23%): Oil & gas consolidation continues. Chevron/Hess $53B. Renewable energy and battery metals M&A accelerating<br>'
        +'3. <strong>Healthcare — $380B</strong> (16%): GLP-1 obesity drugs creating $100B+ market. ADC oncology deals. Sanofi/Blueprint $7B, Thermo Fisher/Solventum $6.1B<br>'
        +'4. <strong>Finance — $280B</strong> (12%): Banking consolidation + PE/credit platform acquisitions. Capital One/Discover $35.3B headliner<br>'
        +'5. <strong>Consumer — $190B</strong> (8%): Mars/Kellanova $36B dominates. Luxury M&A active in Europe<br><br>'
        +'<em>Total 2025 YTD: ~$2.1T across 4,847 deals. Tech\'s share has grown from 24% to 31% YoY, reflecting AI capital deployment.</em>',

    'What is a typical EV/EBITDA multiple for healthcare acquisitions?':
        '<strong>Healthcare M&A Valuation Multiples (2024–2025):</strong><br><br>'
        +'• <strong>Large-Cap Pharma:</strong> 12–16x EV/EBITDA (Pfizer/Seagen closed at ~25x forward, reflecting premium for ADC pipeline)<br>'
        +'• <strong>Biotech (pre-revenue):</strong> Valued on pipeline DCF, typically 3–8x peak sales estimates. Premiums of 40–80% to unaffected price common<br>'
        +'• <strong>MedTech/Devices:</strong> 18–25x EV/EBITDA (premium for recurring revenue, e.g., Intuitive Surgical trades at 68x P/E)<br>'
        +'• <strong>CROs/CDMOs:</strong> 14–20x (Catalent acquired at ~16x by Novo Nordisk for $11B)<br>'
        +'• <strong>Digital Health:</strong> 8–15x revenue (compressed from 20–40x in 2021 SPAC era)<br><br>'
        +'<em>Key driver: GLP-1/obesity pipeline assets command 30–50% control premiums above sector average due to $100B+ TAM.</em>',

    'Explain the Shell/BP merger rumor and its implications':
        '<strong>Shell/BP Merger Analysis:</strong><br><br>'
        +'<strong>The Rumor:</strong> Multiple financial press sources report preliminary discussions between Shell plc and BP plc for a potential merger of equals. Estimated combined value: $350B+, creating the world\'s largest energy company by production and reserves.<br><br>'
        +'<strong>Strategic Rationale:</strong><br>'
        +'• Combined production: ~5.5M boe/day (surpassing Saudi Aramco\'s recent output)<br>'
        +'• Cost synergies: $5–8B annually from overlapping downstream, trading, and corporate functions<br>'
        +'• BP has underperformed peers by 30%+ over 3 years — merger provides a re-rating catalyst<br>'
        +'• Combined LNG portfolio would be world\'s largest, providing gas-to-power strategic advantage<br><br>'
        +'<strong>Challenges:</strong> EU and UK competition review (likely 18+ months), workforce/HQ political sensitivity, culture integration risk, and $100B+ combined net debt.<br><br>'
        +'<em>Probability assessment: 25–30%. Most likely outcome is a BP standalone restructuring or partial asset deal rather than full merger.</em>',

    'What PE dry powder is available and where is it being deployed?':
        '<strong>Private Equity Dry Powder — 2025 Overview:</strong><br><br>'
        +'<strong>Total Global PE Dry Powder: $3.9T</strong> (record high)<br><br>'
        +'<strong>By Strategy:</strong><br>'
        +'• Buyout: $1.1T (KKR, Apollo, Blackstone, Carlyle leading)<br>'
        +'• Growth Equity: $680B (primarily AI/tech focused)<br>'
        +'• Venture Capital: $540B (AI, biotech, climate tech)<br>'
        +'• Private Credit: $480B (fastest growing, direct lending)<br>'
        +'• Infrastructure: $420B (data centers, renewables, transport)<br>'
        +'• Real Estate: $380B (distressed office, data center REITs)<br><br>'
        +'<strong>Deployment Hotspots:</strong><br>'
        +'• Japan buyouts ($20B+ deployed 2024, accelerating)<br>'
        +'• US healthcare services roll-ups<br>'
        +'• European industrial carve-outs<br>'
        +'• AI infrastructure (data centers, GPU clusters)<br>'
        +'• India technology and consumer companies<br><br>'
        +'<em>LP pressure to deploy is mounting — average fund age for undeployed capital is 3.2 years, approaching typical 5-year investment period limits.</em>',
};

function loadQuickBtns(){
    var html='';
    QUICK_QUERIES.forEach(function(q){
        html+='<button class="quick-btn" onclick="askQuestion(\''+q.replace(/'/g,"\\'")+'\')">'+ q+'</button>';
    });
    var el=document.getElementById('quickBtns');if(el) el.innerHTML=html;
}

function askQuestion(q){
    var input=document.getElementById('chatInput');
    if(input){input.value=q;sendMessage();}
}

function addMessage(role,text){
    var msgs=document.getElementById('chatMessages');if(!msgs) return;
    var div=document.createElement('div');
    div.className='msg msg-'+(role==='user'?'user':'ai');
    div.innerHTML='<div class="msg-label">'+(role==='user'?'YOU':'M&A AI ASSISTANT')+'</div><div>'+text+'</div>';
    msgs.appendChild(div);msgs.scrollTop=msgs.scrollHeight;
}

function addTyping(){
    var msgs=document.getElementById('chatMessages');if(!msgs) return null;
    var div=document.createElement('div');div.className='msg msg-ai';div.id='typingMsg';
    div.innerHTML='<div class="msg-label">M&A AI ASSISTANT</div><div><span class="typing-indicator"><span></span><span></span><span></span></span></div>';
    msgs.appendChild(div);msgs.scrollTop=msgs.scrollHeight;return div;
}

function getLocalAIResponse(query){
    var q=query.toLowerCase();
    // Check exact matches first
    for(var key in AI_RESPONSES){
        if(query===key) return AI_RESPONSES[key];
    }
    // Fuzzy keyword matching
    if(q.includes('pending')||q.includes('largest deal')) return AI_RESPONSES['What are the largest pending M&A deals right now?'];
    if(q.includes('regulat')||q.includes('antitrust')||q.includes('doj')||q.includes('ftc')) return AI_RESPONSES['Analyze regulatory risk for tech mega-mergers in 2025'];
    if(q.includes('sector')||q.includes('activity')||q.includes('which sector')) return AI_RESPONSES['Which sectors have the highest M&A activity this year?'];
    if(q.includes('multiple')||q.includes('ebitda')||q.includes('valuation')||q.includes('healthcare')) return AI_RESPONSES['What is a typical EV/EBITDA multiple for healthcare acquisitions?'];
    if(q.includes('shell')||q.includes('bp')||q.includes('merger rumor')) return AI_RESPONSES['Explain the Shell/BP merger rumor and its implications'];
    if(q.includes('dry powder')||q.includes('private equity')||q.includes('pe ')) return AI_RESPONSES['What PE dry powder is available and where is it being deployed?'];

    // Generic fallback
    return '<strong>M&A Intelligence Analysis:</strong><br><br>'
        +'Based on our current dataset of 6,840+ tracked deals across all sectors and regions, here are the key highlights relevant to your query:<br><br>'
        +'• <strong>Global M&A volume</strong> has reached $2.1T YTD in 2025, up 18% versus the same period in 2024<br>'
        +'• <strong>Technology</strong> remains the dominant sector at 31% of total deal value, driven by AI infrastructure consolidation<br>'
        +'• <strong>Average deal premium</strong> stands at 36%, up 4 percentage points from 2024<br>'
        +'• <strong>120+ deals</strong> are currently in regulatory review, representing over $800B in combined value<br>'
        +'• <strong>PE dry powder</strong> stands at a record $3.9T, creating significant deployment pressure<br><br>'
        +'<em>For more specific analysis, try asking about particular deals, sectors, valuations, or regulatory risks. Use the quick queries on the right for pre-built analyses.</em>';
}

function sendMessage(){
    var input=document.getElementById('chatInput');
    var btn=document.getElementById('sendBtn');
    if(!input||!btn) return;
    var text=input.value.trim();if(!text) return;
    input.value='';btn.disabled=true;
    addMessage('user',text);
    var typing=addTyping();
    // Simulate AI thinking delay for realism
    var delay=800+Math.random()*1200;
    setTimeout(function(){
        if(typing) typing.remove();
        var reply=getLocalAIResponse(text);
        addMessage('assistant',reply);
        btn.disabled=false;
    },delay);
}

function initChat(){
    addMessage('assistant','Welcome to the M&A Intelligence Engine. I can analyze deal flow, valuations, regulatory risks, sector trends, and more. Ask me anything about global M&A — or use the quick queries on the right to get started.<br><br><em style="font-size:.75rem;color:var(--text-tertiary);">Responses are generated from our built-in M&A knowledge base covering 6,840+ tracked deals.</em>');
    loadQuickBtns();
}

// ─── MAKE DEALS ──────────────────────────────────────────────────────────────
var MD_SECTORS=[
    {name:'Technology',icon:'💻',desc:'Software, hardware, semiconductors, AI, cloud, cybersecurity & EDA',dealVol:'$714B',deals:'1,840',multiple:'18.4x EBITDA',hotArea:'AI Infrastructure'},
    {name:'Healthcare',icon:'🏥',desc:'Pharma, biotech, med-tech, diagnostics, CRO & health services',dealVol:'$380B',deals:'920',multiple:'14.2x EBITDA',hotArea:'GLP-1 / Oncology'},
    {name:'Energy',icon:'⚡',desc:'Oil & gas, LNG, renewables, utilities, battery metals & EV supply',dealVol:'$540B',deals:'760',multiple:'8.6x EBITDA',hotArea:'Critical Minerals'},
    {name:'Finance',icon:'🏦',desc:'Banking, insurance, asset management, PE, fintech & payments',dealVol:'$280B',deals:'640',multiple:'12.1x EBITDA',hotArea:'Private Credit'},
    {name:'Consumer',icon:'🛍️',desc:'Retail, food & beverage, luxury, e-commerce, FMCG & QSR',dealVol:'$190B',deals:'580',multiple:'11.8x EBITDA',hotArea:'Premium / Luxury'},
    {name:'Industrials',icon:'⚙️',desc:'Aerospace, defence, heavy equipment, automation & supply chain',dealVol:'$210B',deals:'420',multiple:'10.4x EBITDA',hotArea:'Defence Tech'},
    {name:'Media & Telecom',icon:'📡',desc:'Streaming, broadcasting, cable, mobile networks & content',dealVol:'$145B',deals:'310',multiple:'9.2x EBITDA',hotArea:'Sports Rights'},
    {name:'Real Estate',icon:'🏢',desc:'REITs, data center properties, logistics hubs & commercial RE',dealVol:'$98B',deals:'280',multiple:'16.8x FFO',hotArea:'Data Centers'},
    {name:'Mining',icon:'⛏️',desc:'Copper, lithium, cobalt, gold, iron ore & rare earth elements',dealVol:'$120B',deals:'360',multiple:'6.8x EBITDA',hotArea:'Lithium / Copper'},
    {name:'Defense',icon:'🛡️',desc:'Defence prime contractors, hypersonics, space, and cyber warfare',dealVol:'$85B',deals:'190',multiple:'13.6x EBITDA',hotArea:'AI Weapons Systems'},
];

function loadMakeDeals(){
    var html='<div class="deal-type-row">'
        +'<button class="deal-type-btn btn-merger" onclick="openModal(\'mergerModal\')"><span class="btn-icon">🤝</span> Merger<span class="btn-sub">Combine equals for shared growth</span></button>'
        +'<button class="deal-type-btn btn-acquisition" onclick="openModal(\'acquisitionModal\')"><span class="btn-icon">🎯</span> Acquisition<span class="btn-sub">Buy &amp; integrate a target company</span></button>'
        +'</div>'
        +'<div class="section-label-gold">Explore by Sector</div><div class="md-sector-grid">';
    MD_SECTORS.forEach(function(s){
        html+='<div class="md-sector-card"><div class="md-sector-icon">'+s.icon+'</div>'
            +'<div class="md-sector-title">'+s.name+'</div><div class="md-sector-sub">'+s.desc+'</div>'
            +'<div style="background:rgba(201,168,76,.1);border-radius:6px;padding:.5rem .75rem;margin-bottom:1rem;font-size:.75rem;color:var(--accent-gold);font-weight:600;">🔥 Hot: '+s.hotArea+' · Avg '+s.multiple+'</div>'
            +'<div class="md-sector-stats"><div><div class="md-sector-stat-num" style="color:var(--accent-gold);">'+s.dealVol+'</div><div class="md-sector-stat-lbl">YTD Vol.</div></div>'
            +'<div><div class="md-sector-stat-num" style="color:var(--text-primary);">'+s.deals+'</div><div class="md-sector-stat-lbl">Active Deals</div></div></div></div>';
    });
    html+='</div>';
    document.getElementById('mdContent').innerHTML=html;
}

// ─── MODAL ───────────────────────────────────────────────────────────────────
var modalState={m:{step:1,sector:null,value:'$500M',goal:null},a:{step:1,sector:null,value:'$500M',goal:null}};
var SECTOR_OPTIONS=[
    {name:'Technology',icon:'💻'},{name:'Healthcare',icon:'🏥'},{name:'Energy',icon:'⚡'},
    {name:'Finance',icon:'🏦'},{name:'Consumer',icon:'🛍️'},{name:'Industrials',icon:'⚙️'},
    {name:'Media & Telecom',icon:'📡'},{name:'Real Estate',icon:'🏢'},{name:'Mining',icon:'⛏️'},{name:'Defense',icon:'🛡️'},
];
var MERGER_GOALS=[
    {icon:'🌍',title:'Geographic Expansion',desc:'Enter new countries or regions'},
    {icon:'🔬',title:'Technology / IP Access',desc:'Gain proprietary tech or patents'},
    {icon:'📈',title:'Revenue Scale',desc:'Double revenue via combined entity'},
    {icon:'🏭',title:'Vertical Integration',desc:'Control more of the supply chain'},
];
var ACQUISITION_GOALS=[
    {icon:'🤖',title:'Acqui-hire',desc:'Primarily acquiring the team & talent'},
    {icon:'💡',title:'Innovation Buy',desc:'Bring in new products or technology'},
    {icon:'🚫',title:'Eliminate Competitor',desc:'Remove a rival from the market'},
    {icon:'📊',title:'Financial Returns',desc:'PE-style value creation & exit'},
];

function sliderToValue(v){
    var bp=[[0,10,'$50M'],[10,20,'$100M'],[20,30,'$250M'],[30,40,'$500M'],[40,50,'$1B'],[50,60,'$2B'],[60,70,'$5B'],[70,80,'$10B'],[80,90,'$25B'],[90,100,'$50B+']];
    for(var i=0;i<bp.length;i++){if(v>=bp[i][0]&&v<bp[i][1]) return bp[i][2];}
    return '$50B+';
}
function updateValueDisplay(elId,val,prefix){
    document.getElementById(elId).textContent=sliderToValue(parseInt(val));
    modalState[prefix].value=sliderToValue(parseInt(val));
}
function openModal(id){
    var prefix=id==='mergerModal'?'m':'a';
    modalState[prefix]={step:1,sector:null,value:'$500M',goal:null};
    buildModalStep1(prefix);document.getElementById(id).classList.add('open');document.body.style.overflow='hidden';
}
function closeModal(id){document.getElementById(id).classList.remove('open');document.body.style.overflow='';}

function buildModalStep1(p){
    var gridId=p==='m'?'m-sector-grid':'a-sector-grid';
    var html='';
    SECTOR_OPTIONS.forEach(function(s){
        html+='<div class="option-pill" data-val="'+s.name+'" onclick="selectOption(this,\''+p+'\',\'sector\')"><span class="pill-icon">'+s.icon+'</span>'+s.name+'</div>';
    });
    document.getElementById(gridId).innerHTML=html;
    var goals=p==='m'?MERGER_GOALS:ACQUISITION_GOALS;
    var gGridId=p==='m'?'m-goal-grid':'a-goal-grid';
    var gHtml='';
    goals.forEach(function(g){
        gHtml+='<div class="goal-card" data-val="'+g.title+'" onclick="selectGoalCard(this,\''+p+'\')"><div class="goal-card-icon">'+g.icon+'</div><div class="goal-card-title">'+g.title+'</div><div class="goal-card-desc">'+g.desc+'</div></div>';
    });
    document.getElementById(gGridId).innerHTML=gHtml;
}

function selectOption(el,prefix,field){
    el.closest('.option-grid').querySelectorAll('.option-pill').forEach(function(p){p.classList.remove('selected');});
    el.classList.add('selected');modalState[prefix][field]=el.dataset.val;
    document.getElementById(prefix+'-next-btn').disabled=false;
}
function selectGoalCard(el,prefix){
    el.closest('.goal-grid').querySelectorAll('.goal-card').forEach(function(c){c.classList.remove('selected');});
    el.classList.add('selected');modalState[prefix].goal=el.dataset.val;
    document.getElementById(prefix+'-next-btn').disabled=false;
}
function setModalStep(p,step){
    modalState[p].step=step;
    var modalId=p==='m'?'mergerModal':'acquisitionModal';
    document.querySelectorAll('#'+modalId+' .modal-step').forEach(function(s){s.classList.remove('active');});
    document.getElementById(p+'step-'+step).classList.add('active');
    for(var i=1;i<=4;i++){var dot=document.getElementById(p+'step-dot-'+i);if(dot) dot.classList.toggle('done',i<=step);}
    var labels=['','Step 1 of 3','Step 2 of 3','Step 3 of 3','Your Results'];
    document.getElementById(p+'step-label').textContent=labels[step]||'';
    document.getElementById(p+'-back-btn').style.display=step>1?'block':'none';
    var btn=document.getElementById(p+'-next-btn');
    if(step===4){btn.textContent='✕ Close';btn.onclick=function(){closeModal(p==='m'?'mergerModal':'acquisitionModal');};}
    else{btn.style.display='block';btn.textContent=step===3?'✨ Get Recommendations':'Continue →';
        btn.onclick=function(){modalNext(p);};
        btn.disabled=(step===1&&!modalState[p].sector)||(step===3&&!modalState[p].goal);}
}
function modalNext(p){
    var cur=modalState[p].step;
    if(cur===2){modalState[p].value=sliderToValue(parseInt(document.getElementById(p+'-value-slider').value));}
    if(cur<3){setModalStep(p,cur+1);}
    else{buildResults(p);setModalStep(p,4);}
}
function modalBack(p){var cur=modalState[p].step;if(cur>1) setModalStep(p,cur-1);}

// ─── COMPLETE RESULTS FOR ALL SECTORS ────────────────────────────────────────
var ALL_RESULTS={
    Technology:[
        {name:'Palo Alto Networks',val:'$105B',fit:'96%',tags:['Cybersecurity','AI'],desc:'Best-in-class cybersecurity platform. Combined entity creates end-to-end secure cloud infrastructure giant.'},
        {name:'Snowflake Inc.',val:'$48B',fit:'91%',tags:['Data Cloud','Analytics'],desc:'Data cloud leader with 9,000+ enterprise customers. AI+data flywheel unlocks combined value.'},
        {name:'Hugging Face',val:'$4.5B',fit:'88%',tags:['Open Source AI','Developer'],desc:'1M+ AI models hosted — the GitHub of AI. Locks in developer community and model distribution.'}],
    Healthcare:[
        {name:'Daiichi Sankyo',val:'$52B',fit:'94%',tags:['ADC Oncology','Pipeline'],desc:'ADC pioneer — creator of Enhertu. Brings world-class manufacturing and three Phase 3 oncology assets.'},
        {name:'Relay Therapeutics',val:'$2.1B',fit:'91%',tags:['Precision Oncology','PI3K'],desc:'RLY-2608 showing 45% objective response rate in breast cancer — best-in-class efficacy data.'},
        {name:'Genmab A/S',val:'$18B',fit:'86%',tags:['Bispecific Antibodies','EU'],desc:'Bispecific antibody pioneer. European HQ provides EU market access advantage.'}],
    Energy:[
        {name:'Coterra Energy',val:'$18B',fit:'94%',tags:['Permian+Marcellus','FCF Rich'],desc:'Unique dual-basin producer. $3B+ annual FCF, low $35/bbl breakeven. LNG export optionality.'},
        {name:'Redwood Materials',val:'$5B',fit:'91%',tags:['Battery Recycling','EV'],desc:'Founded by JB Straubel (Tesla CTO). Only US-scale battery recycling company. DoE $2B loan.'},
        {name:'Bloom Energy',val:'$3.5B',fit:'85%',tags:['Fuel Cells','Data Center'],desc:'Solid oxide fuel cells providing 24/7 clean power to data centers. AI demand driving backlog growth.'}],
    Finance:[
        {name:'Robinhood Markets',val:'$15B',fit:'92%',tags:['Retail Brokerage','Fintech'],desc:'24M+ funded accounts. Brings retail brokerage platform to institutional acquirer.'},
        {name:'Nubank (Nu Holdings)',val:'$60B',fit:'91%',tags:['Neobank','LatAm'],desc:"World's largest digital bank outside Asia. 105M+ customers. Revenue growing 60%+ YoY."},
        {name:'Klarna Group',val:'$20B',fit:'88%',tags:['BNPL','85M users'],desc:'Buy-Now-Pay-Later leader: 85M consumers, 500K merchants, $80B+ GMV.'}],
    Consumer:[
        {name:'Peloton Interactive',val:'$1.2B',fit:'93%',tags:['Connected Fitness','Subscription'],desc:'7M+ subscribers, premium hardware ecosystem. Integrates with Apple Fitness+ or Amazon Prime.'},
        {name:"Tod's Group",val:'$1.5B',fit:'89%',tags:['Italian Luxury','Heritage'],desc:'Italian luxury house with 400+ retail stores. LVMH delisting bid signals sector consolidation.'},
        {name:'Instacart (Maplebear)',val:'$10B',fit:'85%',tags:['Grocery Delivery','Advertising'],desc:'Leading US grocery delivery. Ad platform monetises 1.4B orders/year. Strategic fit for Walmart or Amazon.'}],
    Industrials:[
        {name:'Vertiv Holdings',val:'$38B',fit:'95%',tags:['Data Center Cooling','Power'],desc:'#1 data center thermal management and UPS. Revenue growing 25%+ as AI drives cooling demand.'},
        {name:'BWX Technologies',val:'$10B',fit:'90%',tags:['Nuclear','Naval Reactors'],desc:'Monopoly supplier of US Navy nuclear reactors. AUKUS submarines driving 20-year backlog.'},
        {name:'Roper Technologies',val:'$58B',fit:'86%',tags:['Industrial Software','Niche'],desc:'Portfolio of 27 niche industrial software businesses. 40%+ EBITDA margins, asset-light model.'}],
    'Media & Telecom':[
        {name:'Paramount Global',val:'$9.5B',fit:'94%',tags:['Content Library','Streaming'],desc:'120K+ hours of content library. CBS, MTV, Nickelodeon, Paramount+. Content arms race target.'},
        {name:'Spotify Technology',val:'$85B',fit:'89%',tags:['Audio Streaming','550M Users'],desc:'550M users, 220M premium subscribers. Podcast and audiobook expansion. Now profitable.'},
        {name:'Endeavor Group',val:'$13B',fit:'85%',tags:['Sports/Entertainment','UFC/WWE'],desc:'UFC owner, WME talent agency, PBR. Sports IP monetisation platform. Silver Lake $13B take-private.'}],
    'Real Estate':[
        {name:'Digital Realty Trust',val:'$48B',fit:'95%',tags:['Data Centers','Global REIT'],desc:'300+ data centers across 50 metros. AI training demand driving 20%+ lease rate increases.'},
        {name:'Prologis',val:'$108B',fit:'88%',tags:['Logistics REIT','Global'],desc:"World's largest logistics REIT. 1.2B sqft. Amazon, FedEx, DHL as tenants. E-commerce tailwind."},
        {name:'CBRE Group',val:'$36B',fit:'84%',tags:['Commercial RE Services','Advisory'],desc:'#1 commercial real estate services firm globally. Data and advisory revenue growing 15%+ YoY.'}],
    Mining:[
        {name:'Lithium Americas',val:'$1.8B',fit:'95%',tags:['Thacker Pass','US Lithium'],desc:"Thacker Pass — largest known lithium deposit in the US. GM $650M JV. Critical to US EV supply chain."},
        {name:'Ivanhoe Mines',val:'$8B',fit:'91%',tags:['Copper','DRC Congo'],desc:'Kamoa-Kakula — highest-grade major copper discovery globally. 600K+ tonnes/year production target.'},
        {name:'Pilbara Minerals',val:'$7B',fit:'86%',tags:['Lithium Spodumene','Australia'],desc:"Australia's largest hard-rock lithium producer. Pilgangoora mine with 100-year resource life."}],
    Defense:[
        {name:'L3Harris Technologies',val:'$42B',fit:'94%',tags:['C4ISR','Space','Electronic Warfare'],desc:'Communications, space, and electronic warfare systems. 80% of revenue from US DoD.'},
        {name:'Anduril Industries',val:'$14B',fit:'92%',tags:['Autonomous Drones','AI Defense'],desc:'Palmer Luckey-founded defense tech unicorn. Lattice AI platform. Counter-drone systems deployed.'},
        {name:'Shield AI',val:'$2.7B',fit:'88%',tags:['Autonomous Aircraft','V-BAT'],desc:'AI pilot Hivemind powers autonomous aircraft. V-BAT drones deployed by US military and allies.'}],
};

function buildResults(p){
    var state=modalState[p];var isMerger=p==='m';
    var elId=isMerger?'merger-results':'acquisition-results';
    var typeLabel=isMerger?'Merger Partner':'Acquisition Target';
    var icon=isMerger?'🤝':'🎯';
    var sector=state.sector||'Technology';
    var html='<div class="results-header"><div class="results-header-icon">'+icon+'</div>'
        +'<div><div class="results-header-title">Top '+typeLabel+'s for '+sector+' · '+state.value+'</div>'
        +'<div class="results-header-sub">Goal: '+(state.goal||'Strategic Growth')+' · Ranked by strategic fit</div></div></div>';
    var comps=ALL_RESULTS[sector]||ALL_RESULTS['Technology'];
    var ranks=['🥇','🥈','🥉'];
    comps.forEach(function(c,i){
        html+='<div class="result-card rank-'+(i+1)+'">'
            +'<div class="result-rank">'+ranks[i]+' #'+(i+1)+' MATCH</div>'
            +'<div class="result-company">'+c.name+'</div>'
            +'<div class="result-meta">Est. Value: '+c.val+'</div>'
            +'<div class="result-tags"><span class="result-tag fit">✓ '+c.fit+' Fit</span>'
            +c.tags.map(function(t){return '<span class="result-tag value">'+t+'</span>';}).join('')+'</div>'
            +'<div class="result-desc">'+c.desc+'</div></div>';
    });
    html+='<div style="margin-top:1.5rem;padding:1rem;background:var(--bg-tertiary);border-radius:8px;font-size:.75rem;color:var(--text-secondary);line-height:1.6;">'
        +'<strong style="color:var(--accent-gold);">⚠️ Disclaimer:</strong> These recommendations are generated from our M&A database for screening purposes only. '
        +'Actual deal execution requires professional advisory, due diligence, and regulatory review. Contact your M&A advisor for actionable next steps.</div>';
    document.getElementById(elId).innerHTML=html;
}

// ─── INIT ────────────────────────────────────────────────────────────────────
window.addEventListener('DOMContentLoaded',function(){
    // Theme restore
    try{
        var saved=localStorage.getItem('theme')||'light';
        if(saved==='dark'){document.documentElement.classList.add('dark-mode');document.getElementById('themeToggle').textContent='☀️';}
    }catch(e){}

    // Set last updated timestamp
    var now=new Date();
    var upd=document.getElementById('lastUpdated');
    if(upd) upd.textContent=now.toLocaleDateString('en-US',{month:'short',day:'numeric',year:'numeric'})+' '+now.toLocaleTimeString('en-US',{hour:'2-digit',minute:'2-digit'});

    // Close modals on overlay click
    document.querySelectorAll('.modal-overlay').forEach(function(el){
        el.addEventListener('click',function(e){if(e.target===el) closeModal(el.id);});
    });

    // Simulate loading delay for skeleton states
    setTimeout(function(){
        initTicker();
        renderStatsGrid('present');
        renderDealsTable(DEALS_DATA['present']);
        document.getElementById('dealCount').textContent=DEALS_DATA['present'].length+' deals';
        loadSectors();
        loadRegions();
        renderAlerts('alertsContainer');
        renderSignals('signalsGrid');
        loadIntelligence();
        loadMakeDeals();
        initChat();
    },400);
});

</script>
</body>
</html>
