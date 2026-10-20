<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Secret Room Investigation Test v47 | Little Dino’s Kitchen Adventures</title>
<style>
:root{--cream:#fff8e8;--green:#315c36;--pink:#f28ba8;--brown:#8a5a3b}
*{box-sizing:border-box}
body{margin:0;background:var(--cream);color:var(--green);font-family:system-ui,-apple-system,Segoe UI,sans-serif;text-align:center}
.wrap{max-width:1200px;margin:auto;padding:18px 12px 34px}
.title{font-weight:800;font-size:clamp(25px,4vw,44px);color:var(--pink);margin:4px 0 2px}
.sub{margin:0 0 16px;font-size:clamp(15px,2vw,20px);color:var(--green)}
.map{position:relative;width:100%;overflow:hidden;border-radius:22px;box-shadow:0 8px 28px rgba(70,45,20,.18);background:#fff}
.map img{display:block;width:100%;height:auto}
.hotspot{position:absolute;background:transparent;border:0;padding:0;cursor:pointer;z-index:2}
.hotspot:focus-visible{outline:3px solid #fff;border-radius:18px;box-shadow:0 0 0 5px var(--pink)}
.panel{display:none;margin:18px auto 0;max-width:900px;background:#fff0f4;border:3px solid #f7b0c3;border-radius:20px;padding:18px;text-align:left;box-shadow:0 5px 18px rgba(70,45,20,.1)}
.panel.show{display:block}
.panel h2{margin:0 0 8px;color:#a94c6a;font-size:clamp(22px,3vw,30px)}
.panel p{margin:0 0 10px;line-height:1.5}
.panel ul{margin:8px 0 0;padding:0;list-style:none;display:grid;gap:8px}
.fridge-search{margin:12px 0;padding:12px;border:2px solid #b9cbb2;border-radius:14px;background:linear-gradient(135deg,#f1f7ed,#fff8ed)}.fridge-search label{display:block;font-weight:800;margin-bottom:7px;color:#315c36}.fridge-search input{width:100%;min-width:0;border:1px solid #b9cbb2;border-radius:10px;padding:12px;background:#fff;color:#315c36;font:inherit}.fridge-search p{font-size:.92em;margin:7px 0 0;color:#5b6958}.fridge-empty{padding:12px;background:#fff;border:1px dashed #b9cbb2;border-radius:12px;margin-top:8px}
.tip-choice{display:block;width:100%;text-align:left;padding:11px 12px;border:1px solid #efb4c4;border-radius:12px;background:#fffaf7;color:#315c36;font:inherit;cursor:pointer}
.tip-choice:hover,.tip-choice:focus-visible{background:#ffe4ec;outline:2px solid #f28ba8}
.pantry-search{margin-top:16px;padding:14px;border:2px solid #f4b5c7;border-radius:16px;background:linear-gradient(135deg,#fff5f7,#fff8e8)}.pantry-search h3{margin:0 0 5px;color:#a94c6a}.pantry-search p{margin:0 0 10px}.pantry-search-row{display:flex;gap:8px}.pantry-search-row input{flex:1;min-width:0;border:1px solid #e8a9bb;border-radius:10px;padding:11px;background:#fff;color:#315c36;font:inherit}.pantry-search-row button{border:0;border-radius:10px;padding:10px 13px;background:#315c36;color:#fff;font-weight:750;cursor:pointer}.pantry-result{margin-top:12px;padding:12px;background:#fff;border:1px solid #efd7c8;border-radius:12px;line-height:1.55;white-space:pre-line}.pantry-smart-results{margin-top:12px;display:grid;gap:10px}.pantry-smart-card{background:#fffdf8;border:1px solid #d7e2d1;border-radius:13px;padding:12px;white-space:pre-line;line-height:1.5}.pantry-smart-card h4{margin:0 0 7px;color:#315c36}.pantry-smart-card p{margin:0}.pantry-smart-card.pink{border-color:#efb4c4;background:#fff7f9}.pantry-smart-card.gold{border-color:#e8d3a6;background:#fffaf0}.pantry-smart-card.blue{border-color:#c7d4e8;background:#f7f9ff}#pantrySmartResults[hidden]{display:none!important}#pantrySearchResult[hidden],#pantryPassport[hidden],#substitutionLab[hidden],#storageGuide[hidden],#flavorGuide[hidden],#pantrySearch[hidden]{display:none!important}.pantry-examples{display:flex;gap:6px;flex-wrap:wrap;margin-top:9px}.pantry-examples button{border:1px solid #efb4c4;border-radius:999px;background:#fffaf7;color:#315c36;padding:6px 10px;cursor:pointer}@media(max-width:600px){.pantry-search-row{flex-direction:column}.pantry-search-row button{width:100%}}
.pantry-passport{margin-top:16px;padding:14px;border:2px solid #b9cbb2;border-radius:16px;background:linear-gradient(135deg,#f1f7ed,#fff8ed)}.pantry-passport h3{margin:0 0 5px;color:#315c36}.pantry-passport>p{margin:0 0 12px}.passport-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:9px}.passport-card{background:#fffdf8;border:1px solid #d7e2d1;border-radius:12px;padding:11px}.passport-card h4{margin:0 0 5px;color:#315c36}.passport-card p{font-size:.95em;margin:0 0 8px;line-height:1.45}.passport-ingredients{display:flex;gap:6px;flex-wrap:wrap}.passport-ingredients button{border:1px solid #e6b5c4;border-radius:999px;background:#fff5f7;color:#315c36;padding:5px 8px;font:inherit;cursor:pointer}.passport-note{margin-top:10px;font-size:.92em;color:#5b6958}@media(max-width:600px){.passport-grid{grid-template-columns:1fr}}
.archivist-search{margin:12px 0;padding:12px;border:2px solid #d7c9e8;border-radius:14px;background:linear-gradient(135deg,#f7f2ff,#fff8e8)}.archivist-search label{display:block;font-weight:800;margin-bottom:7px;color:#655080}.archivist-search form{display:flex;gap:8px}.archivist-search input{flex:1;min-width:0;border:1px solid #cbbadd;border-radius:10px;padding:11px;background:#fff;color:#315c36;font:inherit}.archivist-search button{border:0;border-radius:10px;padding:10px 13px;background:#655080;color:#fff;font-weight:750;cursor:pointer}.archivist-search p{font-size:.92em;margin:7px 0 0;color:#6e627d}@media(max-width:600px){.archivist-search form{flex-direction:column}.archivist-search button{width:100%}}
.tip-box{white-space:pre-line;background:#fff8e8;border:1px solid #efd7c8;padding:13px;border-radius:12px;margin-top:14px;line-height:1.55;color:#315c36}
.close{float:right;border:0;background:var(--pink);color:white;font-weight:800;border-radius:999px;padding:7px 12px;cursor:pointer}
.note{margin-top:12px;font-size:13px;opacity:.75}
.pantry{left:13%;top:22%;width:20%;height:12%}.fridge{left:1%;top:45%;width:18%;height:13%}.herb{left:34%;top:22%;width:23%;height:16%}.dinner{left:53%;top:25%;width:23%;height:13%}.baking{right:10%;top:25%;width:20%;height:13%}.cafe{right:0%;top:43%;width:18%;height:16%}.prep{left:39%;top:53%;width:21%;height:15%}.secret{right:1%;top:62%;width:20%;height:15%}.trash{right:0%;bottom:1%;width:21%;height:15%}.hq{left:4%;bottom:1%;width:25%;height:25%}
@media(max-width:600px){.wrap{padding:10px 7px 24px}.map{border-radius:14px}.panel{padding:14px;border-radius:15px}.note{font-size:12px}}
#herbGardenFrame{margin-top:10px}#herbGardenIframe{display:block;width:100%;height:1100px;border:0;border-radius:14px;background:#fff8ed}@media(max-width:600px){#herbGardenIframe{height:1450px}}

.substitution-lab{margin-top:16px;padding:14px;border:2px solid #e7b8c8;border-radius:16px;background:linear-gradient(135deg,#fff0f5,#fff8e8)}.substitution-lab h3{margin:0 0 5px;color:#a94c6a}.substitution-lab>p{margin:0 0 10px}.swap-form{display:flex;gap:8px}.swap-form input{flex:1;min-width:0;border:1px solid #e8a9bb;border-radius:10px;padding:11px;background:#fff;color:#315c36;font:inherit}.swap-form button{border:0;border-radius:10px;padding:10px 13px;background:#315c36;color:#fff;font-weight:750;cursor:pointer}.swap-examples{display:flex;gap:6px;flex-wrap:wrap;margin-top:9px}.swap-examples button{border:1px solid #efb4c4;border-radius:999px;background:#fffaf7;color:#315c36;padding:6px 10px;cursor:pointer}.swap-result{margin-top:12px;padding:12px;background:#fff;border:1px solid #efd7c8;border-radius:12px;line-height:1.55;white-space:pre-line}.swap-result[hidden]{display:none}@media(max-width:600px){.swap-form{flex-direction:column}.swap-form button{width:100%}}


.storage-guide{margin-top:16px;padding:14px;border:2px solid #c8d8c0;border-radius:16px;background:linear-gradient(135deg,#f1f7ed,#fff8e8)}
.storage-guide h3{margin:0 0 5px;color:#315c36}.storage-guide>p{margin:0 0 10px}
.storage-form{display:flex;gap:8px}.storage-form input{flex:1;min-width:0;border:1px solid #b9cbb2;border-radius:10px;padding:11px;background:#fff;color:#315c36;font:inherit}
.storage-form button{border:0;border-radius:10px;padding:10px 13px;background:#315c36;color:#fff;font-weight:750;cursor:pointer}
.storage-examples{display:flex;gap:6px;flex-wrap:wrap;margin-top:9px}.storage-examples button{border:1px solid #b9cbb2;border-radius:999px;background:#fffdf8;color:#315c36;padding:6px 10px;cursor:pointer}
.storage-result{margin-top:12px;padding:12px;background:#fff;border:1px solid #d7e2d1;border-radius:12px;line-height:1.55;white-space:pre-line}
@media(max-width:600px){.storage-form{flex-direction:column}.storage-form button{width:100%}}

.flavor-guide{margin-top:16px;padding:14px;border:2px solid #efb4c4;border-radius:16px;background:linear-gradient(135deg,#fff2f6,#fff8e8)}
.flavor-guide h3{margin:0 0 5px;color:#a94c6a}.flavor-guide>p{margin:0 0 10px}
.flavor-form{display:flex;gap:8px}.flavor-form input{flex:1;min-width:0;border:1px solid #e8a9bb;border-radius:10px;padding:11px;background:#fff;color:#315c36;font:inherit}
.flavor-form button{border:0;border-radius:10px;padding:10px 13px;background:#315c36;color:#fff;font-weight:750;cursor:pointer}
.flavor-examples{display:flex;gap:6px;flex-wrap:wrap;margin-top:9px}.flavor-examples button{border:1px solid #efb4c4;border-radius:999px;background:#fffaf7;color:#315c36;padding:6px 10px;cursor:pointer}
.flavor-result{margin-top:12px;padding:12px;background:#fff;border:1px solid #efd7c8;border-radius:12px;line-height:1.55;white-space:pre-line}
@media(max-width:600px){.flavor-form{flex-direction:column}.flavor-form button{width:100%}}


.archivist-secret-box{margin:12px 0;padding:14px;border:1px solid #d9cba9;border-radius:14px;background:linear-gradient(135deg,#fff9e9,#fffdf8);color:#514733}
.archivist-secret-box p{margin:0 0 10px}.archivist-secret-box button{border:0;border-radius:10px;padding:10px 14px;background:#596f58;color:#fff;font-weight:700}.archivist-secret-box button:focus-visible{outline:3px solid #d58ca4;outline-offset:2px}#bakingSecretResult{margin-top:10px;white-space:pre-line;line-height:1.5}
.baking-rescue-box{margin:12px 0;padding:14px;border:1px solid #cbdcc6;border-radius:14px;background:linear-gradient(135deg,#f2f8ef,#fffdf8);color:#405642}.baking-rescue-box p{margin:0 0 10px}.baking-rescue-box label{display:block;font-weight:800;margin:8px 0 6px}.baking-rescue-box select{width:100%;padding:11px;border:1px solid #c5d5c0;border-radius:10px;background:white;color:#344239;font:inherit}.baking-rescue-box button{margin-top:9px;border:0;border-radius:10px;padding:10px 14px;background:#55745b;color:white;font-weight:750}.baking-rescue-box button:focus-visible{outline:3px solid #d58ca4;outline-offset:2px}#bakingRescueResult{margin-top:10px;white-space:pre-line;line-height:1.55}

/* Chef Saffron's Dinner Station: warm saffron-orange and cream accents */
.dinner-finder{margin:12px 0 16px;padding:14px;border:2px solid #efc18d;border-radius:16px;background:linear-gradient(135deg,#fff4e5,#fffdf8);color:#593b2b}
.dinner-finder h3{margin:0 0 6px;color:#b65f24}.dinner-finder p{margin:4px 0 10px}
.dinner-search-row{display:flex;gap:8px;flex-wrap:wrap}.dinner-search-row input{flex:1;min-width:180px;border:1px solid #e4b47d;border-radius:10px;padding:11px;background:#fff;color:#593b2b}.dinner-search-row button{border:0;border-radius:10px;padding:10px 14px;background:#c96d2b;color:#fff;font-weight:700}
.dinner-chips{display:flex;gap:7px;flex-wrap:wrap;margin:10px 0}.dinner-chips button{border:1px solid #efcfaa;border-radius:999px;padding:6px 10px;background:#fff0dc;color:#78441f}
.dinner-results{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px;margin-top:10px}.dinner-card{border:1px solid #f0d4b4;border-radius:12px;padding:12px;background:#fff}.dinner-card h4{margin:0 0 5px;color:#a65320}.dinner-card p{margin:5px 0}.dinner-card details{margin-top:8px}.dinner-card summary{cursor:pointer;font-weight:700;color:#b65f24}.dinner-empty{padding:12px;border:1px dashed #e4b47d;border-radius:10px;grid-column:1/-1}
body.dinner-room #roomTitle{color:#b65f24}body.dinner-room .tip-choice{border-color:#efc18d}body.dinner-room .tip-choice:hover,body.dinner-room .tip-choice[aria-pressed="true"]{background:#fff0dc;border-color:#d7823e}
@media(max-width:620px){.dinner-results{grid-template-columns:1fr}.dinner-search-row{flex-direction:column}.dinner-search-row button{width:100%}}



.cafe-search{margin:12px 0 16px;padding:14px;border:2px solid #e2c18c;border-radius:16px;background:linear-gradient(135deg,#fff7e7,#fffdf8);color:#5c4736}.cafe-search h3{margin:0 0 6px;color:#9b633d}.cafe-search p{margin:6px 0 10px}.cafe-search form{display:flex;gap:8px}.cafe-search input{flex:1;min-width:0;padding:11px;border:1px solid #d8b16b;border-radius:10px;background:#fff;font:inherit}.cafe-search form button,.cafe-search-result{border:0;border-radius:10px;padding:10px 13px;background:#9b633d;color:#fff;font-weight:750;cursor:pointer}.cafe-search-result{display:block;margin:8px 0;background:#f3e2c5;color:#6b482e;border:1px solid #d8b16b}.cafe-search[hidden]{display:none!important}@media(max-width:600px){.cafe-search form{flex-direction:column}.cafe-search form button{width:100%}}

/* Ham's café accent: warm cocoa and honey, without changing other rooms. */
body.ham-cafe #roomTitle{color:#9b633d}
body.ham-cafe .tip-choice{border-color:#d8b16b}
body.ham-cafe .tip-choice:hover,body.ham-cafe .tip-choice[aria-pressed="true"]{background:#fff0cf;border-color:#b77a36}
.cafe-search-result-card{background:#fffaf4;border:1px solid #e6d8c7;border-radius:14px;padding:12px;margin:10px 0}.cafe-search-result-card h4{margin:0 0 5px;color:#49634e}.cafe-search-result-card p{margin:7px 0;line-height:1.5}.cafe-search h4{margin:14px 0 6px}
/* Rook’s reuse workshop: turquoise and warm cream. */
body.rook-trash #roomTitle{color:#168f98}
body.rook-trash .panel{border-color:#9ddbd8;background:#f7fcfa}
body.rook-trash .tip-choice{border-color:#8ed0d0;background:#fffdf6;color:#176e73}
body.rook-trash .tip-choice:hover,body.rook-trash .tip-choice[aria-pressed="true"]{background:#e1f7f5;border-color:#168f98}

.rook-reuse-search{margin:16px 0;padding:15px;border:2px solid #72c7c9;border-radius:17px;background:linear-gradient(135deg,#e7f8f7,#fff8e8);color:#176e73}.rook-reuse-search h3{margin:0 0 6px;color:#315c36}.rook-reuse-search>p{line-height:1.5}.rook-search-row{display:flex;gap:8px}.rook-search-row input{flex:1;min-width:0;border:1px solid #a6c4a5;border-radius:10px;padding:12px;font:inherit;background:#fff;color:#176e73}.rook-search-row button,.rook-secret-card button{border:0;border-radius:10px;padding:11px 14px;background:#168f98;color:white;font-weight:800;cursor:pointer}.rook-search-examples{display:flex;flex-wrap:wrap;gap:7px;margin-top:10px}.rook-search-examples button{border:1px solid #72c7c9;border-radius:999px;background:#fffdf8;color:#176e73;padding:7px 10px;font:inherit;cursor:pointer}.rook-reuse-results{display:grid;gap:10px;margin-top:12px}.rook-result-card{background:#fffdf8;border:1px solid #a9dedd;border-radius:13px;padding:13px;text-align:left;line-height:1.55;white-space:pre-line}.rook-result-card h4{margin:0 0 6px;color:#176e73}.rook-result-card p{margin:0 0 7px}.rook-result-card .rook-tag{display:inline-block;border-radius:999px;background:#ddf4f2;padding:3px 8px;font-size:.86em;font-weight:800;margin-bottom:7px}.rook-secret-card{margin-top:15px;padding:13px;border:1px dashed #72c7c9;border-radius:13px;background:#fffdf8}.rook-secret-card p{margin:0 0 9px}.rook-secret-card #rookSecretResult{margin-top:10px;white-space:pre-line;line-height:1.55}.rook-safety-note{font-size:.93em;background:#fff5e4;border-left:4px solid #168f98;padding:10px;border-radius:8px}.rook-reuse-search[hidden]{display:none!important}@media(max-width:600px){.rook-search-row{flex-direction:column}.rook-search-row button{width:100%}}


/* Chef Saffron’s Prep Counter: warm orange and cream, scoped to this room only. */
body.prep-room #roomTitle{color:#c56b2d}
body.prep-room .panel{border-color:#efc49b;background:#fffaf3}
body.prep-room .tip-choice{border-color:#edbd8a;background:#fffdf8;color:#75451f}
body.prep-room .tip-choice:hover,body.prep-room .tip-choice[aria-pressed="true"]{background:#fff0dc;border-color:#d9823b}
.prep-station{margin:14px 0;padding:15px;border:2px solid #e8b27b;border-radius:17px;background:linear-gradient(135deg,#fff0dc,#fffdf8);color:#75451f}
.prep-station h3{margin:0 0 6px;color:#b75f27}.prep-station p{line-height:1.5}
.prep-station form{display:flex;gap:8px}.prep-station input{flex:1;min-width:0;padding:11px;border:1px solid #e5b27b;border-radius:10px;background:white;font:inherit}
.prep-station form button,.prep-station .prep-secret-button{border:0;border-radius:10px;padding:10px 13px;background:#c56b2d;color:white;font-weight:800;cursor:pointer}
.prep-examples{display:flex;flex-wrap:wrap;gap:7px;margin-top:10px}.prep-examples button{border:1px solid #e5b27b;border-radius:999px;padding:7px 10px;background:#fffdf8;color:#75451f;font:inherit;cursor:pointer}
.prep-results{margin-top:12px}.prep-result-card{padding:12px;margin:8px 0;border:1px solid #edc99f;border-radius:12px;background:#fffdf8;line-height:1.55}.prep-result-card h4{margin:0 0 6px;color:#a55322}.prep-secret{margin-top:14px;padding:12px;border:1px dashed #d9823b;border-radius:13px;background:#fffaf2}.prep-secret p{margin:7px 0}.prep-secret-result{white-space:pre-line;line-height:1.55}.prep-station[hidden]{display:none!important}@media(max-width:600px){.prep-station form{flex-direction:column}.prep-station form button{width:100%}}


/* v47: purposeful investigation case, scoped to the Secret Room */
.secret-case{margin:12px 0;padding:14px;border:1px solid #b99766;border-radius:15px;background:#f7eddc;color:#4e3826}
.secret-case h3{margin:0 0 7px;color:#76502e}.secret-case p{line-height:1.5}
.secret-case .case-evidence{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:7px;margin:10px 0}
.secret-case .case-evidence button{border:1px solid #c9ad7c;border-radius:10px;background:#fffaf0;color:#553b26;padding:10px 7px;font:inherit;text-align:left}
.secret-case .case-evidence button.found{background:#e4ecd9;border-color:#7c9a68}
.secret-case .case-result{margin-top:9px;padding:10px;border-radius:10px;background:#fffdf7;line-height:1.5;min-height:42px}
@media(max-width:560px){.secret-case .case-evidence{grid-template-columns:1fr}}

</style>

<style>
.rook-hidden-clue{display:flex;align-items:center;gap:7px;flex-wrap:wrap;margin:4px 0 8px;font-size:.78rem;color:#168f98;}
.rook-hidden-clue button{border:1px dashed #35b9b4;background:#e1f8f5;color:#087e83;border-radius:999px;padding:3px 8px;cursor:pointer;font-size:.9rem;}
#rookClueHint{opacity:.72;font-style:italic;}
#rookClueReveal{flex-basis:100%;margin:4px 0;padding:12px;border:1px dashed #35b9b4;border-radius:12px;background:#e9faf7;color:#245b5c;line-height:1.5;}

/* Secret Room: Forbidden Recipe Archive */
.secret-archive{margin-top:14px;padding:14px;border:1px solid #b99766;border-radius:18px;background:radial-gradient(circle at top right,#f4e5c6 0,#fff8e9 45%,#f2e4cd 100%);color:#4e3826;box-shadow:inset 0 0 0 4px #fffaf0;}
.secret-hero{padding:16px;border-radius:14px;background:linear-gradient(135deg,#3c2b25,#57402e);color:#fff0d0;border:1px solid #b28b56;margin-bottom:12px;}
.secret-hero h3{margin:0 0 6px;color:#ffe8b5;font-size:1.3rem}.secret-hero p{margin:0;line-height:1.5}
.secret-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:9px;margin:12px 0}
.secret-tile{border:1px solid #c9ad7c;border-radius:13px;padding:12px;background:#fffaf0;color:#553b26;text-align:left;min-height:84px;}
.secret-tile strong{display:block;font-size:1.03rem;margin-bottom:4px}.secret-tile span{display:block;font-size:.91rem;line-height:1.35}
.secret-card{border:1px dashed #b58a54;background:#fffdf7;border-radius:13px;padding:13px;margin-top:10px;line-height:1.5;}
.secret-card h4{margin:0 0 6px;color:#76502e}.secret-card p{margin:6px 0}
.secret-archive input{width:100%;padding:11px;border:1px solid #c9ad7c;border-radius:10px;background:#fff;color:#4e3826;margin:6px 0}
.secret-archive button.secret-action{border:0;border-radius:10px;padding:10px 13px;background:#81552e;color:#fff8e9;font-weight:700;margin:4px 4px 4px 0;}
.secret-archive button:disabled{opacity:.6}.secret-status{font-size:.92rem;color:#6d573e;margin-top:8px}
.secret-quote{font-style:italic;border-left:3px solid #ad8451;padding:8px 12px;margin:10px 0;background:#f8eedb;border-radius:0 9px 9px 0}
@media(max-width:560px){.secret-grid{grid-template-columns:1fr}.secret-archive{padding:10px}}

#archivePuzzleDrawers .secret-card{border-style:solid;border-color:#d6bd91;background:#fffaf0}
#archivePuzzleDrawers label{display:block;font-weight:700;margin-top:8px;color:#76502e}
#archivePuzzleDrawers input{width:100%;padding:11px;border:1px solid #c9ad7c;border-radius:10px;background:#fff;color:#4e3826;margin:6px 0;font:inherit}
#archivePuzzleDrawers .drawer-open{border-color:#7c9a68;background:#eef4e7}
</style>

</head>
<body>
<div class="wrap">
<h1 class="title">🗺️ Explore Lil Dino's Kitchen</h1>
<p class="sub">Where should we explore today?<br>Pick a destination and start your adventure! ✨<br><strong>TEST v50 · Persistent Archive + Locked Drawer Puzzles</strong></p>
<div class="map" aria-label="Interactive map of Lil Dino's kitchen">
<img src="https://meloveanime1-netizen.github.io/lil-dino-kitchen-map-new/kitchen-map.png" alt="Little Dino's Kitchen Adventures map with Lil Dino on a pink step stool and his hamster-dragon pet beside him">
<button class="hotspot pantry" aria-label="Open Pantry" data-room="pantry"></button>
<button class="hotspot fridge" aria-label="Open Fridge" data-room="fridge"></button>
<button class="hotspot herb" aria-label="Open Herb Garden" data-room="herb"></button>
<button class="hotspot dinner" aria-label="Open Dinner Station" data-room="dinner"></button>
<button class="hotspot baking" aria-label="Open Baking Corner" data-room="baking"></button>
<button class="hotspot cafe" aria-label="Open Cozy Cafe" data-room="cafe"></button>
<button class="hotspot prep" aria-label="Open Prep Counter" data-room="prep"></button>
<button class="hotspot secret" aria-label="Open Secret Recipe Room" data-room="secret"></button>
<button class="hotspot trash" aria-label="Open Kitchen Trash" data-room="trash"></button>
<button class="hotspot hq" aria-label="Open Lil Dino's Kitchen HQ" data-room="hq"></button>
</div>
<section class="panel" id="panel" aria-live="polite">
<button class="close" id="close" type="button">Close</button>
<h2 id="roomTitle"></h2><p id="roomDesc"></p>
<div id="rookHiddenClue" class="rook-hidden-clue" hidden><button id="rookClueButton" type="button" aria-label="Inspect the tiny turquoise screw">🩵 ·</button><span id="rookClueHint">A tiny turquoise screw is tucked beside the workshop sign…</span><p id="rookClueReveal" aria-live="polite" hidden></p></div>
<div id="rookReuseSearch" class="rook-reuse-search" hidden>
 <h3>🔎 Rook’s Second-Life Search</h3>
 <p>Search an item, scrap, or kitchen question. I’ll help you decide whether to regrow it, reuse it, compost it, recycle it, or discard it safely.</p>
 <form id="rookReuseForm" class="rook-search-row"><input id="rookReuseInput" type="search" aria-label="Search reuse and regrow advice" placeholder="Try onions, ginger, bok choy, lemongrass, rice, lemon peel…" autocomplete="off"><button type="submit">Investigate</button></form>
 <div class="rook-search-examples"><button type="button" data-rook-query="green onions">Green onions</button><button type="button" data-rook-query="celery">Celery</button><button type="button" data-rook-query="lemon peel">Lemon peel</button><button type="button" data-rook-query="eggshells">Eggshells</button><button type="button" data-rook-query="coffee grounds">Coffee grounds</button><button type="button" data-rook-query="moldy bread">Moldy bread</button><button type="button" data-rook-query="glass jar">Glass jar</button><button type="button" data-rook-query="broccoli stems">Broccoli stems</button><button type="button" data-rook-query="onion peels">Onion peels</button><button type="button" data-rook-query="ginger scraps">Ginger scraps</button><button type="button" data-rook-query="bok choy">Bok choy</button><button type="button" data-rook-query="lemongrass">Lemongrass</button><button type="button" data-rook-query="rice">Cooked rice</button></div>
 <div id="rookReuseResults" class="rook-reuse-results" aria-live="polite"><p>“Every object leaves clues. Give me an item to investigate.” — Rook</p></div>
 <div class="rook-secret-card"><h3>🗝️ Rook’s Locked Field Notes</h3><p>Useful discoveries from the workshop’s back shelves.</p><button id="rookRevealSecret" type="button">Reveal a Secret</button><div id="rookSecretResult" aria-live="polite"></div></div>
 <p class="rook-safety-note"><strong>Rook’s rule:</strong> Never taste food to check whether it is safe. Food safety comes before waste reduction, and compost/recycling acceptance varies by local program.</p>
</div>
<div id="prepStation" class="prep-station" hidden>
<h3>🧡 Chef Saffron’s Prep Desk</h3>
<p>Search a skill, ingredient, or cooking question. Get practical prep steps before you start cooking.</p>
<form id="prepSearchForm"><input id="prepSearchInput" type="search" aria-label="Search prep skills" placeholder="Try dice an onion, mince garlic, julienne carrots, measurements…" autocomplete="off"><button type="submit">Find Prep Help</button></form>
<div class="prep-examples"><button type="button" data-prep-query="onion">Onions</button><button type="button" data-prep-query="ginger">Ginger</button><button type="button" data-prep-query="bok choy">Bok choy</button><button type="button" data-prep-query="lemongrass">Lemongrass</button><button type="button" data-prep-query="measurements">Measurements</button><button type="button" data-prep-query="garlic equivalents">Garlic equivalents</button><button type="button" data-prep-query="produce yields">Produce yields</button><button type="button" data-prep-query="knife safety">Knife safety</button><button type="button" data-prep-query="rice">Rice</button><button type="button" data-prep-query="tofu">Tofu</button><button type="button" data-prep-query="carrots">Carrots</button><button type="button" data-prep-query="broccoli">Broccoli</button><button type="button" data-prep-query="bell peppers">Bell peppers</button><button type="button" data-prep-query="chicken">Chicken</button><button type="button" data-prep-query="beef">Beef</button><button type="button" data-prep-query="fish">Fish</button><button type="button" data-prep-query="shrimp">Shrimp</button><button type="button" data-prep-query="eggs">Eggs</button><button type="button" data-prep-query="Asian aromatics">Asian aromatics</button><button type="button" data-prep-query="dice an onion">Dice an onion</button><button type="button" data-prep-query="mince garlic">Mince garlic</button><button type="button" data-prep-query="julienne carrots">Julienne carrots</button><button type="button" data-prep-query="broccoli florets">Broccoli florets</button><button type="button" data-prep-query="shred cabbage">Shred cabbage</button><button type="button" data-prep-query="slice mushrooms">Slice mushrooms</button><button type="button" data-prep-query="cut avocado">Cut avocado</button><button type="button" data-prep-query="chop herbs">Chop herbs</button></div>
<div id="prepSearchResults" class="prep-results" aria-live="polite"><p>“Good prep makes the cooking part easier. Let’s get everything ready first.” — Chef Saffron</p></div>
<div class="prep-secret"><strong>🌶️ A tiny detail on the cutting board…</strong><p>Somewhere in the station, a little orange pepper is hiding.</p><button class="prep-secret-button" id="prepPepperButton" type="button">Inspect the tiny pepper</button><div id="prepSecretResult" class="prep-secret-result" aria-live="polite"></div></div>
<div class="prep-secret prep-archive-secret"><strong>📜 Something is tucked beneath the old cutting board…</strong><p>It looks like a scrap from a recipe that was never meant to be found. Inspect it carefully.</p><button class="prep-secret-button" id="prepArchiveButton" type="button">Inspect the faded recipe scrap</button><div id="prepArchiveResult" class="prep-secret-result" aria-live="polite"></div></div>
</div>
<ul id="roomList"></ul>
<div id="secretArchive" class="secret-archive" hidden>
 <div class="secret-hero"><h3>🕯️ The Forbidden Recipe Archive</h3><p>Some recipes aren’t just about food… They’re about people, places, and the stories someone tried to erase.</p></div>
 <div class="secret-quote">The Archivist: “Every recipe has a voice. You just have to listen.”</div>
 <div class="secret-grid" aria-label="Secret room discoveries">
  <button type="button" class="secret-tile" id="secretSearchTile"><strong>🔎 Search the Archive</strong><span>Look up clues, recipes, characters, and strange references.</span></button>
  <button type="button" class="secret-tile" id="secretDrawerTile"><strong>🗝️ Locked Drawers</strong><span>Inspect the cabinet. Some secrets need a clue first.</span></button>
  <button type="button" class="secret-tile" id="secretFragmentTile"><strong>📜 Recipe Fragments</strong><span>Examine a recipe whose title has been torn away.</span></button>
  <button type="button" class="secret-tile" id="secretMessageTile"><strong>✉️ The Archivist’s Messages</strong><span>Read a hidden note left between the pages.</span></button>
 </div>
 <section class="secret-card" id="secretSearchPanel" hidden><h4>🔎 Search the Archive</h4><p>Try “missing page,” “forbidden recipe,” “guilds,” “third bell,” or a character’s name.</p><form id="secretSearchForm"><input id="secretSearchInput" type="search" placeholder="Search the archive…" aria-label="Search the Forbidden Recipe Archive"><button class="secret-action" type="submit">Search records</button></form><div id="secretSearchResult" aria-live="polite" class="secret-status"></div><button class="secret-action" id="secretNextHint" type="button" hidden>Reveal another hint</button></section>
 <section class="secret-card" id="secretDrawerPanel" hidden><h4>🗝️ The Cabinet of Unlisted Records</h4><p>One drawer has a small symbol: three stars beside a bell. The lock seems to be waiting for a clue.</p><button class="secret-action" id="secretUnlockDrawer" type="button">Inspect the three-star lock</button><div id="secretDrawerResult" aria-live="polite" class="secret-status"></div></section>
 <section class="secret-card" id="secretFragmentPanel" hidden><h4>📜 The Recipe With No Name</h4><p>The title has been torn from this page, but three symbols remain in the margin: a sprig, a bell, and a little open eye.</p><button class="secret-action" id="secretCollectFragment" type="button">Collect recipe fragment</button><div id="secretFragmentResult" aria-live="polite" class="secret-status"></div></section>
 <section class="secret-card" id="secretMessagePanel" hidden><h4>✉️ A note in the Archivist’s hand</h4><p>“Someone went to considerable trouble to remove the name, yet left the recipe intact. Either they were careless… or they wanted someone to find it.”</p><button class="secret-action" id="secretRevealMessage" type="button">Turn over the note</button><div id="secretMessageResult" aria-live="polite" class="secret-status"></div></section>
 <section class="secret-card"><h4>👁️ A detail that doesn’t belong</h4><p>A tiny purple star is etched into the leg of the central desk. Tap to inspect it.</p><button class="secret-action" id="secretEasterEgg" type="button">Inspect the purple star</button><div id="secretEasterResult" aria-live="polite" class="secret-status"></div></section>

 <section class="secret-case" aria-labelledby="secretCaseTitle">
  <h3 id="secretCaseTitle">🕵️ Active Investigation: The Recipe With No Name</h3>
  <p>The Archivist has opened one case for you. Your job is to gather evidence, compare the clues, and decide what the evidence supports. Tap each evidence item to inspect it.</p>
  <div class="case-evidence">
   <button type="button" data-case-evidence="fragment">📜 <strong>Evidence A</strong><br>Recipe fragment</button>
   <button type="button" data-case-evidence="drawer">🗝️ <strong>Evidence B</strong><br>Three-star drawer</button>
   <button type="button" data-case-evidence="letter">✉️ <strong>Evidence C</strong><br>Uncatalogued letter</button>
  </div>
  <div id="caseEvidenceResult" class="case-result" aria-live="polite">Case status: 0 of 3 evidence items examined.</div>
  <div id="caseConclusion" hidden>
   <p><strong>Your conclusion:</strong> What is the strongest explanation for the missing recipe title?</p>
   <button class="secret-action" type="button" data-case-answer="right">Someone deliberately removed the name but left clues behind.</button>
   <button class="secret-action" type="button" data-case-answer="wrong">The page faded naturally and the symbols are decoration.</button>
  </div>
  <div id="caseReward" class="case-result" aria-live="polite" hidden></div>
 </section>
 <section class="secret-card" id="caseFilesCabinet" aria-labelledby="caseFilesTitle">
  <h4 id="caseFilesTitle">🗄️ The Case Files Cabinet</h4>
  <p id="cabinetIntro">A narrow cabinet stands against the wall. Its brass label reads: “Solved cases only.” The first drawer is sealed.</p>
  <div id="cabinetLocked" class="secret-status">🔒 No files available yet. Solve the active investigation to earn your first file.</div>
  <div id="cabinetUnlocked" hidden>
   <button type="button" class="secret-action" id="openCaseFile001">📁 Open Case File 001 — The Erased Name</button>
   <div id="caseFile001Details" class="secret-card" hidden>
    <h4>📜 Case File 001 — The Erased Name</h4>
    <p><strong>Status:</strong> Solved · First Archive discovery</p>
    <p><strong>Finding:</strong> A missing title is not proof that a recipe never existed.</p>
    <p><strong>Evidence summary:</strong> The title was cleanly torn away; the three-star-and-bell symbol links the fragment to a locked drawer; and the letter describes deliberate removal.</p>
    <p class="secret-quote">The Archivist: “Good. Now ask who benefited from its disappearance.”</p>
    <p><strong>Next lead:</strong> Investigate who had a reason to erase the recipe—and what the guilds wanted kept hidden.</p>
   </div>
  </div>
 </section>

 <section class="secret-card" id="archivePuzzleDrawers" aria-labelledby="archivePuzzleTitle">
  <h4 id="archivePuzzleTitle">🔐 The Locked Drawers</h4>
  <p>Two narrow drawers sit beneath the Case Files Cabinet. Each has a different lock. The Archivist has left just enough clues to begin.</p>
  <div class="secret-card" id="puzzleDrawerOne">
   <h4>🔔 Drawer I — The Bell Lock</h4>
   <p><strong>Clue:</strong> An old catalog entry says, “When the ___ is remembered, the drawer may open.” What words belong in the blank?</p>
   <form id="drawerOneForm"><label for="drawerOneAnswer">Enter the phrase</label><input id="drawerOneAnswer" type="text" placeholder="Type the clue phrase…" autocomplete="off"><button class="secret-action" type="submit">Try the lock</button></form>
   <div id="drawerOneResult" class="secret-status" aria-live="polite">🔒 The drawer is locked.</div>
  </div>
  <div class="secret-card" id="puzzleDrawerTwo">
   <h4>👁️ Drawer II — The Margin Symbols</h4>
   <p><strong>Clue:</strong> The torn recipe carries three symbols in order. Enter them as words, separated by spaces.</p>
   <form id="drawerTwoForm"><label for="drawerTwoAnswer">Enter the symbols</label><input id="drawerTwoAnswer" type="text" placeholder="Three symbols…" autocomplete="off"><button class="secret-action" id="drawerTwoSubmit" type="submit">Try the lock</button></form>
   <div id="drawerTwoResult" class="secret-status" aria-live="polite">🔒 This drawer has a second lock. Open Drawer I first.</div>
  </div>
 </section>
 <section class="secret-card" id="discoveryJournal" aria-labelledby="discoveryJournalTitle">
  <h4 id="discoveryJournalTitle">📔 The Discovery Journal</h4>
  <p>The Archivist’s journal keeps a record of artifacts and leads you have actually uncovered. Your entries update from your saved Archive progress.</p>
  <div id="journalArtifactEye" class="secret-card"><h4>👁️ Artifact: The Brass Eye</h4><p id="journalEyeStatus">🔒 Not yet recovered. Open Drawer I to find the token.</p><p><strong>Record:</strong> A brass token stamped with a tiny open eye. Its purpose is still unknown.</p></div>
  <div id="journalLeadIngredient" class="secret-card"><h4>🧩 Lead: The Impossible Ingredient</h4><p id="journalIngredientStatus">🔒 Not yet recovered. Open Drawer II to uncover the hidden Archive slip.</p><p><strong>Record:</strong> “The first erased recipe was not the only one. Follow the ingredient that appears where no ingredient should be.”</p></div>
  <div id="journalNextCase" class="secret-status" aria-live="polite">📌 The next case remains sealed until both drawer discoveries are recorded.</div>
 </section>

 <section class="secret-case" id="case002Investigation" aria-labelledby="case002Title">
  <h3 id="case002Title">🧪 Case File 002 — The Impossible Ingredient</h3>
  <p id="case002Intro">The Discovery Journal has recorded both drawer discoveries. A new investigation can begin: find the ingredient that appears where no ingredient should be. Examine all three pieces of evidence before making your deduction.</p>
  <div id="case002Locked" class="secret-status">🔒 CASE FILE 002 SEALED — Recover the Brass Eye from Drawer I and the Impossible Ingredient lead from Drawer II to open this investigation.</div>
  <div id="case002Work" hidden>
   <div class="case-evidence">
    <button type="button" data-case002-evidence="ledger">📒 <strong>Evidence A</strong><br>The Ingredient Ledger</button>
    <button type="button" data-case002-evidence="margin">📜 <strong>Evidence B</strong><br>The Recipe Margin</button>
    <button type="button" data-case002-evidence="map">🗺️ <strong>Evidence C</strong><br>The Missing Place</button>
   </div>
   <div id="case002EvidenceResult" class="case-result" aria-live="polite">Evidence examined: 0 of 3.</div>
   <div id="case002Conclusion" hidden>
    <p><strong>Your deduction:</strong> Why does “winter sugar” appear in the ledger’s blank space?</p>
    <button class="secret-action" type="button" data-case002-answer="wrong">It is an ordinary ingredient accidentally written in the wrong column.</button>
    <button class="secret-action" type="button" data-case002-answer="right">It marks a recipe connected to a place the Archive has deliberately removed from its records.</button>
    <button class="secret-action" type="button" data-case002-answer="wrong">It is a made-up ingredient with no connection to the missing records.</button>
   </div>
   <div id="case002Reward" class="case-result" aria-live="polite" hidden></div>
  </div>
 </section>
 <section class="secret-card" id="caseFile002Cabinet" aria-labelledby="caseFile002Title">
  <h4 id="caseFile002Title">📁 Case File 002 — The Impossible Ingredient</h4>
  <p id="caseFile002Status">🔒 This file will be added to the cabinet when the investigation is solved.</p>
  <div id="caseFile002Details" hidden>
   <p><strong>Finding:</strong> “Winter sugar” appears beside a blank location field, matching a recipe tied to a place removed from the Archive’s map.</p>
   <p><strong>Novel thread:</strong> The Archive may be erasing places as well as names. The ingredient is a trace left behind by a history someone tried to remove.</p>
   <p class="secret-quote">The Archivist: “An ingredient cannot remember a place. Unless, of course, the place was never truly gone.”</p>
  </div>
 </section>
 <section class="secret-case" id="case003Preview" aria-labelledby="case003Title">
  <h3 id="case003Title">📄 Case File 003 — The Page That Shouldn’t Exist</h3>
  <p id="case003Gate">🔒 This page remains sealed until Case File 002 has been solved.</p>
  <div id="case003Work" hidden>
   <p class="secret-status">📜 RECOVERED DOCUMENT · ARCHIVE ORIGIN UNKNOWN</p>
   <div class="secret-card">
    <h4>Fragment from the Forbidden Recipe Archive</h4>
    <p><em>If this page has reached you, then the Archive has begun remembering.</em></p>
    <p>I once believed recipes were simply instructions: ingredients gathered, measurements followed, something made with care.</p>
    <p>I was wrong.</p>
    <p>Some recipes remember the hands that created them. Some remember places that no longer exist. And a rare few remember people whose names have been erased from every record we possess.</p>
    <p>The first name disappeared seventeen years before the doors were sealed.</p>
    <p>The second was removed from the family register.</p>
    <p>The third—</p>
    <p><em>The writing stops here. The rest of the page has been cut away.</em></p>
    <p class="secret-quote">“Do not let the Archivist discover that you have found this.”</p>
   </div>
   <button class="secret-action" type="button" id="recordCase003Page">📌 Record this page in the Discovery Journal</button>
   <div id="case003Result" class="case-result" aria-live="polite">This fragment points toward the novel’s central mystery, but its author is still unknown.</div>
  </div>
 </section>
 <p class="secret-status" id="archiveSaveStatus">📌 Archive progress will be saved in this browser when storage is available.</p>
</div>
<div id="pantrySearch" class="pantry-search" hidden><h3>🦖 Ask Lil Dino — Smart Pantry Search</h3><p>Search once to see ingredient notes and matching storage, flavor, substitution, and around-the-world tips together.</p><form id="pantrySearchForm" class="pantry-search-row"><input id="pantrySearchInput" aria-label="Search a pantry ingredient" placeholder="Try rice, flour, beans, oats…" autocomplete="off"><button type="submit">Ask Dino</button></form><div class="pantry-examples" aria-label="Popular pantry searches"><button type="button" data-pantry-example="rice">Rice</button><button type="button" data-pantry-example="flour">Flour</button><button type="button" data-pantry-example="beans">Beans</button><button type="button" data-pantry-example="oats">Oats</button><button type="button" data-pantry-example="pasta">Pasta</button><button type="button" data-pantry-example="soy sauce">Soy sauce</button><button type="button" data-pantry-example="miso">Miso</button><button type="button" data-pantry-example="gochujang">Gochujang</button><button type="button" data-pantry-example="coconut milk">Coconut milk</button><button type="button" data-pantry-example="tahini">Tahini</button><button type="button" data-pantry-example="lentils">Lentils</button><button type="button" data-pantry-example="couscous">Couscous</button><button type="button" data-pantry-example="tamarind paste">Tamarind</button></div><div id="pantrySearchResult" class="pantry-result" aria-live="polite" hidden></div><div id="pantrySmartResults" class="pantry-smart-results" aria-live="polite" hidden></div></div>
<div id="pantryPassport" class="pantry-passport" hidden><h3>🌏 Pantry Passport</h3><p>Travel through pantry staples, learn how they are used, and tap an ingredient to ask Lil Dino about it.</p><div class="passport-grid"><article class="passport-card"><h4>🥢 East Asian Pantry</h4><p>Explore ingredients used across distinct East Asian food traditions.</p><div class="passport-ingredients"><button type="button" data-passport-ingredient="soy sauce">Soy sauce</button><button type="button" data-passport-ingredient="miso">Miso</button><button type="button" data-passport-ingredient="gochujang">Gochujang</button><button type="button" data-passport-ingredient="nori">Nori</button><button type="button" data-passport-ingredient="sesame oil">Sesame oil</button></div></article><article class="passport-card"><h4>🧆 Middle Eastern & Mediterranean</h4><p>Discover staples found in many different dishes across these diverse regions.</p><div class="passport-ingredients"><button type="button" data-passport-ingredient="tahini">Tahini</button><button type="button" data-passport-ingredient="couscous">Couscous</button><button type="button" data-passport-ingredient="chickpeas">Chickpeas</button><button type="button" data-passport-ingredient="lentils">Lentils</button></div></article><article class="passport-card"><h4>🌶️ South & Southeast Asian Pantry</h4><p>Explore ingredients used differently across South Asian and Southeast Asian cuisines.</p><div class="passport-ingredients"><button type="button" data-passport-ingredient="coconut milk">Coconut milk</button><button type="button" data-passport-ingredient="tamarind paste">Tamarind</button><button type="button" data-passport-ingredient="fish sauce">Fish sauce</button><button type="button" data-passport-ingredient="curry powder">Curry powder</button></div></article><article class="passport-card"><h4>🌍 More Places to Explore</h4><p>The passport can grow over time with more ingredients and carefully researched regional collections.</p><div class="passport-ingredients"><button type="button" data-passport-ingredient="quinoa">Quinoa</button><button type="button" data-passport-ingredient="black beans">Black beans</button><button type="button" data-passport-ingredient="palm sugar">Palm sugar</button></div></article></div><p class="passport-note">Lil Dino’s note: an ingredient can travel across borders, and a region can hold many different cuisines. We’re learning the details, not flattening them.</p></div>
<div id="substitutionLab" class="substitution-lab" hidden><h3>🔄 Ingredient Substitution Lab</h3><p>Missing something? Tell Lil Dino which ingredient your recipe needs, and get a practical alternative with notes about flavor or texture.</p><form id="swapForm" class="swap-form"><input id="swapInput" aria-label="Ingredient you are missing" placeholder="Try buttermilk, eggs, or butter…" autocomplete="off"><button type="submit">Find a Swap</button></form><div class="swap-examples" aria-label="Try a substitution"><button type="button" data-swap-example="buttermilk">Buttermilk</button><button type="button" data-swap-example="egg">Egg</button><button type="button" data-swap-example="butter">Butter</button><button type="button" data-swap-example="sour cream">Sour cream</button><button type="button" data-swap-example="lemon juice">Lemon juice</button><button type="button" data-swap-example="cornstarch">Cornstarch</button></div><div id="swapResult" class="swap-result" aria-live="polite" hidden></div></div>

<div id="storageGuide" class="storage-guide" hidden>
<h3>🥬 Storage & Freshness Guide</h3>
<p>Ask where an ingredient belongs, how to store it, and what signs to watch for. Package directions still come first!</p>
<form id="storageForm" class="storage-form"><input id="storageInput" aria-label="Ingredient to look up for storage" placeholder="Try potatoes, flour, coconut milk…" autocomplete="off"><button type="submit">Check Storage</button></form>
<div class="storage-examples" aria-label="Popular storage questions">
<button type="button" data-storage-example="potatoes">Potatoes</button><button type="button" data-storage-example="flour">Flour</button><button type="button" data-storage-example="opened coconut milk">Opened coconut milk</button><button type="button" data-storage-example="berries">Berries</button><button type="button" data-storage-example="bread">Bread</button><button type="button" data-storage-example="eggs">Eggs</button><button type="button" data-storage-example="leftovers">Leftovers</button><button type="button" data-storage-example="soy sauce">Soy sauce</button>
</div><div id="storageResult" class="storage-result" aria-live="polite" hidden></div>
</div>

<div id="flavorGuide" class="flavor-guide" hidden>
<h3>🍓 Flavor Pairing Guide</h3>
<p>Wonder what tastes good together? Pick an ingredient or type your own. Lil Dino has opinions. Many, unfortunately.</p>
<form id="flavorForm" class="flavor-form"><input id="flavorInput" aria-label="Ingredient to find flavor pairings for" placeholder="Try strawberries, mushrooms, or chickpeas…" autocomplete="off"><button type="submit">Find Pairings</button></form>
<div class="flavor-examples" aria-label="Popular flavor pairing searches">
<button type="button" data-flavor-example="strawberries">Strawberries</button><button type="button" data-flavor-example="tomatoes">Tomatoes</button><button type="button" data-flavor-example="chicken">Chicken</button><button type="button" data-flavor-example="mushrooms">Mushrooms</button><button type="button" data-flavor-example="chickpeas">Chickpeas</button><button type="button" data-flavor-example="potatoes">Potatoes</button><button type="button" data-flavor-example="shrimp">Shrimp</button><button type="button" data-flavor-example="chocolate">Chocolate</button>
</div><div id="flavorResult" class="flavor-result" aria-live="polite" hidden></div>
</div>

<div id="dinnerFinder" class="dinner-finder" hidden>
<h3>🍲 Dinner Finder</h3><p>Search a dish, ingredient, cuisine, or dinner mood. Try “Thai,” “easy,” “cozy,” or “fresh.” Choose a recipe to open its ingredients and steps.</p>
<form id="dinnerSearchForm" class="dinner-search-row"><input id="dinnerSearchInput" aria-label="Search dinner recipes" placeholder="Try shrimp, chickpeas, pasta, quick dinner…" autocomplete="off"><button type="submit">Find Dinner</button></form>
<div class="dinner-chips" aria-label="Popular cuisine and dinner mood searches"><button type="button" data-dinner-search="quick">⚡ Quick & Easy</button><button type="button" data-dinner-search="cozy comfort">🍲 Cozy Comfort</button><button type="button" data-dinner-search="fresh light">🥗 Fresh & Light</button><button type="button" data-dinner-search="vegetarian">🥬 Vegetarian</button><button type="button" data-dinner-search="pasta italian">🍝 Italian</button><button type="button" data-dinner-search="mexican taco">🌮 Mexican</button><button type="button" data-dinner-search="japanese">🍱 Japanese</button><button type="button" data-dinner-search="thai">🍜 Thai</button><button type="button" data-dinner-search="chicken">🍗 Chicken</button><button type="button" data-dinner-search="around the world">🌎 Around the World</button><button type="button" data-dinner-search="seafood">🦐 Seafood</button><button type="button" data-dinner-search="one pan">🍳 One-Pan</button></div>
<div id="dinnerResults" class="dinner-results" aria-live="polite"></div>
</div>
<div id="tipBox" class="tip-box" hidden></div>
<div id="herbGardenFrame" hidden><iframe id="herbGardenIframe" title="Juniper Vale’s Herb Garden" loading="lazy"></iframe></div>
</section>
<div class="note">Tap a sign in the kitchen to explore. 🦖💗</div>
</div>
<script>
(function(){
'use strict';
const rooms={
pantry:{title:'🫙 Lil Dino’s Pantry — Ingredient Headquarters',desc:'“Welcome to my pantry. Please do not reorganize my snacks without submitting the proper paperwork.” Learn to store staples, organize shelves, and make the most of what you already have.',items:[
['🫙 Store It','Keep dry staples such as rice, flour, pasta, oats, and cereal in clean, dry, airtight containers. Store them in a cool, dry place away from sunlight, heat, and moisture. Follow package directions after opening. Whole-grain flours usually keep longer in the refrigerator or freezer.'],
['🧺 Organize It','Group baking supplies, grains, canned goods, snacks, and seasonings. Keep everyday items easy to reach, label containers with the ingredient name, and add an opened-on date when helpful. “If you cannot find the cinnamon, the cinnamon has won.”'],
['🌾 Learn About It','Flour helps give baked goods structure. Rice, oats, and pasta provide carbohydrates; beans and lentils provide plant protein and fiber; oils add fat and help cook food. “Ingredients have jobs. Unlike that mystery jar in the back.” Check labels for allergens and storage directions.'],
['⏰ Use It First','Place older packages in front and newer ones behind, but only use food that is still in good condition. Check for torn packaging, moisture, insects, mold, or unusual smells. When in doubt about a product’s safety, discard it. “First in, first out. Revolutionary, I know.”']
]},
fridge:{title:'🥛 The Fridge — Food Freshness Guide',desc:'Practical storage guidance to help food stay fresh and safe.',items:[
['🍓 Strawberries & Berries','Refrigerate berries dry and unwashed in a breathable container. Remove damaged or moldy berries, and wash just before eating.'],
['🐉 Dragon Fruit','Keep an uncut ripe dragon fruit in the refrigerator to extend freshness. Once cut, cover it in an airtight container and refrigerate; use within a few days.'],
['🥬 Lettuce & Greens','Refrigerate dry leaves in a container or bag with a paper towel to absorb extra moisture. Replace the towel if it becomes wet.'],
['🍌 Bananas','Keep unripe bananas at room temperature. Refrigerating ripe bananas slows further ripening, though the peel may darken.'],
['🥛 Milk & Dairy','Keep the refrigerator at 40°F (4°C) or colder. Store milk on an interior shelf rather than in the door, where temperatures fluctuate more.'],
['🥩 Meat & Chicken','Keep raw meat sealed on the lowest shelf to prevent drips. Refrigerate promptly or freeze; cook chicken to 165°F (74°C).'],
['🥚 Eggs','Keep eggs in their carton inside the refrigerator, not in the door. Refrigerate cooked eggs promptly.'],
['❄️ Freeze It','Freeze extra berries, chopped fruit, bread, and leftovers in airtight packaging. Label with the date and remove excess air from freezer bags.'],
['⏰ Use Me First','Check cut fruit, leafy greens, ripe berries, and opened foods regularly. Discard food that shows signs of spoilage.'],
['🍎 Apples',"STORE IT: Refrigerate apples to keep them crisp longer; keep away from foods sensitive to ethylene if needed. ORGANIZE IT: Use the crisper drawer or a breathable produce bag. LEARN ABOUT IT: Bruises speed up softening; one damaged apple should be checked and separated. USE ME FIRST: Slice softer apples into oatmeal, muffins, or cooked fruit; discard moldy or rotten fruit."],
['🍇 Grapes',"STORE IT: Refrigerate unwashed and dry in a ventilated container; wash just before eating. ORGANIZE IT: Keep in the produce drawer or on a shelf where the container will not be crushed. LEARN ABOUT IT: Moisture encourages mold. USE ME FIRST: Freeze sound grapes for snacks or add them to fruit salad; discard moldy grapes and check nearby fruit."],
['🫐 Blueberries',"STORE IT: Refrigerate dry and unwashed in a breathable container; remove crushed berries. ORGANIZE IT: Keep in the produce drawer. LEARN ABOUT IT: Washing before storage leaves extra moisture and can shorten quality. USE ME FIRST: Freeze clean, dry berries or add them to pancakes and oatmeal."],
['🍑 Peaches & Plums',"STORE IT: Let firm fruit ripen at room temperature; refrigerate once ripe to slow further softening. ORGANIZE IT: Keep ripe fruit in the crisper, away from crushing. LEARN ABOUT IT: Cold can dull flavor, so allow refrigerated fruit to warm a little before eating. USE ME FIRST: Use soft but sound fruit in compote or baking."],
['🥑 Avocados',"STORE IT: Ripen unripe avocados on the counter; refrigerate once ripe. Cover cut avocado tightly and use promptly; a little lemon can slow browning but does not make it last indefinitely. ORGANIZE IT: Keep unripe fruit outside the fridge and ripe fruit in the crisper. LEARN ABOUT IT: Browning is often oxidation, not by itself proof of spoilage. USE ME FIRST: Mash ripe avocado into toast, dressing, or guacamole; discard moldy or rotten fruit."],
['🥕 Carrots',"STORE IT: Refrigerate in a bag or container; remove leafy tops if attached because they draw moisture. ORGANIZE IT: Place in the crisper, away from ethylene-sensitive produce where practical. LEARN ABOUT IT: Limp carrots may have lost moisture; sliminess or mold means discard. USE ME FIRST: Add flexible but otherwise sound carrots to soup or roast them."],
['🥬 Celery',"STORE IT: Refrigerate wrapped or in a suitable produce container to limit drying; keep it clean and dry. ORGANIZE IT: Store in the crisper or a long produce drawer. LEARN ABOUT IT: Limpness can mean moisture loss; slime or bad odor means discard. USE ME FIRST: Chop crisp or slightly limp celery into soup, stir-fry, or stock."],
['🥦 Broccoli & Cauliflower',"STORE IT: Refrigerate unwashed in a ventilated bag or container. ORGANIZE IT: Keep in the crisper, away from raw meat and drips. LEARN ABOUT IT: Yellowing can indicate aging; mold, slime, or an off smell means discard. USE ME FIRST: Roast florets, add them to stir-fries, or blanch and freeze."],
['🍄 Mushrooms',"STORE IT: Refrigerate in their original breathable packaging or a paper bag; avoid sealed damp storage. ORGANIZE IT: Place on a shelf or in the crisper where they stay dry. LEARN ABOUT IT: Surface moisture encourages deterioration. USE ME FIRST: Cook mushrooms that are still firm and smell normal; discard slimy or strongly unpleasant ones."],
['🥒 Cucumbers',"STORE IT: Refrigerate if preferred for freshness, but avoid freezing temperatures; keep dry. ORGANIZE IT: Use a warmer part of the fridge or produce drawer, away from very cold spots. LEARN ABOUT IT: Very cold storage can cause pitting and watery texture. USE ME FIRST: Use softened but sound cucumbers in salads, quick pickles, or chilled soups."],
['🫑 Bell Peppers',"STORE IT: Refrigerate dry in a produce bag or container. ORGANIZE IT: Place in the crisper. LEARN ABOUT IT: Wrinkles often mean moisture loss; mold or soft wet patches are warning signs. USE ME FIRST: Slice and freeze extra peppers for cooked dishes, or add them to stir-fries."],
['🍅 Tomatoes',"STORE IT: Keep unripe tomatoes at room temperature. Refrigerate ripe tomatoes if you need to slow spoilage; let them warm before eating for better flavor. ORGANIZE IT: Ripen on the counter, then move ripe fruit to the fridge if needed. LEARN ABOUT IT: Chilling can reduce aroma and texture quality. USE ME FIRST: Use ripe tomatoes in sauce, salsa, or soup; discard moldy or leaking ones."],
['🥬 Napa Cabbage',"STORE IT: Refrigerate whole and unwashed in a bag or produce container; keep cut portions wrapped. ORGANIZE IT: Store in the crisper, away from raw meat. LEARN ABOUT IT: Outer leaves protect the inner leaves; remove damaged outer leaves. USE ME FIRST: Use wilting but sound leaves in soup, stir-fry, or dumplings; discard slimy or moldy portions."],
['🥬 Bok Choy',"STORE IT: Refrigerate unwashed in a breathable bag or container; keep it from drying out. ORGANIZE IT: Put it in the crisper. LEARN ABOUT IT: Separate stems and leaves when preparing; stems take longer to cook. USE ME FIRST: Use soon if leaves begin to wilt; stir-fry stems first, then add leaves."],
['🥕 Daikon Radish',"STORE IT: Refrigerate in a bag or container; remove leafy tops if attached. ORGANIZE IT: Place in the crisper. LEARN ABOUT IT: Drying can make it rubbery, while slime or mold indicates spoilage. USE ME FIRST: Use firm but slightly dried daikon in soup, braises, or quick pickles."],
['🌱 Bean Sprouts',"STORE IT: Refrigerate promptly and follow package instructions; use quickly. ORGANIZE IT: Keep sealed and separate from ready-to-eat foods if raw, and prevent leaks. LEARN ABOUT IT: Raw sprouts have a higher foodborne-illness risk; people at higher risk should avoid raw or lightly cooked sprouts. USE ME FIRST: Cook thoroughly in soups or stir-fries; discard slimy, moldy, or foul-smelling sprouts."],
['🍄 Enoki Mushrooms',"STORE IT: Refrigerate in original packaging and follow the use-by directions. ORGANIZE IT: Keep chilled and separate from foods that will be eaten without cooking. LEARN ABOUT IT: Enoki have been linked to foodborne illness outbreaks; cook thoroughly and avoid raw use. USE ME FIRST: Add to hot pot, soup, or stir-fry and cook thoroughly; discard slimy or moldy mushrooms."],
['🫚 Fresh Ginger',"STORE IT: Refrigerate dry in a bag or container; freeze extra ginger for longer storage. ORGANIZE IT: Keep in the crisper or a sealed container on a shelf. LEARN ABOUT IT: Wrinkling suggests drying; mold or soft, wet decay means discard. USE ME FIRST: Grate frozen ginger directly into soups, marinades, and stir-fries."],
['🌿 Lemongrass',"STORE IT: Refrigerate stalks wrapped loosely or in a container; freeze extra trimmed stalks. ORGANIZE IT: Place in the crisper. LEARN ABOUT IT: The tender inner portion is aromatic; tough outer layers are often bruised or removed for cooking. USE ME FIRST: Bruise stalks for soup or curry, or freeze chopped portions."],
['🌿 Thai Basil',"STORE IT: Treat it as a delicate herb; keep loosely wrapped and use promptly. Basil may darken in very cold conditions, so avoid the coldest fridge spots. ORGANIZE IT: Keep in a warmer area or stand stems in water at room temperature for short-term use if suitable. LEARN ABOUT IT: Chilling can blacken basil leaves. USE ME FIRST: Add to curries, noodle dishes, and stir-fries near the end."],
['🍃 Kaffir Lime Leaves',"STORE IT: Refrigerate fresh leaves in a sealed container for short-term storage or freeze for longer keeping. ORGANIZE IT: Store in a small labeled container in the herb area. LEARN ABOUT IT: Leaves are aromatic and often used to infuse soups and curries; remove tough leaves before serving if desired. USE ME FIRST: Freeze extras in small portions for tom yum, curry, or broth."],
['🥬 Curry Leaves',"STORE IT: Refrigerate fresh leaves in a dry container for short-term use, or freeze them in portions. ORGANIZE IT: Keep in the herb drawer or a labeled freezer bag. LEARN ABOUT IT: Their aroma fades with age. USE ME FIRST: Temper in hot oil for dals, curries, and rice dishes, or freeze before they wilt."],
['🧄 Garlic Chives',"STORE IT: Refrigerate dry in a bag or container and use while crisp. ORGANIZE IT: Put in the crisper or herb section. LEARN ABOUT IT: They have a mild garlic-onion flavor and cook quickly. USE ME FIRST: Add to dumplings, eggs, noodles, or stir-fries."],
['🥢 Fresh Rice Noodles',"STORE IT: Follow the package label; refrigerate fresh noodles and use within the stated period. ORGANIZE IT: Keep sealed on an interior shelf, away from raw meat. LEARN ABOUT IT: Fresh noodles are perishable and are not stored like dry pantry noodles. USE ME FIRST: Use opened packages promptly and discard if the package is swollen, slimy, or smells off."],
['🥟 Dumpling Wrappers',"STORE IT: Refrigerate unopened and opened wrappers according to package directions; seal tightly to prevent drying. Freeze if the label permits and you need longer storage. ORGANIZE IT: Keep flat in a sealed package on an interior shelf. LEARN ABOUT IT: Dried edges tear easily. USE ME FIRST: Make dumplings or wontons soon after opening; discard if moldy or off-smelling."],
['🧊 Tofu',"STORE IT: Follow package directions. Refrigerate opened tofu in a clean covered container with fresh water if the package instructions recommend it, changing water daily; use promptly. ORGANIZE IT: Keep sealed on an interior shelf away from raw meat. LEARN ABOUT IT: Silky, firm, and extra-firm tofu differ in texture and water content. USE ME FIRST: Use opened tofu promptly in stir-fries, soups, or scrambles; discard if sour-smelling, slimy, or moldy."],
['🫘 Tempeh',"STORE IT: Refrigerate and follow package directions; freeze if you will not use it by the stated date. ORGANIZE IT: Keep sealed on an interior shelf. LEARN ABOUT IT: Tempeh is fermented soy cake, but it still needs proper refrigeration. USE ME FIRST: Slice and pan-fry, bake, or crumble into stir-fries; discard if it has unexpected discoloration, slime, or an unpleasant odor."],
['🥬 Kimchi',"STORE IT: Refrigerate after opening and follow the product label; use a clean utensil. ORGANIZE IT: Keep tightly closed on an interior shelf to contain odors and prevent leaks. LEARN ABOUT IT: Fermentation makes it tangy; it can continue fermenting slowly in the fridge. USE ME FIRST: Add to fried rice, pancakes, soups, or stews; discard if moldy or otherwise clearly spoiled."],
['🥣 Miso Paste',"STORE IT: Refrigerate after opening if the label directs; keep the container tightly closed and use a clean spoon. ORGANIZE IT: Place in a sealed container on an interior shelf. LEARN ABOUT IT: Miso is fermented and salty, but product directions still matter. USE ME FIRST: Stir into soup, dressing, marinades, or butter; check the label and discard if mold or unusual spoilage appears."],
['🌶️ Gochujang',"STORE IT: Refrigerate after opening according to package directions and keep the lid clean and tight. ORGANIZE IT: Place in a sealed container on an interior shelf. LEARN ABOUT IT: This Korean fermented chili paste is concentrated, sweet, savory, and spicy. USE ME FIRST: Add small amounts to marinades, sauces, or stews; use clean utensils and follow the label."],
['🥢 Soy Sauce',"STORE IT: Follow the bottle label; refrigeration after opening can help preserve flavor, especially for some varieties. ORGANIZE IT: If refrigerated, keep on an interior shelf rather than the door when possible. LEARN ABOUT IT: Regular soy sauce is usually shelf-stable, but some specialty sauces have different directions. USE ME FIRST: Use older opened bottles for marinades or stir-fries if they remain within label guidance and show no spoilage."],
['🥥 Opened Coconut Milk',"STORE IT: Transfer leftovers from a can to a clean covered container, refrigerate promptly, and use within about 3–4 days as a general leftover guideline unless the label says otherwise. ORGANIZE IT: Keep on an interior shelf with the date labeled. LEARN ABOUT IT: Separation can be normal; stir and check smell, appearance, and storage history. USE ME FIRST: Add to curry, soup, oatmeal, or smoothies; discard if moldy, fizzy unexpectedly, or off-smelling."],
['🧈 Paneer',"STORE IT: Refrigerate sealed and follow package directions; once opened, keep covered and use promptly. ORGANIZE IT: Place on an interior shelf away from raw meat. LEARN ABOUT IT: Paneer is a fresh cheese and is more perishable than many aged cheeses. USE ME FIRST: Add to curry, skewers, or stir-fry; discard if slimy, moldy, or unpleasant-smelling."],
['🥛 Yogurt & Labneh',"STORE IT: Refrigerate promptly and keep containers closed; use clean utensils and follow package guidance after opening. ORGANIZE IT: Keep on an interior shelf, not the door. LEARN ABOUT IT: A little liquid separation can be normal; mold or an unusual odor is not. USE ME FIRST: Use opened containers within label guidance in sauces, marinades, dips, or dressings."],
['🌶️ Fresh Chilies',"STORE IT: Refrigerate dry in a produce bag or container; freeze extras whole or chopped. ORGANIZE IT: Place in the crisper, away from raw meat. LEARN ABOUT IT: Wrinkling often means moisture loss; mold or soft wet decay means discard. USE ME FIRST: Chop into salsa, curry, sambal, or stir-fries; wash hands after handling hot varieties."],
['🥭 Green Mango',"STORE IT: Firm unripe mangoes can ripen at room temperature; refrigerate once ripe or cut. Cover cut fruit and refrigerate promptly. ORGANIZE IT: Ripen on the counter, then move ripe or cut fruit to a covered container in the fridge. LEARN ABOUT IT: Color alone does not always show ripeness. USE ME FIRST: Use ripe fruit in chutney, salads, smoothies, or desserts."],
['🌿 Cilantro',"STORE IT: Refrigerate dry in a loose bag or stand stems in a jar with a little water covered loosely; change water and remove damaged leaves. ORGANIZE IT: Keep in the herb drawer or a stable container on an interior shelf. LEARN ABOUT IT: Leaves and stems are both edible and flavorful. USE ME FIRST: Blend into chutney, salsa, soup, or garnish; freeze chopped leaves if they will be cooked later."],
['🌿 Mint',"STORE IT: Refrigerate loosely wrapped or stand stems in a jar with water for short-term storage. ORGANIZE IT: Keep in the herb section, away from crushing. LEARN ABOUT IT: Mint can wilt quickly when dry. USE ME FIRST: Add to chutney, tea, salads, fruit, or yogurt sauces; freeze leaves in ice cubes for drinks."],
['🧀 Feta & Opened Cheese',"STORE IT: Follow package directions; keep cheese tightly wrapped or in its recommended brine. ORGANIZE IT: Place on an interior shelf in a sealed container to prevent odors spreading. LEARN ABOUT IT: Different cheeses have different moisture levels and storage needs. USE ME FIRST: Crumble into salads, eggs, or roasted vegetables; discard soft cheeses with mold unless the product guidance explicitly says otherwise."],
['🍚 Cooked Rice',"STORE IT: Cool and refrigerate promptly in shallow containers; do not leave at room temperature for long. Refrigerate within 2 hours (1 hour above 90°F/32°C) and use within 3–4 days as a general leftover guideline. ORGANIZE IT: Store covered on an interior shelf, above raw meat. LEARN ABOUT IT: Bacillus cereus spores can survive cooking, so time and temperature matter. USE ME FIRST: Reheat until steaming hot throughout (165°F/74°C is a useful leftover target) and only reheat what you need."],
['🍜 Cooked Noodles & Pasta',"STORE IT: Refrigerate in a covered container promptly; use within 3–4 days as a general leftover guideline. ORGANIZE IT: Keep on an interior shelf above raw meat. LEARN ABOUT IT: Plain cooked noodles and sauced pasta may store differently depending on ingredients. USE ME FIRST: Add to soup, stir-fry, or a quick pasta bake; reheat thoroughly and discard if storage time or temperature is uncertain."],
['🥟 Leftover Dumplings',"STORE IT: Refrigerate promptly in a covered shallow container and use within 3–4 days as a general cooked-leftover guideline. ORGANIZE IT: Keep on an interior shelf, clearly dated. LEARN ABOUT IT: Fillings may contain meat, seafood, or vegetables, so treat them as perishable cooked food. USE ME FIRST: Pan-steam, steam, or reheat until hot throughout; do not use if left out too long."],
['🍈 Cut Melon',"STORE IT: Refrigerate cut melon promptly in a covered container; keep the rind clean before cutting. ORGANIZE IT: Store on an interior shelf away from raw meat. LEARN ABOUT IT: Whole melons should be washed under running water before cutting, even if the rind is not eaten. USE ME FIRST: Eat refrigerated cut melon promptly and discard if it has been left out too long or shows spoilage."],
['🍞 Tortillas & Flatbreads',"STORE IT: Follow the package directions; refrigerate after opening if directed, or freeze extra to extend quality. ORGANIZE IT: Keep sealed and dry so they do not absorb odors or moisture. LEARN ABOUT IT: Some tortillas are shelf-stable unopened; fresh flatbreads may need refrigeration. USE ME FIRST: Use opened packs for wraps, quesadillas, or quick chips; discard any moldy pieces and check the rest."],
['🍗 Cooked Chicken',"STORE IT: Refrigerate promptly in shallow, covered containers and use within 3–4 days as a general leftover guideline, or freeze. ORGANIZE IT: Store above raw meat on an interior shelf. LEARN ABOUT IT: Cooked chicken should reach 165°F/74°C when reheated. USE ME FIRST: Add to soup, fried rice, wraps, or salads; never taste it to decide if it is safe."],
['🐟 Fresh Fish',"STORE IT: Keep very cold and follow the seller/package instructions; cook promptly, generally within 1–2 days refrigerated, or freeze. ORGANIZE IT: Keep sealed on the lowest shelf if raw to prevent drips. LEARN ABOUT IT: Smell alone cannot guarantee safety; time and temperature matter. USE ME FIRST: Cook promptly and discard if improperly stored or clearly spoiled."],
['🍤 Shrimp',"STORE IT: Refrigerate promptly and cook within 1–2 days, or freeze; follow package guidance. ORGANIZE IT: Keep sealed on the lowest shelf if raw. LEARN ABOUT IT: Raw seafood is highly perishable; prevent cross-contamination. USE ME FIRST: Cook thoroughly until opaque and firm; discard if left out too long or storage is uncertain."],
['🌱 Fresh Noodles & Tofu Skins',"STORE IT: Check whether the product is refrigerated or shelf-stable; follow the label once opened. ORGANIZE IT: Keep refrigerated versions sealed on an interior shelf, separate from raw meat. LEARN ABOUT IT: Fresh and dried products have very different storage requirements. USE ME FIRST: Use opened fresh products promptly in soup, hot pot, or stir-fries."],
['🥬 Nopales',"STORE IT: Refrigerate fresh cactus pads in a produce bag or container and use while firm. ORGANIZE IT: Keep in the crisper away from raw meat. LEARN ABOUT IT: Spines must be removed before preparation; buy cleaned nopales when possible. USE ME FIRST: Cook in salads, tacos, eggs, or stews; discard if slimy or moldy."],
['🍈 Jackfruit (Cut)',"STORE IT: Refrigerate cut fresh jackfruit in a covered container and use promptly; freeze portions for longer storage. ORGANIZE IT: Keep on an interior shelf in a sealed container because its aroma can spread. LEARN ABOUT IT: Fresh ripe jackfruit and canned young jackfruit are different products with different storage needs. USE ME FIRST: Add ripe fruit to desserts or use young jackfruit in savory dishes; follow label guidance for canned leftovers."],
['🥬 Okra',"STORE IT: Refrigerate dry and unwashed in a breathable bag; avoid trapping moisture. ORGANIZE IT: Keep in the crisper. LEARN ABOUT IT: Okra can become slimy when cut, which is normal during cooking, but slimy raw surfaces or mold can indicate spoilage. USE ME FIRST: Roast, sauté, stew, or freeze while fresh."],
['🍌 Plantains',"STORE IT: Ripen at room temperature; refrigerate only when ripe if you need to slow further changes, though peel color may darken. ORGANIZE IT: Keep unripe plantains outside the fridge and ripe ones in the crisper if needed. LEARN ABOUT IT: Green plantains are starchier; ripe ones are sweeter. USE ME FIRST: Fry, bake, or mash according to ripeness."]
]},
herb:{title:'🌿 The Herb Garden — Herb & Seasoning Guide',desc:'Choose an ingredient to see seasonings that pair well with it.',items:[
['🍗 Chicken','Rosemary, thyme, garlic, paprika, lemon, and black pepper work well with roasted or grilled chicken.'],
['🍝 Pasta','Basil, oregano, parsley, and garlic pair well with pasta. Add fresh basil near the end to preserve its aroma.'],
['🥦 Vegetables','Try thyme with roasted vegetables, dill with carrots or peas, and garlic with mushrooms or greens.'],
['🍲 Soup','Bay leaf, thyme, parsley, and black pepper add depth. Remove whole bay leaves before serving.'],
['🥔 Potatoes','Rosemary, garlic, paprika, chives, and black pepper work well with roasted or mashed potatoes.'],
['🥚 Eggs','Chives, dill, parsley, smoked paprika, and black pepper complement eggs. Add delicate fresh herbs near the end.']
]},
dinner:{title:'🍝 The Dinner Station — Chef Saffron’s Kitchen',desc:'🧡 Chef Saffron is at the station! Pick a dinner mood or search for an ingredient, dish, or cuisine. She believes dinner should be flavorful, flexible, and doable.',items:[
['⚡ Quick & Easy','Try veggie-and-egg fried rice, a quesadilla with beans and cheese, or pasta tossed with garlic, olive oil, and vegetables.'],
['🍲 Cozy & Comforting','Make a hearty soup, baked potato with toppings, or simple pasta bake. Add vegetables and a protein to make it more filling.'],
['🥗 Fresh & Light','Build a grain bowl with greens, chopped vegetables, beans or chicken, and a lemon dressing.'],
['🌶️ Something Flavorful','Season with garlic, cumin, paprika, chili, or curry powder. Add a little at a time and taste as you go.'],
['🍝 Pasta Night','Combine cooked pasta with sautéed vegetables and tomato sauce or olive oil, garlic, and herbs.'],
['🌮 Taco Night','Fill tortillas with beans, cooked meat or vegetables; add salsa, cabbage, cheese, and lime.'],
['🥘 One-Pan Dinner','Roast chopped vegetables and a suitable protein on a sheet pan. Cut pieces evenly and cook each item to a safe temperature.'],
['🎲 Surprise Me!','Tonight’s idea: crispy chicken wraps with lettuce and a simple side salad. Swap in beans or roasted vegetables if you prefer.']
]},
baking:{title:'🍪 The Baking Corner — Baking Lab',desc:'Practical baking help, measurements, swaps, and flavor ideas.',items:[
['🧁 Baking Basics','Preheat the oven first. Gather and measure ingredients before mixing. Use room-temperature eggs or butter only when the recipe calls for them. Cool baked goods on a rack.'],
['🔄 Ingredient Swaps','Buttermilk: add 1 tablespoon lemon juice or vinegar to a measuring cup, then add milk to the 1-cup line. Wait 5–10 minutes. Plain yogurt can often replace sour cream in cakes and quick breads.'],
['🥄 Measurements','1 cup = 16 tablespoons = 48 teaspoons. 1 tablespoon = 3 teaspoons. 1 stick butter = ½ cup = 8 tablespoons = about 113 g. 1 cup all-purpose flour weighs about 120 g; spoon it into the cup and level it.'],
['🔥 Baking Tips','Spoon flour into measuring cups instead of packing it. Measure liquids at eye level. Mix muffins just until combined, use the center oven rack, and set a timer.'],
['🍓 Flavor Combos','Try lemon + blueberry, apple + cinnamon, chocolate + raspberry, banana + walnut, or pumpkin + ginger. Start with small amounts of strong extracts and spices.'],
['❓ What Happens If…?','Too much flour can make baked goods dry. Overmixing muffins can make them tough. Old baking powder can prevent a good rise. Baking soda and baking powder are not interchangeable 1:1.'],
['🎯 Baking Challenges','Choose one recipe, measure carefully, and change only one thing at a time. Compare the result so you learn what works.']
]},
cafe:{title:'☕ Ham’s Cozy Café — Sips, Snacks & Quality Control',desc:'Ham runs this snug little café: practical drinks, comforting treats, and very serious snack quality-control.',items:[
['☕ Coffee & Tea','Ham’s café notes: Brew coffee according to the package, then add milk, oat milk, or a little sweetener to taste. For green tea, use hot—not fiercely boiling—water to keep it gentler. Ham says the mug must be snack-sized.'],
['🍓 Refreshing Drinks','Ham’s strawberry refresher: Mash 3–4 sliced strawberries with 1 teaspoon sugar. Add 1 cup cold water or chilled tea, a squeeze of lemon, and ice. Taste before adding more sugar. “Quality control requires one tiny sip. Possibly two.”'],
['🍰 Café Treats','Easy café treats: layer yogurt, fruit, and granola for a parfait; make cinnamon toast with butter and cinnamon sugar; or serve cookies with fruit. Ham recommends checking every plate for crumbs.'],
['🍯 Syrups & Flavor Ideas','Ham’s flavor board: vanilla + cinnamon, strawberry + lemon, caramel + coffee, honey + ginger tea, or chocolate + peppermint. Add flavor a little at a time. “If it smells like a snack, I’m interested.”'],
['🧊 Ice & Serving Tips','Chill drinks before serving. Large ice cubes melt more slowly, and leftover coffee can be frozen in an ice-cube tray for iced coffee. Refrigerate milk-based drinks promptly. Ham insists the treat plate stays away from the edge of the counter.'],
['🌏 Around-the-World Café Passport','Take a little café trip around the world! Explore Asian café drinks and sweets, plus treats and sips inspired by Latin America, Europe, and beyond. Recipes are home-kitchen-friendly, and regional styles vary—Ham recommends trying one new flavor at a time.'],
['🥤 Smoothies & Blended Drinks','Blend fruit with yogurt, milk, or a non-dairy alternative for a café-style smoothie. Try strawberry-banana, mango, or berry blends. Keep dairy-based smoothies chilled and serve promptly.'],
['✨ Fun Café Creations','Ham’s special menu for playful café drinks: over-the-top frappés, dessert-inspired sips, colorful refreshers, and creative flavor combinations. Tap for a rotating recommendation, then adjust sweetness and toppings to taste.'],
['🥤 Milkshakes & Malt Shop','Ham’s malt-shop menu has classic diner milkshakes and extra-decadent dessert shakes. Blend ice cream with milk until creamy, then add flavorings and toppings. For a malt, add 1–2 tablespoons malted milk powder. Keep dairy drinks chilled until serving.']
]},
prep:{title:'🔪 Chef Saffron’s Prep Counter — Kitchen Skills Lab',desc:'🧡 Chef Saffron runs this practical prep station. Search a technique or ingredient, learn how to get it ready, and make cooking feel calmer before the pan gets hot.',items:[
['🔪 Cutting Skills','Use a stable cutting board and keep fingertips curled back in a claw grip. For an onion, trim the stem end, halve through the root, peel, make lengthwise cuts, then crosswise cuts. Keep the knife tip and fingers controlled; never rush.'],
['🐔 Preparing Meat Safely','Use a separate board for raw meat and seafood. Do not wash raw chicken because splashes can spread germs. Wash hands and clean surfaces after handling it. Cook poultry to 165°F (74°C) in the thickest part, using a food thermometer.'],
['🥄 Measurements & Conversions','1 cup = 16 tablespoons = 48 teaspoons. 1 tablespoon = 3 teaspoons. ½ cup = 8 tablespoons. One cup of all-purpose flour weighs about 120 g, but weights vary by ingredient; a kitchen scale is best for baking.'],
['🧄 Ingredient Equivalents: Garlic, Ginger & More','GARLIC: 1 medium head usually has about 10 cloves; 1 medium clove minced is roughly 1 teaspoon, so 3 cloves are about 1 tablespoon. A whole head can yield around 2–3 tablespoons minced, but head and clove sizes vary. GINGER: 1 tablespoon freshly grated ginger is roughly a 1-inch piece, depending on thickness. LEMON: 1 medium lemon often gives about 2–3 tablespoons juice. ONION: 1 medium onion yields roughly 1 cup chopped. These are estimates, not exact measurements; use the recipe’s amount when precision matters.'],
['🥄 Quick Kitchen Spoon Conversions','3 teaspoons = 1 tablespoon; 4 tablespoons = ¼ cup; 8 tablespoons = ½ cup; 12 tablespoons = ¾ cup; 16 tablespoons = 1 cup. For garlic, 1 teaspoon minced garlic is about 1 medium clove, and 1 tablespoon is about 3 medium cloves. Measuring spoons are more reliable than guessing by eye.'],
['🍋 Produce Yield Cheat Sheet','Approximate yields: 1 medium lemon = 2–3 tablespoons juice; 1 medium onion = about 1 cup chopped; 1 medium carrot = about ½ cup chopped; 1 medium bell pepper = about 1 cup chopped; 1 medium garlic clove = about 1 teaspoon minced. Sizes vary, so treat these as kitchen estimates.'],
['🔄 Ingredient Substitutions','For 1 cup buttermilk, add 1 tablespoon lemon juice or vinegar to a measuring cup, then add milk to the 1-cup line. Rest 5–10 minutes. Plain yogurt can often replace sour cream in some baked goods, though texture may change.'],
['🧅 Produce Prep & Washing','Wash produce under running water before cutting; do not use soap or household cleaners. Dry leafy greens well. Remove damaged parts, use a clean board, and prep the ingredients that take longest first.'],
['🧄 Garlic, Ginger & Shallots','Crush or mince garlic for a stronger, more even flavor; slice ginger thinly across the fibers or grate it. Shallots are often milder than onions. Prep these before heating oil so they do not burn while you search for the next ingredient.'],
['🥬 Leafy Greens & Cabbage','Remove damaged outer leaves, rinse under running water, and dry well. For napa cabbage or bok choy, separate the leaves to rinse away grit. Cut thick stems smaller than the leaves so they cook at a similar pace.'],
['🥢 Around-the-World Prep: Lemongrass','Trim the dry root end and tough top, peel away dry outer layers, then bruise the tender stalk for soups and curries. Large pieces can flavor a dish and be removed before serving; finely minced tender inner parts can be eaten.'],
['🍄 Mushrooms & Tofu','Brush off visible dirt or briefly rinse mushrooms and dry them well. Drain tofu and press gently between clean towels if the recipe needs it to brown. Keep tofu refrigerated and follow package handling instructions.'],
['🍚 Rice & Noodle Mise en Place','Measure sauces and prepare toppings before cooking. Follow the rice or noodle package for rinsing and cooking directions. Refrigerate cooked rice promptly in shallow containers; do not leave it sitting at room temperature.'],
['🔥 Get the Pan Ready','Read the full recipe first. Chop and measure ingredients, set out tools, and preheat only when the recipe calls for it. Keep towel ends, paper, and loose sleeves away from burners.'],
['🧼 Clean Hands, Clean Station','Wash hands with soap and water before cooking and after touching raw meat, seafood, eggs, or rubbish. Use separate boards or thoroughly wash and sanitize between raw animal foods and ready-to-eat ingredients.'],
['🔪 How to Dice an Onion','Cut off the stem end, halve through the root, and peel. Place each half flat-side down. Make lengthwise cuts toward—but not through—the root, then crosswise cuts to create dice. Keep fingertips curled back and make smaller cuts for a finer dice.'],
['🧄 How to Mince Garlic','Separate a clove from the head and peel it. Trim the hard root tip, lightly crush the clove with the flat side of a knife if comfortable, then slice and rock the knife across the slices until finely chopped. Keep the knife tip controlled; a garlic press is another option.'],
['🥕 How to Cut Carrots: Coins, Sticks & Dice','Wash and trim the ends; peel if desired. For coins, slice crosswise. For sticks, cut into manageable lengths, slice a thin piece to make a flat base, then cut planks and sticks. For dice, cut the sticks crosswise. Keep pieces similar in size for even cooking.'],
['🥕 How to Julienne Vegetables','Wash and trim the vegetable. Cut a flat side so it sits securely, slice into even planks, stack a few planks, then cut into thin matchsticks. Work in small stacks and keep fingertips curled back. This works well for carrots, bell peppers, and firm vegetables.'],
['🫑 How to Slice a Bell Pepper','Wash and dry the pepper. Cut around the stem and lift out the core and seeds. Cut the pepper into flat panels, place skin-side down, then slice into strips. For dice, gather the strips and cut across them.'],
['🥦 How to Cut Broccoli Florets','Rinse the broccoli. Cut florets from the main stalk where the small stems branch off; split large florets through their stems so they are similar in size. Peel the tough outer layer of the stalk, then slice the tender center into coins or sticks.'],
['🥬 How to Shred Cabbage','Remove damaged outer leaves and rinse the cabbage. Cut it into quarters through the core, then cut out the tough core from each quarter. Place a quarter flat-side down and slice crosswise into thin ribbons. For stir-fries, cut some ribbons shorter if needed.'],
['🍅 How to Dice a Tomato','Wash and dry the tomato. Use a sharp knife or serrated knife. Cut into slices, stack or arrange the slices, then cut into strips and crosswise into dice. For less watery dishes, remove some seeds and gel if the recipe calls for it.'],
['🥒 How to Cut Cucumber: Rounds, Half-Moons & Dice','Wash and dry. Trim the ends. Slice crosswise for rounds; halve lengthwise first for half-moons. For dice, cut into long planks, then strips, then crosswise cubes. Keep the pieces even so they look tidy and cook consistently.'],
['🍄 How to Slice Mushrooms','Brush away dirt or rinse briefly and dry well. Trim any dry stem end. Place the mushroom on its side and slice from cap to stem with controlled, even cuts. Quarter small mushrooms instead when the recipe needs larger pieces.'],
['🥑 How to Cut an Avocado Safely','Wash the outside first. On a stable board, cut lengthwise around the fruit and twist the halves apart. Remove the pit with a spoon rather than striking it with a knife. Scoop out the flesh and slice or dice on the board.'],
['🌿 How to Chop Fresh Herbs','Rinse herbs and dry them thoroughly. Remove tough stems when needed, gather the leaves into a small loose pile, and use a sharp knife to slice or chop with a controlled rocking motion. Avoid repeatedly crushing delicate leaves; basil is often best sliced just before use.'],
['🫚 How to Slice Ginger','Scrape the thin skin with a spoon if desired. Cut off a manageable piece and slice across the fibers for tender pieces. For matchsticks, stack thin slices and cut into strips; for mince, gather the strips and chop finely. A grater works for paste-like ginger.'],
['🥬 How to Cut Bok Choy','Separate the leaves and rinse carefully around the base to remove grit. Trim the root end. Slice thick white stems crosswise and keep the tender green leaves in larger pieces. Add stems first when stir-frying and leaves near the end.'],
['🍋 How to Zest and Cut Citrus','Wash and dry the lemon or lime. For zest, grate only the colored outer layer and stop before the bitter white pith. For wedges, cut lengthwise through the fruit, then cut each half into wedges. For juice, halve across the middle and squeeze over a small strainer if desired.'],
['🍍 How to Cut Pineapple','Lay the pineapple on a stable board and trim top and base so it stands securely. Slice away the peel in strips from top to bottom, then remove remaining eyes. Cut into quarters lengthwise and remove the tough core before slicing or dicing. Ask an adult for help if the fruit feels unstable.'],
['🥭 How to Dice a Mango','Wash the mango. Hold it upright and slice down each side of the flat pit to make two cheeks. Score the flesh in a grid without cutting through the skin, then push the skin outward and cut the cubes away with a spoon or knife. Trim remaining flesh from around the pit.'],
['🧅 Onions & Red Onions','Trim the stem end, cut the onion in half through the root, peel, and make controlled lengthwise and crosswise cuts. Keep the root end intact while dicing to help hold layers together. Red onions are useful raw in salads or cooked in sauces and stir-fries.'],
['🧄 Scallions & Green Onions','Trim the root ends and any wilted tips, rinse under running water, and dry. Slice white and green parts separately if the recipe cooks them at different times. Keep the pieces refrigerated in a clean container.'],
['🥕 Carrots & Parsnips','Scrub under running water and trim the ends. Peel if desired or if the skin is rough. Cut pieces to a similar size so they cook evenly; dense root vegetables usually need more time than leafy vegetables.'],
['🥔 Potatoes & Sweet Potatoes','Scrub thoroughly under running water and remove eyes or damaged areas. Cut evenly for roasting or boiling. Do not use potatoes that are green, bitter, or heavily sprouted. Keep raw cut potatoes from drying out and cook promptly.'],
['🥦 Broccoli & Cauliflower','Rinse under running water and separate florets into similar sizes. Peel the tougher outer layer from thick broccoli stems and slice the tender center. Dry well before roasting so the vegetables brown rather than steam.'],
['🥬 Cabbage, Napa Cabbage & Bok Choy','Remove damaged outer leaves and rinse leaves separately to remove grit. Slice thick ribs more finely than tender leaves. For stir-fries, add the stems first and leaves later so both finish tender.'],
['🍅 Tomatoes & Cherry Tomatoes','Rinse and dry before slicing. Use a stable board and a sharp knife; a serrated knife can help with ripe tomatoes. Cut just before serving if you want to keep salads from becoming watery.'],
['🥒 Cucumbers & Zucchini','Rinse and dry, trim both ends, and slice to a consistent thickness. For stir-fries, avoid crowding the pan; watery vegetables brown better when cooked in batches.'],
['🫑 Bell Peppers','Rinse, cut around the stem, remove the core and seeds, then slice into strips or dice. Keep the knife tip controlled and use a flat side of the pepper against the board for stability.'],
['🍆 Eggplant','Rinse, trim the stem, and cut into even cubes or slices. Salt only when a recipe calls for it or when you want to draw out moisture from a particular variety. Roast or sauté in batches to avoid steaming.'],
['🍄 Mushrooms','Brush off dirt or rinse briefly and dry well. Trim dry stem ends, then slice or quarter to a similar size. Cook in a roomy pan so moisture can evaporate and the mushrooms can brown.'],
['🥑 Avocado','Rinse the outside before cutting. Place it on a stable board and carefully cut around the pit; do not strike the pit with a knife. Scoop or peel the flesh, then add citrus if the recipe needs slower browning.'],
['🍋 Lemons, Limes & Citrus','Wash the fruit before zesting or cutting. Zest only the colored outer peel, avoiding the bitter white pith. Roll gently on the counter to help release juice, then cut across the middle and squeeze.'],
['🌿 Fresh Herbs: Cilantro, Parsley & Basil','Remove damaged leaves, rinse gently under running water, and dry thoroughly. Pick leaves from tough stems; tender cilantro and parsley stems can often be chopped for cooked dishes. Add delicate basil near the end of cooking.'],
['🌶️ Fresh Chili Peppers','Rinse and dry, remove the stem, and slice or mince with a controlled knife grip. Avoid touching your eyes; wash hands, board, and knife well after handling hot peppers. Use gloves if your skin is sensitive.'],
['🌱 Lemongrass & Galangal','For lemongrass, trim the dry ends and remove tough outer layers; bruise whole pieces for flavoring or finely mince the tender inner portion. Galangal is firm and fibrous, so slice thinly for infusing soups and curry pastes and remove large pieces if the recipe calls for it.'],
['🫚 Fresh Ginger','Scrape the thin skin with a spoon if desired, then slice across the fibers, mince, or grate. Grated ginger disperses quickly; larger slices can flavor broths and be removed before serving.'],
['🥬 Bean Sprouts','Keep refrigerated and follow package guidance. Rinse under running water just before use and drain well. For people at higher risk from foodborne illness, cooked sprouts are safer than raw sprouts; cook thoroughly in stir-fries or soups.'],
['🫛 Green Beans & Snow Peas','Rinse, trim stem ends, and remove strings if present. Cut into similar lengths. Add tender snow peas near the end of cooking so they stay bright and crisp.'],
['🌽 Corn on the Cob','Remove husks and silk, rinse, and cut kernels from the cob only on a stable board with the cob held securely. Keep the flat end down when possible and use a controlled downward cut.'],
['🍗 Raw Chicken','Keep raw chicken separate from ready-to-eat foods and do not rinse it. Use a dedicated board or wash and sanitize the board and tools after use. Cook all poultry to 165°F (74°C), checking the thickest part with a food thermometer.'],
['🥩 Beef & Steak','Keep raw beef chilled until prep time and use separate tools from produce. Pat dry with a paper towel if browning is needed, then discard the towel and wash hands. Use a thermometer and follow safe minimum temperatures for the cut and preparation.'],
['🐖 Pork Chops & Pork Tenderloin','Keep pork refrigerated and separate from produce. Trim excess fat if desired using a stable board and controlled cuts. Whole cuts of pork should reach 145°F (63°C) followed by a 3-minute rest; ground pork should reach 160°F (71°C).'],
['🍔 Ground Beef & Ground Meat','Keep ground meat cold and handle it with clean hands or utensils. Do not reuse a plate or tools that held raw meat for cooked food unless washed first. Cook ground beef, pork, lamb, or veal to 160°F (71°C); ground poultry to 165°F (74°C).'],
['🦃 Turkey','Keep raw turkey separate from produce and ready-to-eat foods; do not wash it. Clean and sanitize the sink area if raw juices touch it. Cook turkey to 165°F (74°C) in the thickest parts, checking with a food thermometer.'],
['🐟 Fish Fillets','Keep fish refrigerated and prepare it on a clean, separate board. Check for pin bones with clean fingers or tweezers and remove them carefully. Cook fish to 145°F (63°C), or until flesh is opaque and separates easily with a fork.'],
['🍤 Shrimp & Prawns','Keep shrimp cold until ready to prep. Peel and devein if needed, then wash hands and tools after handling raw seafood. Cook until the flesh is pearly and opaque; avoid cross-contamination with cooked shrimp or salad ingredients.'],
['🦪 Mussels & Clams','Keep live shellfish chilled and follow trusted seafood-safety guidance. Discard cracked shells or shells that do not close when tapped before cooking. Cook until shells open and discard any that remain closed after cooking; follow local food-safety guidance.'],
['🥚 Eggs','Wash hands after handling raw eggs and keep eggs away from ready-to-eat foods. Crack eggs into a separate small bowl rather than directly into a mixed dish so shell pieces can be removed and spoiled eggs do not ruin the batch. Cook eggs until whites and yolks are firm unless using pasteurized eggs for a suitable recipe.'],
['🥓 Bacon & Sausage','Keep raw bacon and sausage separate from other ingredients. Prepare vegetables first, then handle raw meat, or thoroughly clean and sanitize tools between tasks. Cook sausage thoroughly; ground sausage should reach 160°F (71°C), or 165°F (74°C) for poultry sausage.'],
['🥢 Tofu & Tempeh','Keep refrigerated and follow the package date and handling instructions. Drain tofu and pat dry for better browning; cut into even cubes or slabs. Use clean utensils and refrigerate leftovers promptly.'],
['🍜 Asian Aromatics: Garlic, Ginger & Scallions','Prepare garlic, ginger, and scallions before heating the wok or pan because aromatics can burn quickly. Slice ingredients evenly and keep sauces measured nearby. Add garlic and ginger after the pan is ready, stirring briefly before adding wetter ingredients.'],
['🥢 Noodles: Prep Before the Wok','Read the package because rice noodles, wheat noodles, and fresh noodles need different soaking or cooking times. Drain well before stir-frying and prepare sauce, vegetables, and protein first. Avoid leaving cooked noodles at room temperature; refrigerate promptly.'],
['🍚 Rice: Rinse, Measure & Store','Follow the rice variety and package instructions for rinsing and water ratio. Use a clean pot or rice cooker. Refrigerate cooked rice promptly in shallow containers; do not leave it at room temperature for extended periods.'],
['🌏 Daikon, Lotus Root & Asian Eggplant','Rinse and scrub daikon and lotus root well; peel if the recipe prefers. Slice lotus root evenly and keep cut pieces from drying out. Trim Asian eggplant and cut to a similar size; cook until tender.'],
['⚖️ Ingredient Weights: Flour, Sugar & More','Approximate weights depend on how an ingredient is packed and measured. 1 US cup all-purpose flour is about 120 g; 1 cup granulated sugar about 200 g; 1 cup packed brown sugar about 220 g; 1 cup water about 240 g; 1 cup butter about 227 g. For baking, weigh ingredients when possible and follow the recipe’s stated method.'],
['🥕 Ingredient Weights: Chopped Produce','Approximate chopped yields: 1 medium onion is around 150 g and about 1 cup; 1 medium carrot around 60–75 g and about ½ cup; 1 medium bell pepper around 150 g and about 1 cup; 1 cup chopped broccoli around 90–100 g. Produce sizes and cut sizes vary, so treat these as planning estimates.'],
['🧄 Ingredient Weights: Garlic & Ginger','Garlic varies greatly by clove size: 1 medium clove is roughly 1 teaspoon minced, often around 3 g; 1 tablespoon minced garlic is about 3 medium cloves. One tablespoon grated fresh ginger may weigh around 6 g. These are approximate kitchen conversions, not exact substitutes for a scale.'],
['📏 What Does “Dice” Mean?','Dice means cutting food into small, fairly even cubes. Recipes may specify small, medium, or large dice; unless a size is given, aim for pieces that cook evenly and suit the dish. First cut the ingredient into planks, then sticks, then cubes.'],
['🔪 Chop vs. Mince vs. Slice','SLICE: cut into flat pieces. CHOP: cut into pieces, often less uniform than a dice. DICE: cut into fairly even cubes. MINCE: cut very finely. Use a stable board and controlled cuts; smaller pieces usually cook faster and release flavor more quickly.'],
['🥕 Julienne & Batonnet','JULIENNE means thin matchsticks; BATONNET means thicker sticks. Trim the ingredient, create a flat side, cut into even planks, stack a few planks, then cut into sticks. Keep fingers curled back and work in small stacks so pieces do not slide.'],
['🌿 What Is Chiffonade?','Chiffonade makes fine ribbons from leafy herbs or greens. Stack clean, dry leaves, roll them loosely into a small cylinder, then slice crosswise with a sharp knife. Use a gentle, controlled motion; delicate herbs such as basil are best cut shortly before serving.'],
['🍳 Cooking Terms: Sauté, Simmer & Sear','SAUTÉ: cook smaller pieces in a little fat over moderate-to-high heat, stirring as needed. SIMMER: cook gently with small bubbles, not a vigorous boil. SEAR: brown the surface over high heat before continuing the recipe. Pan heat and timing depend on the food and recipe.'],
['🥣 Cooking Terms: Whisk, Fold & Beat','WHISK: mix briskly to combine or incorporate air. BEAT: mix more vigorously until a recipe’s texture changes. FOLD: gently combine by sweeping a spatula down through the mixture and up over itself, preserving air in batters such as whipped cream or egg whites.'],
['🥬 Cooking Terms: Blanch, Drain & Pat Dry','BLANCH: briefly cook food in boiling water, often followed by an ice bath. DRAIN: remove liquid using a colander or sieve. PAT DRY: gently blot with a clean paper towel or kitchen towel. Drying vegetables or tofu can help browning; follow the recipe for timing.'],
['🧂 Cooking Terms: Season to Taste','Season to taste means add a little seasoning, taste safely, and adjust gradually. Consider salt, acid such as lemon juice, herbs, heat, and sweetness. Do not taste food that contains raw meat, raw eggs, or other ingredients that are not safe to eat uncooked.'],
['🌡️ Final Food-Safety Temperature Check','Use a food thermometer rather than color alone. Common US minimums: poultry 165°F (74°C); ground beef, pork, lamb, or veal 160°F (71°C); fish 145°F (63°C); whole cuts of pork, beef, lamb, and veal generally 145°F (63°C) with a 3-minute rest. Check the thickest part and follow current official guidance for special dishes.'],
['🔪 Knife & Cutting Board Safety Check','Place a damp towel under a cutting board if it slides. Keep the knife sharp and controlled, curl fingertips back, and cut away from your body when appropriate. Never try to catch a falling knife. Keep raw meat separate from ready-to-eat foods and wash hands, tools, and surfaces between tasks.'],
['🧼 Final Prep Station Safety Check','Wash produce under running water, not soap. Keep raw meat and seafood separate from ready-to-eat ingredients; do not wash raw poultry. Refrigerate perishables promptly and clean spills as you go. When uncertain about a food’s safety, do not taste it to check.']
['🧊 Mise en Place for Meat & Produce','Prepare produce first, then raw meat or seafood, using separate boards and utensils. Measure sauces, arrange ingredients in cooking order, and keep raw animal foods refrigerated until needed. Never put cooked food back on a plate that held raw meat unless it has been washed.']
]},
secret:{title:'🔐 The Secret Room — The Forbidden Recipe Archive',desc:'Some recipes aren’t just about food. They’re about people, places, and the stories someone tried to erase.',items:[['📜 The Recipe With No Name','A recipe fragment waits on the central desk.']]},
trash:{title:'♻️ Rook’s Trash Can — Reuse & Regrow',desc:'“Before you throw that away, ask one question: is its story actually over?” Welcome to Rook’s quietly clever reuse workshop. Explore regrowing, composting, safe reuse, item sorting, and a few secrets hiding in plain sight.',items:[
['🌱 Grow It Again — Green Onions','ROOK’S FIELD NOTE: Green onions are one of the easiest kitchen scraps to try regrowing. Place the clean white root ends in a small glass with enough water to cover the roots, keep the tops above water, and set them in bright light. Refresh the water regularly. New green growth is useful, but this does not guarantee a whole new onion; potting in soil may help longer-term growth. Try sound romaine bases or celery bases too, knowing results vary.'],
['♻️ Compost Corner — What Belongs?','ROOK’S FIELD NOTE: Many fruit and vegetable scraps, coffee grounds, paper filters, and eggshells can suit a home compost system. Acceptance depends on the system and local program. Meat, dairy, oils, and cooked foods may attract pests or be excluded from basic backyard bins; check your local rules before adding them. Keep compost balanced with suitable “greens” and “browns,” and never assume every compostable-labeled item belongs in every bin.'],
['🫙 Second-Chance Shelf — Reuse Safely','ROOK’S FIELD NOTE: Clean citrus zest can brighten baking or dressings. Broccoli stems can be peeled, sliced, and cooked. Tender herb stems can flavor soups and sauces. Sound vegetable scraps can be frozen in a labeled bag for a future stock, then simmered and strained. Use clean, food-safe containers for food; do not reuse a container for food if it held chemicals or is damaged. Refrigerate perishable scraps promptly.'],
['🔎 Where Does It Go? — Sorting Field Guide','ROOK’S FIELD NOTE: Search the item list and choose the closest match. Fruit and vegetable scraps may be compostable where accepted; clean jars may be reusable; packaging depends on local recycling rules; and spoiled food should not be tasted to test safety. Moldy or unsafe food is not rescued by trimming or cooking in every case. When uncertain, follow local waste guidance and choose safety over salvage.'],
['✨ Reveal a Secret — Rook’s Hidden Notes','ROOK’S SECRET: The best waste-reduction trick is often planning before the scraps exist. Freeze small portions of sound vegetable trimmings as you cook, label the bag, and use them for stock when you have enough. A second secret: not every scrap can regrow, and not every item belongs in compost. “Mystery is fun. Mystery mold is not. Throw that one away.”'],
['🍋 Citrus Peels — A Bright Second Life','Clean zest can flavor sugar, baked goods, or dressings. Avoid the bitter white pith when zesting. Compost peels only if your compost system accepts them.'],
['🥔 Potato Peels — Check First','Peels from sound potatoes can be roasted if cleaned and prepared safely. Do not use green, bitter, or heavily sprouted potatoes; discard them.'],
['🥚 Eggshells — Compost Check','Rinse eggshells if your compost method recommends it, crush them, and add only where accepted. They are not a quick fix for plant calcium needs.'],
['⚠️ Safety First — No Guesswork','Never taste food to decide whether it is safe. Discard food with concerning spoilage, and do not reuse scraps that may have contacted chemicals. Keep raw-food scraps chilled if you are saving them for later cooking.'],
['🧅 Green Onion Regrowth','Set clean root ends in a small glass with roots covered and leaves above water. Give bright light and refresh water frequently. Harvest modest new greens; regrowth is not a guarantee of a full new plant.'],
['🥬 Romaine Lettuce Base','A sound romaine base may produce small leaves in shallow water and bright light. Change water regularly. Treat this as a small experiment, not a promise of a full new lettuce head.'],
['🌿 Herb Stem Cuttings','Some herbs, such as mint and basil, may root from healthy cuttings. Remove lower leaves, place stems in clean water, and change it often. Rooting success depends on the herb and cutting.'],
['🥕 Carrot Tops — What to Expect','The crown may grow leafy greens, but it will not regrow a new carrot root. Use the leaves only if the carrot is sound, the greens are correctly identified, and you know they suit your recipe.'],
['🧄 Garlic Cloves','A sprouting garlic clove can grow green shoots in soil, but the result varies. Use sound cloves; discard any that are moldy or soft and decaying.'],
['☕ Coffee Grounds','Used coffee grounds can go into some compost systems in moderate amounts. They are not magic fertilizer; avoid piling thick layers directly onto garden soil.'],
['🍌 Banana Peels','Banana peels may be accepted by many home compost systems, where they break down over time. Chop them into smaller pieces to help decomposition. Do not assume every municipal organics program accepts them.'],
['🍎 Apple Cores','Apple cores can often be composted where food scraps are accepted. Remove stickers if possible and check local collection rules.'],
['🥦 Broccoli Stems','Trim away any tough or damaged outer parts, then peel and slice the tender stem for stir-fries, soups, slaws, or roasting. Store refrigerated and use promptly.'],
['🥔 Potato Peels','Peels from sound potatoes can be cooked after washing and safe preparation. Do not use green, bitter, or heavily sprouted potatoes; discard them rather than trying to salvage them.'],
['🍋 Lemon & Citrus Peel','Clean zest can flavor sugar, baked goods, dressings, and marinades. Avoid the bitter white pith when zesting. Compost only if your system accepts citrus.'],
['🥚 Eggshells','Eggshells may be compostable in systems that accept them; crushing helps them break down. They do not quickly solve plant nutrient problems. Wash hands and surfaces after handling raw eggs.'],
['🥖 Stale Bread','Bread that is simply dry but has no signs of spoilage can sometimes become croutons, breadcrumbs, or toast. If it is moldy, discard it; do not sniff closely or trim around the mold.'],
['🍞 Moldy Bread — Discard','Bread is porous, so visible mold can extend beyond the spot you see. Do not taste it or cut off only the moldy patch. Discard the loaf and clean the storage area.'],
['🫙 Clean Glass Jars','A clean, undamaged food jar may be reused for dry storage or crafts. For canning and shelf-stable preserving, use jars and lids designed for that purpose and follow tested guidance.'],
['📦 Cardboard & Egg Cartons','Clean, dry cardboard may be recyclable where accepted; greasy or food-soiled material may be treated differently. Molded-pulp cartons may be compostable in some systems; foam and plastic cartons follow different local rules.'],
['🧊 Freezer Scrap Bag','Freeze sound vegetable trimmings promptly in a labeled, food-safe bag. Avoid scraps that are spoiled or contaminated. Use the frozen trimmings in a suitable stock, then strain and discard the spent solids.'],
['🥕 Vegetable Stock Scraps','Onion ends, clean carrot peels, and herb stems can add flavor to stock. Avoid moldy scraps, excessive bitter brassica scraps, and anything dirty or chemically contaminated. Freeze promptly if not using soon.'],
['🥛 Dairy & Meat Scraps','Do not put meat, fish, dairy, or oily leftovers into a basic backyard compost bin unless its specific guidance allows them. They may attract pests. Follow local organics collection instructions.'],
['🛢️ Cooking Oil','Do not pour cooking oil or grease down the drain. Let small amounts cool and absorb into an appropriate disposable material if local guidance allows, or use a local collection option for larger amounts.'],
['🔋 Batteries & Electronics','Do not put batteries or electronics in ordinary recycling or compost. Look for an approved local drop-off or household hazardous-waste program; lithium batteries can pose fire risks.'],
['🧴 Chemical Containers','Never reuse a container that held cleaners, pesticides, fuel, or other chemicals for food. Follow the product label and local hazardous-waste guidance for disposal.'],
['🌱 Compost Greens & Browns','Many compost systems need a balance of nitrogen-rich “greens” and carbon-rich “browns,” plus moisture and air. The right balance depends on your system; follow its instructions.'],
['🪴 When Regrowth Fails','Not every vegetable scrap can regrow into a full plant. Some produce is harvested for its root, fruit, or seed, and a cut base may only make leaves. That is a useful experiment, not a failure.'],
['🧽 Clean Before Reusing','Wash reusable food containers with dish soap and water, check for cracks or lingering odors, and let them dry. Do not reuse containers that are damaged or were not intended for food.'],
['🗓️ Label & Plan','Label freezer bags and leftovers with the name and date. Plan a meal around the most perishable ingredients first, and follow safe storage timelines rather than relying on smell alone.'],
['🕵️ Rook’s Final Clue','Waste prevention begins before the bin: plan portions, store food correctly, freeze extras promptly, and buy what you can use. Cleverness is not forcing unsafe food to become dinner.']
]},
hq:{title:'🦖 Lil Dino’s Kitchen HQ',desc:'Home base for Little Dino’s Kitchen Adventures!',items:[
['💗 Cook','Pick a recipe, gather ingredients, and read the full instructions before starting.'],
['🗺️ Explore','Choose a room on the kitchen map to learn storage, prep, seasoning, and cooking basics.'],
['✨ Discover','Try one new ingredient, technique, or flavor combination at a time.'],
['🐹 Meet the adventure buddy','Lil Dino’s tiny hamster-dragon buddy is the official kitchen-floor supervisor. Keep curious pets away from hot surfaces, knives, and food-prep areas.']
]}
};
const panel=document.getElementById('panel');
const title=document.getElementById('roomTitle');
const desc=document.getElementById('roomDesc');
const list=document.getElementById('roomList');
const tipBox=document.getElementById('tipBox');
const pantrySearch=document.getElementById('pantrySearch');
const pantrySearchInput=document.getElementById('pantrySearchInput');
const pantrySearchResult=document.getElementById('pantrySearchResult');
const pantrySmartResults=document.getElementById('pantrySmartResults');
const pantryPassport=document.getElementById('pantryPassport');
const substitutionLab=document.getElementById('substitutionLab');
const storageGuide=document.getElementById('storageGuide');
const flavorGuide=document.getElementById('flavorGuide');
let activeRoom='';
const fridgeSearchWrap=document.createElement('div');
fridgeSearchWrap.className='fridge-search';
fridgeSearchWrap.hidden=true;
fridgeSearchWrap.innerHTML='<label for="fridgeIngredientSearch">🌏 Find a fridge ingredient</label><input id="fridgeIngredientSearch" type="search" placeholder="Try bok choy, tofu, berries, paneer…" autocomplete="off"><p>Type an ingredient to find its guide. Search includes ingredients from Asian cuisines and around the world.</p><div id="fridgeSearchStatus" aria-live="polite"></div>';
list.parentNode.insertBefore(fridgeSearchWrap,list);
const fridgeIngredientSearch=fridgeSearchWrap.querySelector('#fridgeIngredientSearch');
const fridgeSearchStatus=fridgeSearchWrap.querySelector('#fridgeSearchStatus');
const archivistSearchWrap=document.createElement('div');
archivistSearchWrap.className='archivist-search';
archivistSearchWrap.hidden=true;
archivistSearchWrap.innerHTML='<label for="archivistSearchInput">📜 Search Baking Help or Archive Clues</label><form id="archivistSearchForm"><input id="archivistSearchInput" type="search" placeholder="Try flour, baking powder, or torn page…" autocomplete="off"><button type="submit">Search notes</button></form><div class="archivist-secret-box"><p><strong>📖 The Archivist’s Baking Secrets</strong><br>Small notes from the margins of the recipe books.</p><button type="button" id="revealBakingSecret">🔐 Reveal a Secret</button><div id="bakingSecretResult" aria-live="polite"></div></div><div class="baking-rescue-box"><p><strong>🧁 The Baking Rescue Desk</strong><br>Something went wrong? Choose your baking mystery and get a few practical fixes.</p><label for="bakingRescueProblem">What happened?</label><select id="bakingRescueProblem"><option value="cookies">🍪 My cookies spread too thin</option><option value="drycake">🍰 My cake turned out dry</option><option value="rise">🍞 My bread or cake did not rise</option><option value="brownies">🍫 My brownies turned out cakey</option><option value="frosting">🧁 My frosting is too runny</option><option value="burnt">🔥 The outside browned before the middle baked</option><option value="dense">🥮 My bake is dense or tough</option>\n<option value="hardcookies">🍪 My cookies are hard or burnt</option>\n<option value="nocookie">🍪 My cookies barely spread</option>\n<option value="sinkcake">🎂 My cake sank in the middle</option>\n<option value="stuckcake">🎂 My cake stuck to the pan</option>\n<option value="cupcakes">🧁 My cupcakes overflowed or baked unevenly</option>\n<option value="gummybread">🍞 My bread is gummy inside</option>\n<option value="doughrise">🍞 My yeast dough will not rise</option>\n<option value="piecrust">🥧 My pie crust shrank or cracked</option>\n<option value="soggypie">🥧 My pie crust is soggy</option>\n<option value="chocolate">🍫 My chocolate seized or got grainy</option>\n<option value="stiff frosting">🍥 My frosting is too stiff or grainy</option>\n<option value="lumpy">🥞 My batter is lumpy</option>\n<option value="pan">📏 I need a different pan size</option>\n<option value="substitute">🥚 I am missing an ingredient</option></select><button type="button" id="bakingRescueButton">🛟 Help me rescue it</button><div id="bakingRescueResult" aria-live="polite"></div></div><p>Ask a practical baking question, or search for one of the Archivist’s unusual records.</p><div id="archivistSearchStatus" aria-live="polite"></div>';
list.parentNode.insertBefore(archivistSearchWrap,list);
const cafeSearchWrap=document.createElement('div');
cafeSearchWrap.className='cafe-search';
cafeSearchWrap.hidden=true;
cafeSearchWrap.innerHTML='<h3>🔎 Search Ham’s Café Menu</h3><p>Tell Ham what flavor you want—or type a drink name to find its recipe.</p><form id="cafeSearchForm"><input id="cafeSearchInput" type="search" placeholder="Try chocolate, mango, fruity tea, sweet coffee…" autocomplete="off"><button type="submit">Find My Drink</button></form><div id="cafeSearchResults" aria-live="polite"></div>';
list.parentNode.insertBefore(cafeSearchWrap,list);
const cafeSearchInput=cafeSearchWrap.querySelector('#cafeSearchInput');
const cafeSearchResults=cafeSearchWrap.querySelector('#cafeSearchResults');
const cafeDrinkRecipes=[
 {name:'Chocolate Mocha',keys:['chocolate','mocha','sweet coffee','chocolate coffee'],kind:'Coffee',recipe:'Mix 1–2 teaspoons cocoa powder and sweetener to taste into 2 tablespoons hot coffee until smooth. Add 1 cup hot or cold milk and 1 shot espresso or ½ cup strong coffee. Serve warm or over ice.'},
 {name:'Strawberry Milk Tea',keys:['strawberry','milk tea','fruity tea','fruit tea','sweet tea'],kind:'Tea',recipe:'Steep 1 black tea bag in ½ cup hot water for 3–5 minutes; remove the bag and cool. Stir in 2–3 tablespoons strawberry syrup or mashed strawberry purée. Pour over ice and add ½ cup milk. Adjust sweetness to taste.'},
 {name:'Mango Iced Tea',keys:['mango','fruity tea','fruit tea','sweet tea','iced tea'],kind:'Tea',recipe:'Steep 1 black or green tea bag in 1 cup hot water according to the package, then cool. Stir in 2–4 tablespoons mango purée or mango nectar. Pour over ice and add a squeeze of lime if desired.'},
 {name:'Mango Milk Tea',keys:['mango','milk tea','sweet tea'],kind:'Tea',recipe:'Brew 1 black tea bag in ½ cup hot water for 3–5 minutes; remove and cool. Stir in 2–3 tablespoons mango purée or syrup, add ½ cup milk, and serve over ice. Add cooked tapioca pearls if you have them.'},
 {name:'Strawberry Smoothie',keys:['strawberry','smoothie','fruity','fruit','sweet'],kind:'Smoothie',recipe:'Blend 1 cup strawberries (fresh or frozen), ½ banana, ½ cup milk or yogurt, and ½–1 cup ice or frozen fruit until smooth. Add honey or sugar only if needed.'},
 {name:'Mango Smoothie',keys:['mango','smoothie','fruity','fruit','sweet'],kind:'Smoothie',recipe:'Blend 1 cup mango chunks, ½ cup yogurt, and ½ cup milk or juice. Add ice for a thicker drink, or a little more liquid for a thinner smoothie.'},
 {name:'Chocolate Frappé',keys:['chocolate','frappe','frappé','sweet coffee','iced coffee'],kind:'Blended coffee',recipe:'Blend ½ cup chilled strong coffee, ½ cup milk, 1 tablespoon cocoa or chocolate syrup, 1–2 teaspoons sugar (to taste), and 1 cup ice until slushy. Top with whipped cream if desired.'},
 {name:'Vanilla Sweet Iced Coffee',keys:['sweet coffee','coffee','vanilla','iced coffee'],kind:'Coffee',recipe:'Stir 1–2 teaspoons vanilla syrup into ¾ cup chilled coffee. Add ½ cup milk and pour over ice. Taste before adding more sweetener.'},
 {name:'Brown Sugar Milk Tea',keys:['milk tea','sweet tea','boba','brown sugar'],kind:'Tea',recipe:'Steep 1 black tea bag in ½ cup hot water for 3–5 minutes; remove and cool. Stir in 1–2 teaspoons brown sugar until dissolved, add ½ cup milk, and serve over ice. Add cooked tapioca pearls if desired.'},
 {name:'Peach Fruity Tea',keys:['peach','fruity tea','fruit tea','sweet tea','iced tea'],kind:'Tea',recipe:'Brew 1 black or green tea bag according to package directions and cool. Stir in 2–3 tablespoons peach nectar or peach purée, pour over ice, and finish with lemon if desired.'},
 {name:'Snickers-Inspired Frappé',keys:['snickers','chocolate','caramel','peanut butter','frappe','frappé'],kind:'Fun café creation',recipe:'Blend ½ cup chilled coffee, ½ cup milk, 1 tablespoon chocolate syrup, 1 tablespoon caramel sauce, 1 teaspoon peanut butter (check allergy needs), and 1 cup ice until smooth. This is a homemade flavor-inspired drink, not an official branded recipe.'},
 {name:'Ube Coconut Iced Latte',keys:['ube','coconut','sweet coffee','latte','purple'],kind:'Around-the-world café idea',recipe:'Whisk 1–2 teaspoons ube powder or ube spread with 2 tablespoons warm milk until smooth. Add ½ cup cold milk and ice, then pour in ½ cup chilled espresso or strong coffee. Sweeten to taste; omit coffee for a creamy ube milk drink.'},
 {name:'Classic Vanilla Milkshake',keys:['milkshake','milk shakes','milk shake','vanilla','classic shake','diner shake','creamy'],kind:'Classic diner milkshake',recipe:'Blend 2 cups vanilla ice cream with ½ cup cold milk and ½ teaspoon vanilla until smooth. Add a splash more milk for a thinner shake. Top with whipped cream if desired.'},
 {name:'Chocolate Milkshake',keys:['milkshake','milk shake','chocolate','chocolate shake','classic shake','diner shake','sweet','creamy'],kind:'Classic diner milkshake',recipe:'Blend 2 cups vanilla or chocolate ice cream, ½ cup milk, and 2 tablespoons chocolate syrup until smooth. For a richer chocolate flavor, add 1 teaspoon cocoa powder.'},
 {name:'Strawberry Milkshake',keys:['milkshake','milk shake','strawberry','strawberry shake','fruity','creamy','sweet'],kind:'Classic diner milkshake',recipe:'Blend 2 cups vanilla ice cream, ½ cup milk, and ½ cup sliced strawberries until smooth. Taste and add a little strawberry syrup if you want it sweeter.'},
 {name:'Cookies and Cream Milkshake',keys:['milkshake','milk shake','cookies and cream','oreo','cookie shake','dessert shake','chocolate','creamy'],kind:'Classic diner milkshake',recipe:'Blend 2 cups vanilla ice cream with ½ cup milk and 4 chocolate sandwich cookies until creamy. Crush another cookie over the top.'},
 {name:'Chocolate Peanut Butter Milkshake',keys:['milkshake','milk shake','peanut butter','chocolate','dessert shake','creamy'],kind:'Classic diner milkshake',recipe:'Blend 2 cups chocolate or vanilla ice cream, ½ cup milk, 1 tablespoon peanut butter, and 1 tablespoon chocolate syrup. Check allergy needs and avoid peanut butter if it is unsafe for anyone being served.'},
 {name:'Strawberry Cheesecake Milkshake',keys:['milkshake','milk shake','strawberry','cheesecake','dessert shake','extra sweet'],kind:'Over-the-top dessert milkshake',recipe:'Blend 2 cups vanilla ice cream, ½ cup milk, ½ cup strawberries, 1 tablespoon softened cream cheese, and 1 crushed graham cracker. Top with whipped cream and extra crumbs if desired.'},
 {name:'Banana Pudding Milkshake',keys:['milkshake','milk shake','banana','banana pudding','dessert shake','creamy'],kind:'Over-the-top dessert milkshake',recipe:'Blend 2 cups vanilla ice cream, ½ cup milk, ½ ripe banana, and 2 vanilla wafer cookies. Top with whipped cream and a wafer. Keep chilled and serve promptly.'},
 {name:'Brownie Batter Milkshake',keys:['milkshake','milk shake','brownie','brownie batter','chocolate','dessert shake','extra sweet'],kind:'Over-the-top dessert milkshake',recipe:'Blend 2 cups chocolate ice cream, ½ cup milk, and one fully baked, cooled brownie. Top with brownie pieces if desired; do not use raw brownie batter containing uncooked flour or eggs.'},
 {name:'Birthday Cake Milkshake',keys:['milkshake','milk shake','birthday cake','cake','vanilla','dessert shake','sprinkles'],kind:'Over-the-top dessert milkshake',recipe:'Blend 2 cups vanilla ice cream, ½ cup milk, ¼ teaspoon vanilla, and a small piece of baked vanilla cake. Top with whipped cream and sprinkles.'},
 {name:'Salted Caramel Pretzel Milkshake',keys:['milkshake','milk shake','caramel','salted caramel','pretzel','dessert shake','sweet'],kind:'Over-the-top dessert milkshake',recipe:'Blend 2 cups vanilla ice cream, ½ cup milk, and 1–2 tablespoons caramel sauce. Top with crushed pretzels and a tiny pinch of salt. Add pretzels just before serving so they stay crisp.'},
 {name:'Mango Coconut Milkshake',keys:['milkshake','milk shake','mango','coconut','tropical','fruity','dessert shake'],kind:'Fruity dessert milkshake',recipe:'Blend 1 cup mango chunks, 1½ cups vanilla ice cream, ¼ cup milk, and 2 tablespoons coconut milk until creamy. Add more milk a little at a time if needed.'},
 {name:'Peach Cobbler Milkshake',keys:['milkshake','milk shake','peach','peach cobbler','cinnamon','fruity','dessert shake'],kind:'Fruity dessert milkshake',recipe:'Blend 1 cup sliced peaches, 1½ cups vanilla ice cream, ¼–½ cup milk, and a pinch of cinnamon. Top with a little crushed baked cookie or crumble.'},
 {name:'Pineapple Vanilla Milkshake',keys:['milkshake','milk shake','pineapple','vanilla','tropical','fruity'],kind:'Fruity dessert milkshake',recipe:'Blend 1 cup well-drained pineapple chunks, 1½ cups vanilla ice cream, and ¼–½ cup milk until smooth. Add a little more pineapple for a stronger fruit flavor.'},
 {name:'Blueberry Cheesecake Milkshake',keys:['milkshake','milk shake','blueberry','cheesecake','fruity','dessert shake'],kind:'Fruity dessert milkshake',recipe:'Blend ½ cup blueberries, 1½ cups vanilla ice cream, ¼–½ cup milk, and 1 tablespoon softened cream cheese. Top with crushed graham cracker if desired.'},
 {name:'Strawberry Banana Milkshake',keys:['milkshake','milk shake','strawberry','banana','fruity','fruit shake'],kind:'Fruity dessert milkshake',recipe:'Blend ½ cup strawberries, ½ banana, 1½ cups vanilla ice cream, and ¼–½ cup milk until creamy.'}
];
function cafeEscape(text){return String(text).replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));}
cafeSearchWrap.querySelector('#cafeSearchForm').addEventListener('submit',e=>{
 e.preventDefault();
 const q=cafeSearchInput.value.trim().toLowerCase();
 if(!q){cafeSearchResults.innerHTML='<p>Type a flavor such as “chocolate” or a craving such as “fruity tea” to get started.</p>';return;}
 const terms=q.replace(/[^a-z0-9\s-]/g,' ').split(/\s+/).filter(Boolean);
 const recipes=cafeDrinkRecipes.map(r=>{const hay=(r.name+' '+r.keys.join(' ')+' '+r.kind+' '+r.recipe).toLowerCase();let score=0;if(r.name.toLowerCase()===q)score+=100;if(r.name.toLowerCase().includes(q))score+=30;if(r.keys.some(k=>k===q))score+=24;if(r.keys.some(k=>k.includes(q)))score+=12;if(terms.length>1&&terms.every(t=>hay.includes(t)))score+=18;else score+=terms.filter(t=>hay.includes(t)).length*3;return {...r,score};}).filter(r=>r.score>0).sort((a,b)=>b.score-a.score);
 const sectionMatches=rooms.cafe.items.map((entry,index)=>({entry,index})).filter(x=>(x.entry[0]+' '+x.entry[1]).toLowerCase().includes(q));
 let html='';
 if(recipes.length){html+='<h4>🥤 '+(recipes.length===1?'Here’s your drink recipe':'Ham’s recommendations')+'</h4>'+recipes.slice(0,6).map(r=>'<article class="cafe-search-result-card"><h4>'+cafeEscape(r.name)+'</h4><p><strong>'+cafeEscape(r.kind)+'</strong></p><p>'+cafeEscape(r.recipe)+'</p><p>🐹 Ham says: “Taste as you go. I volunteer for quality control.”</p></article>').join('');}
 if(sectionMatches.length){html+='<h4>📚 Café sections that may help</h4>'+sectionMatches.map(x=>'<button type="button" class="cafe-search-result" data-cafe-index="'+x.index+'">'+cafeEscape(x.entry[0])+'</button><p>'+cafeEscape(x.entry[1])+'</p>').join('');}
 if(!html){html='<p>No close match yet. Try chocolate, strawberry, mango, fruity tea, sweet coffee, milk tea, smoothie, frappé, or milkshake. Search for a specific drink name to find its recipe.</p>';}
 cafeSearchResults.innerHTML=html;
});
cafeSearchResults.addEventListener('click',e=>{const b=e.target.closest('[data-cafe-index]');if(!b)return;const idx=Number(b.dataset.cafeIndex);const choice=list.querySelector('[data-tip-index="'+idx+'"]');if(choice)choice.click();});
const archivistSearchInput=archivistSearchWrap.querySelector('#archivistSearchInput');
const archivistSearchStatus=archivistSearchWrap.querySelector('#archivistSearchStatus');
const revealBakingSecret=archivistSearchWrap.querySelector('#revealBakingSecret');
const bakingSecretResult=archivistSearchWrap.querySelector('#bakingSecretResult');
const archivistBakingSecrets=[
 {title:'🧈 Secret No. 1 — The Butter Rule',text:'Softened butter should give slightly when pressed, but it should not be melted. Softened butter can trap air when creamed with sugar; melted butter changes the texture.'},
 {title:'🌾 Secret No. 2 — The Flour Deception',text:'Spoon flour lightly into a dry measuring cup and level the top. Scooping directly from the bag can pack in extra flour and make baked goods dry.'},
 {title:'🥣 Secret No. 3 — The Overmixing Curse',text:'For tender muffins and quick breads, mix wet and dry ingredients only until just combined. A few small lumps are usually better than overmixing.'},
 {title:'⚗️ Secret No. 4 — The Two White Powders',text:'Baking soda and baking powder are not interchangeable 1:1. Baking soda needs acid in the recipe; baking powder includes an acid component.'},
 {title:'🍪 Secret No. 5 — The Waiting Period',text:'Many cookies continue to set as they cool. Let them rest on the baking sheet for the recipe’s suggested time before moving them to a cooling rack.'},
 {title:'🔥 Secret No. 6 — The Untrustworthy Oven',text:'An oven dial can be inaccurate. An oven thermometer can help you check the actual temperature, especially if cakes bake unevenly or cookies brown too quickly.'}
];
let lastBakingSecretIndex=-1;
revealBakingSecret.addEventListener('click',()=>{
 if(activeRoom!=='baking')return;
 let nextIndex=Math.floor(Math.random()*archivistBakingSecrets.length);
 if(archivistBakingSecrets.length>1){while(nextIndex===lastBakingSecretIndex)nextIndex=Math.floor(Math.random()*archivistBakingSecrets.length);}
 lastBakingSecretIndex=nextIndex;
 const secret=archivistBakingSecrets[nextIndex];
 bakingSecretResult.textContent=secret.title+'\n'+secret.text;
});
const bakingRescueAdvice={
 cookies:{title:'🍪 Cookies spreading too thin',text:'• Chill the dough for 20–30 minutes if the recipe allows.\n• Use a cool baking sheet, not one that is still hot from the previous batch.\n• Check that the butter was softened, not melted, unless the recipe says otherwise.\n• Measure flour carefully; too little can make cookies spread.\nNext time: bake one test cookie before baking the whole tray.'},
 drycake:{title:'🍰 A dry cake',text:'• Check for overbaking; start checking a few minutes before the recipe’s stated time.\n• Measure flour by spooning it into the cup and leveling it, rather than scooping and packing.\n• Mix only as much as the recipe directs after adding flour.\nFor this cake: serve with fruit, yogurt, or a light syrup if the flavor suits it. Avoid adding liquid blindly to the whole cake.'},
 rise:{title:'🍞 The bake did not rise',text:'• Check the expiration date and storage of baking powder or baking soda.\n• Confirm you used the correct leavener; they are not a 1:1 swap.\n• Make sure the oven was fully preheated before the pan went in.\n• For yeast dough, check that the yeast is active and the liquid was not too hot.\nClue: a sudden change in ingredient amounts or mixing method can also affect rise.'},
 brownies:{title:'🍫 Brownies turned out cakey',text:'• Brownies with more flour or more leavening tend to be cakier.\n• Avoid adding extra flour when measuring; spoon and level it.\n• Mix only as directed and check doneness early—overbaking dries them out.\nIf the recipe is designed for fudgy brownies, check whether baking powder was accidentally added.'},
 frosting:{title:'🧁 Frosting is too runny',text:'• If it is buttercream, chill it briefly, then beat again.\n• Add powdered sugar a little at a time if the recipe’s balance allows.\n• If the butter or cream cheese became very warm, cooling may help.\n• For whipped cream frosting, chill the bowl and cream; do not keep adding sugar as the only fix.\nDifferent frostings behave differently, so use the recipe’s specific guidance.'},
 burnt:{title:'🔥 Outside browned, middle still underdone',text:'• Check that the oven rack is near the recipe’s recommended position.\n• Use an oven thermometer to check whether the oven runs hot.\n• If the top browns too quickly, loosely tent with foil when appropriate and continue baking until safely done.\n• Use the pan size listed in the recipe; a different size changes baking time and depth.'},
 dense:{title:'🥮 Dense or tough texture',text:'• For cakes and quick breads, mix only until the ingredients are just combined after adding flour.\n• Check that the correct amount of leavener was used and that it is still active.\n• Measure flour carefully to avoid adding too much.\n• For yeast bread, allow enough time for proofing and check that the dough was not too dry.\nThe best fix depends on whether it was a cake, muffin, quick bread, or yeast bread.'}
 ,
 hardcookies:{title:'🍪 Hard or burnt cookies',text:'• Check the oven temperature with an oven thermometer if cookies brown too fast.\n• Begin checking a little before the recipe’s bake time ends; cookies firm as they cool.\n• Measure flour carefully and avoid baking longer than needed.\nNext time: bake a small test batch and note the exact timing.'},
 nocookie:{title:'🍪 Cookies barely spread',text:'• Check whether the dough was very cold; let it sit briefly if the recipe allows.\n• Make sure you measured flour accurately and did not add too much.\n• Confirm the recipe calls for softened or melted butter and used the correct kind.\nCookie recipes vary, so change only one factor at a time.'},
 sinkcake:{title:'🎂 Cake sank in the middle',text:'• Avoid opening the oven early; the structure may not have set yet.\n• Check that the leavener is fresh and measured correctly.\n• Confirm the oven was preheated and the pan size matches the recipe.\n• Test the center for doneness before removing the cake.'},
 stuckcake:{title:'🎂 Cake stuck to the pan',text:'• Follow the recipe’s pan-prep instructions: grease, flour, or line as directed.\n• Let the cake cool for the recommended time before turning it out.\n• Run a thin spatula gently around the edge if appropriate; do not force a fragile warm cake.\nFor next time, parchment on the bottom can help when the recipe permits.'},
 cupcakes:{title:'🧁 Cupcakes overflowed or baked unevenly',text:'• Fill liners only to the level recommended by the recipe, often about two-thirds full.\n• Make sure the oven rack is centered and the oven is fully preheated.\n• Use one consistent scoop so portions bake evenly.\n• Check that the muffin pan is not crowded or filled unevenly.'},
 gummybread:{title:'🍞 Bread is gummy inside',text:'• Bread may need more baking time; use the recipe’s doneness cues and an appropriate internal-temperature check.\n• Let the loaf cool before slicing so the crumb can set.\n• Check that liquid and flour were measured accurately.\nA gummy center can have several causes, so avoid adding extra flour without checking the recipe.'},
 doughrise:{title:'🍞 Yeast dough will not rise',text:'• Check that the yeast is in date and was stored as directed.\n• Liquid that is too hot can damage yeast; follow the recipe’s temperature guidance.\n• Give dough enough time in a comfortably warm, draft-free place; colder rooms slow rising.\n• Salt should be measured accurately and mixed as the recipe directs.'},
 piecrust:{title:'🥧 Pie crust shrank or cracked',text:'• Avoid stretching dough to fit the pan; stretched dough can shrink as it bakes.\n• Chill the dough as directed and let it relax if it keeps springing back.\n• If it cracks while rolling, let it warm slightly and patch small cracks with scraps.\n• Handle pastry gently to help keep it tender.'},
 soggypie:{title:'🥧 Soggy pie crust',text:'• Follow the recipe’s instructions for blind-baking or venting the crust.\n• Avoid adding filling while the crust is warm unless the recipe says to.\n• Very juicy fillings may need the thickener and prep method specified by the recipe.\n• Bake until the crust is properly browned, not just until the filling bubbles.'},
 chocolate:{title:'🍫 Chocolate seized or turned grainy',text:'• Keep water and steam away from melting chocolate; even a little moisture can make it seize.\n• Use gentle, low heat and stir frequently.\n• If it has seized, it may not return to a dipping texture; depending on the recipe, adding hot liquid gradually can turn it into a sauce or ganache.\nUse a dry bowl and utensils next time.'},
 'stiff frosting':{title:'🍥 Frosting is too stiff or grainy',text:'• For buttercream, add a tiny amount of milk or cream at a time until it reaches the needed consistency.\n• If grainy, check whether sugar dissolved or whether the butter/cream cheese was at the right temperature for that recipe.\n• Beat only as long as the recipe recommends.\nDifferent frosting styles need different fixes; avoid adding liquid all at once.'},
 lumpy:{title:'🥞 Lumpy batter',text:'• For muffins, pancakes, and quick breads, small lumps are often fine—overmixing can make them tough.\n• For a smoother cake batter, add ingredients in the order the recipe gives and scrape the bowl.\n• Sift dry ingredients when the recipe calls for it.\nDo not keep beating a quick-bread batter just to remove every lump.'},
 pan:{title:'📏 Changing pan size',text:'• A wider pan makes batter shallower and may bake faster; a smaller/deeper pan may need longer.\n• Do not fill a pan more than the recipe’s guidance allows.\n• Keep an eye on doneness and use the recipe’s visual or internal cues.\nFor best results, tell me the original pan and the one you have so we can compare them.'},
 substitute:{title:'🥚 Missing an ingredient',text:'• First identify the ingredient and its job: moisture, fat, structure, sweetness, acidity, or leavening.\n• Baking swaps can change texture and rise, so avoid assuming every ingredient has a 1:1 substitute.\n• Use a substitution tested for that specific recipe when possible.\nSearch the Baking Corner’s Ingredient Swap Guide for a more targeted option.'}
};
document.getElementById('bakingRescueButton').addEventListener('click',()=>{
 if(activeRoom!=='baking')return;
 const advice=bakingRescueAdvice[document.getElementById('bakingRescueProblem').value];
 const result=document.getElementById('bakingRescueResult');
 result.textContent=advice.title+'\n'+advice.text;
});

const gardenDocument = "\u003c!doctype html>\n\u003chtml lang=\"en\">\n\u003chead>\n\u003cmeta charset=\"utf-8\">\u003cmeta name=\"viewport\" content=\"width=device-width,initial-scale=1\">\n\u003ctitle>Lil Dino's Herb Garden\u003c/title>\n\u003cstyle>\n@import url('https://fonts.googleapis.com/css2?family=Caveat:wght@400;500;600;700&display=swap');\n:root{--cream:#fff8ed;--paper:#fffdf8;--sage:#dce8d7;--green:#55745b;--pink:#f3c9d5;--ink:#344239;--muted:#68766d;--line:#e4e8dc}\n*{box-sizing:border-box}body{margin:0;background:var(--cream);color:var(--ink);font-family:\"Caveat\",\"Segoe Print\",\"Bradley Hand\",cursive;line-height:1.45;font-size:20px}button,input{font:inherit}button{cursor:pointer}.wrap{max-width:960px;margin:auto;padding:14px}.hero{background:linear-gradient(130deg,#e8f0e1,#fff2f4);border:1px solid var(--line);border-radius:22px;padding:22px;display:grid;grid-template-columns:1fr auto;gap:10px;align-items:center}.kicker{font-size:1rem;font-weight:800;letter-spacing:.12em;text-transform:uppercase;color:var(--green)}h1{font-size:clamp(1.8rem,5vw,3rem);line-height:1.1;margin:8px 0;color:#385342}.hero p{margin:0;color:#526357}.mascot{font-size:clamp(4rem,10vw,6rem)}.chip{display:inline-block;font-size:1rem;background:#ffffffc9;border:1px solid var(--line);border-radius:999px;padding:5px 9px;font-size:.82rem;margin:10px 4px 0 0}.nav{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:8px;margin:14px 0}.nav button{border:1px solid var(--line);border-radius:13px;background:var(--paper);padding:11px 6px;color:var(--ink);font-weight:750}.nav button[aria-selected=true]{background:var(--sage);border-color:#b7cdb4;color:#35543b}.ico{display:block;font-size:1.35rem}.panel{background:var(--paper);border:1px solid var(--line);border-radius:18px;padding:17px}.panel h2{margin:0;color:#3d5945}.sub{color:var(--muted);margin:3px 0 14px}.searchrow{display:flex;gap:8px;margin:12px 0}.searchrow input{flex:1;min-width:0;border:1px solid #ccd8c9;background:white;border-radius:11px;padding:12px;color:var(--ink)}.searchrow button{border:0;border-radius:11px;background:var(--green);color:white;font-weight:800;padding:12px 15px}.examples{display:flex;flex-wrap:wrap;gap:7px;margin:0 0 14px}.examples button{background:#f9f1e7;border:1px solid #eadfce;border-radius:999px;padding:7px 10px;color:#5c6258}.results{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px}.card{background:white;border:1px solid var(--line);border-radius:14px;padding:13px}.card h3{margin:0 0 5px;color:#3e5b45}.card p{margin:5px 0;color:#56645a}.tag{display:inline-block;font-size:.95rem;background:#f7e4ea;color:#874b60;border-radius:999px;padding:3px 8px;font-size:.75rem;font-weight:800}.empty{padding:14px;border:1px dashed #ccd8c9;border-radius:12px;color:var(--muted);grid-column:1/-1}.note{border-left:4px solid var(--pink);background:#fff4f6;padding:10px 12px;border-radius:0 10px 10px 0;margin-top:12px;color:#6e4e59}.footer{text-align:center;color:var(--muted);font-size:1rem;padding:18px}.hidden{display:none!important}button:focus-visible,input:focus-visible{outline:3px solid #d58ca4;outline-offset:2px}@media(max-width:620px){.wrap{padding:10px}.hero{padding:16px}.nav{grid-template-columns:repeat(2,minmax(0,1fr))}.results{grid-template-columns:1fr}.panel{padding:13px}.searchrow{flex-direction:column}.searchrow button{width:100%}}\n\u003c/style>\u003c/head>\n\u003cbody>\u003cmain class=\"wrap\">\n\u003cheader class=\"hero\">\u003cdiv>\u003cdiv class=\"kicker\">Little Dino's Kitchen Adventures\u003c/div>\u003ch1>\ud83c\udf3f The Herb Garden\u003c/h1>\u003cp>Find flavors that fit your food, discover useful swaps, and keep fresh herbs at their best.\u003c/p>\u003cspan class=\"chip\">\ud83c\udf43 Practical kitchen tips\u003c/span>\u003cspan class=\"chip\">\ud83e\udd44 Flavor ideas\u003c/span>\u003c/div>\u003cdiv class=\"mascot\" role=\"img\" aria-label=\"Lil Dino\">\ud83d\udc07\ud83c\udf3f\u003c/div>\u003c/header>\n\u003cnav class=\"nav\" aria-label=\"Herb Garden tools\" role=\"tablist\">\u003cbutton role=\"tab\" aria-selected=\"true\" data-tab=\"guide\">\u003cspan class=\"ico\">\ud83c\udf31\u003c/span>Herb Guide\u003c/button>\u003cbutton role=\"tab\" aria-selected=\"false\" data-tab=\"matcher\">\u003cspan class=\"ico\">\ud83c\udf7d\ufe0f\u003c/span>Flavor Matcher\u003c/button>\u003cbutton role=\"tab\" aria-selected=\"false\" data-tab=\"swaps\">\u003cspan class=\"ico\">\ud83d\udd04\u003c/span>Herb Swaps\u003c/button>\u003cbutton role=\"tab\" aria-selected=\"false\" data-tab=\"storage\">\u003cspan class=\"ico\">\u2744\ufe0f\u003c/span>Fresh Storage\u003c/button>\u003c/nav>\n\u003csection class=\"panel\" id=\"panel-guide\" role=\"tabpanel\">\u003ch2>Herb & Seasoning Guide\u003c/h2>\u003cp class=\"sub\">Search an herb or spice to learn its flavor and best uses.\u003c/p>\u003cform class=\"searchrow\" id=\"guide-form\">\u003cinput id=\"guide-search\" aria-label=\"Search herbs\" placeholder=\"Try basil, rosemary, thyme, cumin\u2026\" autocomplete=\"off\">\u003cbutton>Find herb\u003c/button>\u003c/form>\u003cdiv class=\"examples\" data-fill=\"guide-search\">\u003cbutton type=\"button\">Basil\u003c/button>\u003cbutton type=\"button\">Rosemary\u003c/button>\u003cbutton type=\"button\">Thyme\u003c/button>\u003cbutton type=\"button\">Cumin\u003c/button>\u003cbutton type=\"button\">Paprika\u003c/button>\u003cbutton type=\"button\">Mint\u003c/button>\u003c/div>\u003cdiv class=\"results\" id=\"guide-results\" aria-live=\"polite\">\u003c/div>\u003c/section>\n\u003csection class=\"panel hidden\" id=\"panel-matcher\" role=\"tabpanel\">\u003ch2>Flavor Matcher\u003c/h2>\u003cp class=\"sub\">Enter a food or dish to find herbs and seasonings that pair well.\u003c/p>\u003cform class=\"searchrow\" id=\"match-form\">\u003cinput id=\"match-search\" aria-label=\"Food to match\" placeholder=\"Try chicken, potatoes, pasta, strawberries\u2026\" autocomplete=\"off\">\u003cbutton>Match flavors\u003c/button>\u003c/form>\u003cdiv class=\"examples\" data-fill=\"match-search\">\u003cbutton type=\"button\">Chicken\u003c/button>\u003cbutton type=\"button\">Potatoes\u003c/button>\u003cbutton type=\"button\">Pasta\u003c/button>\u003cbutton type=\"button\">Eggs\u003c/button>\u003cbutton type=\"button\">Mushrooms\u003c/button>\u003cbutton type=\"button\">Strawberries\u003c/button>\u003c/div>\u003cdiv class=\"results\" id=\"match-results\" aria-live=\"polite\">\u003c/div>\u003c/section>\n\u003csection class=\"panel hidden\" id=\"panel-swaps\" role=\"tabpanel\">\u003ch2>Herb Substitutions\u003c/h2>\u003cp class=\"sub\">Search an herb you\u2019re missing. Substitutes taste different, so start with less and adjust.\u003c/p>\u003cform class=\"searchrow\" id=\"swap-form\">\u003cinput id=\"swap-search\" aria-label=\"Herb to substitute\" placeholder=\"Try basil, oregano, thyme\u2026\" autocomplete=\"off\">\u003cbutton>Find a swap\u003c/button>\u003c/form>\u003cdiv class=\"examples\" data-fill=\"swap-search\">\u003cbutton type=\"button\">Basil\u003c/button>\u003cbutton type=\"button\">Oregano\u003c/button>\u003cbutton type=\"button\">Thyme\u003c/button>\u003cbutton type=\"button\">Cilantro\u003c/button>\u003cbutton type=\"button\">Rosemary\u003c/button>\u003cbutton type=\"button\">Dill\u003c/button>\u003c/div>\u003cdiv class=\"results\" id=\"swap-results\" aria-live=\"polite\">\u003c/div>\u003c/section>\n\u003csection class=\"panel hidden\" id=\"panel-storage\" role=\"tabpanel\">\u003ch2>Keep Fresh Herbs Fresh\u003c/h2>\u003cp class=\"sub\">Search a fresh herb for practical storage guidance.\u003c/p>\u003cform class=\"searchrow\" id=\"storage-form\">\u003cinput id=\"storage-search\" aria-label=\"Fresh herb to store\" placeholder=\"Try parsley, cilantro, basil, mint\u2026\" autocomplete=\"off\">\u003cbutton>Storage tip\u003c/button>\u003c/form>\u003cdiv class=\"examples\" data-fill=\"storage-search\">\u003cbutton type=\"button\">Parsley\u003c/button>\u003cbutton type=\"button\">Cilantro\u003c/button>\u003cbutton type=\"button\">Basil\u003c/button>\u003cbutton type=\"button\">Mint\u003c/button>\u003cbutton type=\"button\">Rosemary\u003c/button>\u003cbutton type=\"button\">Thyme\u003c/button>\u003c/div>\u003cdiv class=\"results\" id=\"storage-results\" aria-live=\"polite\">\u003c/div>\u003cdiv class=\"note\">Discard herbs that are slimy, moldy, or smell unpleasant. Wash under running water before use; dry well for better storage.\u003c/div>\u003c/section>\n\n\u003cdiv class=\"footer\">A little flavor wisdom from Juniper Vale \ud83c\udf3f \ud83d\udc07 \u00b7 Cooking tips, not a growing guide.\u003c/div>\u003c/main>\n\u003cscript>\n(function(){\nconst herbs={\nbasil:[\"Basil\",\"Sweet, fresh, peppery, with a gentle anise note.\",\"Tomatoes, pasta, pesto, eggs, beans, and strawberries.\",\"Add delicate fresh basil near the end.\"],\nrosemary:[\"Rosemary\",\"Piney, woody, and strongly aromatic.\",\"Roasted potatoes, chicken, lamb, beans, and hearty breads.\",\"Use a small amount; it can quickly dominate.\"],\nthyme:[\"Thyme\",\"Earthy, lightly minty, and subtle.\",\"Chicken, mushrooms, soups, beans, and roasted vegetables.\",\"Add a small pinch early in cooking.\"],\nparsley:[\"Parsley\",\"Clean, grassy, and gently peppery.\",\"Potatoes, eggs, fish, salads, sauces, and fresh garnishes.\",\"Chop and add near the end.\"],\noregano:[\"Oregano\",\"Peppery, earthy, and robust.\",\"Tomato sauces, pizza, roasted vegetables, beans, and Greek-style dishes.\",\"Dried oregano is concentrated; start with less.\"],\nmint:[\"Mint\",\"Cool, sweet, and refreshing.\",\"Tea, peas, yogurt sauces, fruit salads, lamb, and chocolate.\",\"Add near the end to preserve its fresh aroma.\"],\ncilantro:[\"Cilantro\",\"Bright, citrusy, and green; some people perceive it as soapy.\",\"Salsa, tacos, curries, beans, rice, and lime-forward dishes.\",\"Add leaves near the end; tender stems are flavorful too.\"],\ndill:[\"Dill\",\"Fresh, grassy, lightly anise-like.\",\"Cucumbers, potatoes, eggs, fish, yogurt sauces, and pickles.\",\"Fresh dill is delicate; stir it in near the end.\"],\nchives:[\"Chives\",\"Mild, fresh onion flavor.\",\"Eggs, potatoes, soups, cream cheese, and salads.\",\"Snip finely and sprinkle on at the end.\"],\nsage:[\"Sage\",\"Earthy, savory, and slightly peppery.\",\"Poultry, squash, beans, browned butter, and hearty sauces.\",\"Use sparingly; sage can become dominant.\"],\ncumin:[\"Cumin\",\"Warm, earthy, nutty, and slightly smoky.\",\"Beans, lentils, chili, tacos, roasted carrots, and spice rubs.\",\"Start with a small pinch and adjust to taste.\"],\npaprika:[\"Paprika\",\"Mildly sweet and peppery; smoked paprika adds smoky depth.\",\"Eggs, potatoes, chicken, soups, beans, and roasted vegetables.\",\"Check whether your paprika is sweet, smoked, or hot.\"],\nsalt:[\"Salt\",\"Enhances flavor and balances bitterness; different salts vary in texture.\",\"Nearly all savory dishes, baking, vegetables, meat, rice, and soups.\",\"Add gradually and taste as you go; salty sauces and seasoning blends already contain salt.\"],\nblackpepper:[\"Black pepper\",\"Warm, sharp, woody heat.\",\"Eggs, steak, chicken, vegetables, soups, pasta, and sauces.\",\"Freshly ground pepper gives a brighter aroma.\"],\nlemonpepper:[\"Lemon pepper\",\"Citrusy, peppery, and savory; many blends contain salt.\",\"Chicken, fish, potatoes, broccoli, noodles, and roasted vegetables.\",\"Check the label for salt before adding more.\"],\ngarlicpowder:[\"Garlic powder\",\"Savory, mellow garlic flavor.\",\"Meat, vegetables, soups, sauces, potatoes, marinades, and rubs.\",\"Use less than fresh garlic at first; it distributes evenly in dry rubs.\"],\nonionpowder:[\"Onion powder\",\"Sweet, savory onion flavor without texture.\",\"Burgers, meatloaf, soups, sauces, dips, vegetables, and spice blends.\",\"Great in dry rubs; start with a small amount.\"],\nchilipowder:[\"Chili powder\",\"Warm, earthy, and mildly to moderately spicy depending on the blend.\",\"Chili, tacos, beans, roasted vegetables, chicken, and stews.\",\"Blend contents vary; taste before adding extra heat.\"],\ncinnamon:[\"Cinnamon\",\"Sweet, woody warmth.\",\"Oatmeal, baked goods, apples, some curries, tagines, and warm drinks.\",\"A little goes a long way in savory dishes.\"],\nturmeric:[\"Turmeric\",\"Earthy, gently bitter, warm, and golden.\",\"Dals, curries, rice, soups, tofu, and roasted vegetables.\",\"Pair with other spices; use modestly because it can taste bitter in excess.\"],\nginger:[\"Ginger\",\"Fresh ginger is bright and zesty; dried ginger is warmer.\",\"Stir-fries, noodles, soups, marinades, baked goods, and tea.\",\"Fresh and ground ginger are not exact substitutes; adjust to taste.\"],\ngarammasala:[\"Garam masala\",\"A warm Indian spice blend that may include cumin, coriander, cardamom, cinnamon, cloves, and pepper.\",\"Curries, lentils, roasted vegetables, chicken, and chickpeas.\",\"Recipes vary by blend; often add toward the end for aroma.\"],\ncoriander:[\"Coriander\",\"Citrusy, floral, and lightly nutty.\",\"Indian curries, beans, roasted carrots, fish, marinades, and pickles.\",\"Ground coriander tastes different from fresh cilantro leaves.\"],\ncardamom:[\"Cardamom\",\"Fragrant, citrusy, sweet, and herbal.\",\"Chai, rice puddings, baked goods, pilafs, and some curries.\",\"Use sparingly; it is potent.\"],\nfive_spice:[\"Chinese five-spice\",\"Sweet, warm, aromatic, and often licorice-like; blends commonly include star anise, fennel, cinnamon, cloves, and Sichuan pepper.\",\"Roasted pork, duck, tofu, mushrooms, stir-fries, and marinades.\",\"Use a small pinch first; blend ingredients vary.\"],\nsichuan_pepper:[\"Sichuan pepper\",\"Citrusy and tingling rather than simply hot.\",\"Mapo tofu, chili oil, noodles, stir-fries, and Sichuan-style dishes.\",\"Use lightly; its numbing tingle is distinctive.\"],\nwhitepepper:[\"White pepper\",\"Earthy, sharper, and less fruity than black pepper.\",\"Chinese soups, congee, fried rice, creamy sauces, and marinades.\",\"Add gradually; its flavor can become strong.\"],\nsesame_seeds:[\"Sesame seeds\",\"Toasty, nutty flavor.\",\"Rice bowls, noodles, salads, tofu, vegetables, and breads.\",\"Toast briefly in a dry pan to deepen flavor; watch closely.\"],\nnori:[\"Nori\",\"Briny, savory seaweed flavor.\",\"Rice, sushi, noodles, eggs, popcorn, and soups.\",\"Keep dry and airtight so it stays crisp.\"],\nfurikake:[\"Furikake\",\"Japanese rice seasoning, often containing sesame, seaweed, salt, and other ingredients.\",\"Rice, noodles, eggs, popcorn, roasted vegetables, and avocado.\",\"Check the label for fish, sesame, soy, or other allergens.\"],\nmiso:[\"Miso\",\"Salty, deeply savory fermented soybean paste; flavor varies by type.\",\"Soups, glazes, dressings, marinades, noodles, and vegetables.\",\"Dissolve into a little warm liquid; avoid boiling hard if you want to preserve delicate aroma.\"],\ngochugaru:[\"Gochugaru\",\"Korean red pepper flakes with fruity, smoky, mild-to-hot heat depending on type.\",\"Kimchi, stews, noodles, marinades, rice bowls, and dipping sauces.\",\"Heat levels vary; start small.\"],\ncurry_powder:[\"Curry powder\",\"A blend that may include turmeric, coriander, cumin, fenugreek, and other spices.\",\"Soups, lentils, chicken, chickpeas, rice, and roasted vegetables.\",\"There is no single standard blend, so taste and adjust.\"],\nfive_spice_powder:[\"Five-spice powder\",\"Warm, sweet, aromatic Chinese spice blend.\",\"Pork, duck, tofu, mushrooms, stir-fries, and marinades.\",\"Use a small pinch first; it can dominate quickly.\"],\nsoy_sauce:[\"Soy sauce\",\"Salty, savory umami flavor.\",\"Stir-fries, noodles, rice, marinades, soups, and dipping sauces.\",\"Use less added salt when cooking with it; choose tamari or a labeled alternative if needed.\"],\nrice_vinegar:[\"Rice vinegar\",\"Mild, clean acidity.\",\"Sushi rice, quick pickles, dipping sauces, slaws, and stir-fries.\",\"Season gradually; seasoned rice vinegar may already contain sugar and salt.\"],\n\"lemongrass\":[\"Lemongrass\", \"Bright citrus aroma with a gentle herbal edge.\", \"Thai-style soups, curries, marinades, stir-fries, and teas.\", \"Bruise or finely mince the tender inner part; remove tough outer layers if needed.\"],\n\"lemon pepper\":[\"Lemon pepper\", \"Citrusy, peppery, and savory; many blends contain salt.\", \"Chicken, fish, potatoes, broccoli, noodles, and roasted vegetables.\", \"Check the label before adding salt because many blends are already salted.\"],\n\"black pepper\":[\"Black pepper\", \"Warm, sharp, woody heat.\", \"Eggs, steak, chicken, vegetables, soups, pasta, and sauces.\", \"Freshly ground pepper gives a brighter aroma.\"],\n\"garlic powder\":[\"Garlic powder\", \"Savory, mellow garlic flavor.\", \"Meat, vegetables, soups, sauces, potatoes, marinades, and rubs.\", \"Start with a little; it distributes evenly in dry rubs.\"],\n\"onion powder\":[\"Onion powder\", \"Sweet, savory onion flavor without texture.\", \"Burgers, meatloaf, soups, sauces, dips, vegetables, and spice blends.\", \"Great in dry rubs; start with a small amount.\"],\n\"smoked paprika\":[\"Smoked paprika\", \"Deep smoky pepper flavor with mild sweetness.\", \"Potatoes, beans, eggs, chicken, soups, tofu, and roasted vegetables.\", \"Choose sweet, hot, or smoked style to suit the dish.\"],\n\"star anise\":[\"Star anise\", \"Strong, sweet licorice-like aroma.\", \"Broths, braises, pho-style soups, poached fruit, and Chinese five-spice blends.\", \"Use sparingly and remove whole pieces before serving.\"],\n\"curry leaves\":[\"Curry leaves\", \"Fresh, citrusy, nutty aroma used in South Asian cooking.\", \"Dals, curries, lentils, coconut dishes, and rice.\", \"Often briefly sizzle in oil to release aroma; not the same as curry powder.\"],\n\"sumac\":[\"Sumac\", \"Tangy, lemony, fruity acidity.\", \"Roasted vegetables, salads, chicken, hummus, rice, and grilled foods.\", \"Sprinkle near the end for a bright finish.\"],\n\"five spice\":[\"Chinese five-spice\", \"A warm, aromatic blend often containing star anise, fennel, cinnamon, cloves, and Sichuan pepper.\", \"Pork, tofu, roasted vegetables, marinades, and braises.\", \"Use sparingly; blends vary by brand.\"],\n};\nconst pairs={\nchicken:[\"Thyme \u00b7 Rosemary \u00b7 Sage \u00b7 Parsley \u00b7 Paprika \u00b7 Garlic\",\"Rosemary and thyme are great for roasting. Add parsley or lemon for a brighter finish.\"],\npotato:[\"Rosemary \u00b7 Thyme \u00b7 Chives \u00b7 Paprika \u00b7 Dill \u00b7 Garlic\",\"Rosemary and thyme suit roasting; chives or dill are great on boiled potatoes or potato salad.\"],\npasta:[\"Basil \u00b7 Oregano \u00b7 Parsley \u00b7 Thyme \u00b7 Garlic\",\"Basil and oregano suit tomato sauces. Parsley brightens creamy or garlic-based pasta.\"],\negg:[\"Chives \u00b7 Parsley \u00b7 Dill \u00b7 Paprika \u00b7 Basil\",\"Chives give a gentle onion note; dill works well in egg salad.\"],\nmushroom:[\"Thyme \u00b7 Parsley \u00b7 Rosemary \u00b7 Sage \u00b7 Garlic\",\"Thyme and garlic are especially good with saut\u00e9ed mushrooms; add parsley at the end.\"],\nstrawber:[\"Mint \u00b7 Basil \u00b7 Cinnamon\",\"Mint is refreshing with berries; a little basil adds an aromatic twist.\"],\nfish:[\"Dill \u00b7 Parsley \u00b7 Thyme \u00b7 Paprika\",\"Dill and parsley pair well with lemon and fish.\"],\nbean:[\"Cumin \u00b7 Oregano \u00b7 Thyme \u00b7 Sage \u00b7 Paprika\",\"Cumin adds warmth, oregano gives a robust herbal note, and thyme suits soups.\"],\ncarrot:[\"Thyme \u00b7 Rosemary \u00b7 Cumin \u00b7 Parsley \u00b7 Cinnamon\",\"Thyme is an easy savory choice; cumin brings warmth.\"],\ntomato:[\"Basil \u00b7 Oregano \u00b7 Thyme \u00b7 Parsley\",\"Basil is classic with fresh tomatoes; oregano and thyme work in cooked sauces.\"],\nrice:[\"Ginger \u00b7 Garlic \u00b7 White pepper \u00b7 Sesame \u00b7 Furikake \u00b7 Scallions\",\"Try ginger and garlic for fried rice, or furikake and sesame for a quick Japanese-inspired rice bowl.\"],\nnoodles:[\"Garlic \u00b7 Ginger \u00b7 Sesame \u00b7 White pepper \u00b7 Chili flakes \u00b7 Sichuan pepper\",\"Ginger and garlic are a flexible base; sesame and chili add aroma and heat.\"],\ntofu:[\"Ginger \u00b7 Garlic \u00b7 Soy sauce \u00b7 Five-spice \u00b7 Gochugaru \u00b7 Sesame\",\"Press tofu if your recipe calls for it, then season with a savory marinade or a little gochugaru.\"],\n\"stir fry\":[\"Ginger \u00b7 Garlic \u00b7 Soy sauce \u00b7 Sesame \u00b7 White pepper \u00b7 Chili flakes\",\"Cook aromatics briefly, then add sauce; sesame oil is usually best as a finishing flavor.\"],\ndumplings:[\"Ginger \u00b7 Garlic \u00b7 White pepper \u00b7 Scallions \u00b7 Sesame\",\"Ginger and scallions brighten fillings; use sesame and soy sauce in a dipping sauce.\"],\ncurry:[\"Cumin \u00b7 Coriander \u00b7 Turmeric \u00b7 Ginger \u00b7 Garam masala \u00b7 Chili\",\"Toast ground spices briefly in oil without scorching, then add aromatics and the other ingredients.\"],\nlentil:[\"Cumin \u00b7 Coriander \u00b7 Turmeric \u00b7 Garam masala \u00b7 Paprika\",\"These warm spices work well in lentils and dal; finish with lemon or fresh herbs if desired.\"],\nsalmon:[\"Dill \u00b7 Lemon pepper \u00b7 Ginger \u00b7 Soy sauce \u00b7 Sesame\",\"Use dill and lemon pepper for a familiar flavor, or ginger and soy for an Asian-inspired glaze.\"],\nbeef:[\"Black pepper \u00b7 Garlic powder \u00b7 Paprika \u00b7 Ginger \u00b7 Soy sauce \u00b7 Five-spice\",\"For a classic rub use pepper, garlic, and paprika; for stir-fry use ginger and a little soy sauce.\"],\npork:[\"Five-spice \u00b7 Ginger \u00b7 Garlic \u00b7 Black pepper \u00b7 Paprika\",\"Five-spice pairs well with pork; use a light hand and balance with acidity if needed.\"],\nbroccoli:[\"Garlic \u00b7 Lemon pepper \u00b7 Sesame \u00b7 Ginger \u00b7 Chili flakes\",\"Roast with garlic and lemon pepper, or finish stir-fried broccoli with ginger and sesame.\"],\n\"ground beef\":[\"Black pepper \u00b7 Garlic \u00b7 Onion powder \u00b7 Paprika \u00b7 Cumin \u00b7 Chili powder\", \"Use garlic, onion, and pepper as a simple base; cumin and chili powder give it a taco-style direction.\"],\n\"dragon fruit\":[\"Mint \u00b7 Lime zest \u00b7 Ginger (very lightly)\", \"Dragon fruit is delicate; fresh mint and a little lime usually complement it without overpowering it.\"],\n\"strawberries\":[\"Mint \u00b7 Basil \u00b7 Black pepper (tiny pinch) \u00b7 Cinnamon\", \"Mint or basil adds freshness; use pepper sparingly for a subtle contrast.\"],\n};\nconst swaps={\nbasil:\"Oregano (stronger and earthier); marjoram (milder and sweet); parsley with a pinch of oregano (fresh but different).\",\noregano:\"Marjoram (milder); thyme (earthier); Italian seasoning (check the blend ingredients).\",\nthyme:\"Marjoram (milder); oregano (stronger, use less); poultry seasoning for soups or roasts (blend varies).\",\ncilantro:\"Flat-leaf parsley with a little lime zest; mint in some salads or chutneys; or simply leave it out.\",\nrosemary:\"Thyme (less piney); sage (earthy and strong, use sparingly); Italian seasoning for general savory dishes.\",\ndill:\"Tarragon (slightly anise-like); parsley with lemon zest (brighter); chives for a mild fresh finish.\",\nparsley:\"Chives for a gentle onion note; cilantro for a citrusy flavor if you like it; a little celery leaf.\",\nmint:\"Lemon zest for freshness; a little basil in some fruit dishes; or leave it out.\",\nsalt:\"If reducing salt, boost flavor with lemon juice, vinegar, garlic, onion, herbs, or salt-free spices. Salt substitutes containing potassium are not suitable for everyone.\",\nblackpepper:\"White pepper for a different, earthier heat; a small pinch of chili flakes for more heat; or omit it.\",\nlemonpepper:\"Use lemon zest plus black pepper. Check whether the recipe also needs salt, since many lemon-pepper blends are salted.\",\ngarlicpowder:\"Use fresh minced garlic (roughly 1 small clove for 1/8 teaspoon powder as a starting point), or granulated garlic.\",\nonionpowder:\"Use finely minced fresh onion or shallot; adjust moisture and cook time as needed.\",\ncumin:\"Coriander is lighter and more citrusy; chili powder can work in some Mexican-style dishes but varies by blend.\",\nturmeric:\"A little curry powder can work in some recipes, but it changes the flavor and may contain several spices.\",\nginger:\"Ground ginger can replace fresh ginger in many cooked dishes, using much less; it tastes warmer and less bright.\",\ngarammasala:\"Use a small amount of curry powder or a mix of cumin, coriander, and cinnamon if appropriate; the flavor will differ.\",\ncoriander:\"A little cumin plus citrus zest can provide warmth and brightness, but is not an exact match.\",\nfive_spice:\"Try a tiny pinch of cinnamon with fennel or star anise if available; use sparingly.\",\nsichuan_pepper:\"Black pepper plus a little citrus zest gives some brightness but not the signature tingling effect.\",\nwhitepepper:\"Black pepper is the easiest substitute, though it has a fruitier aroma and visible specks.\",\ngochugaru:\"Use paprika for color and mildness, or a small amount of chili flakes for more heat; flavor will differ.\",\ncurry_powder:\"Combine cumin, coriander, turmeric, and a little ginger if available; exact blend depends on the recipe.\",\nsoy_sauce:\"Tamari is often similar; coconut aminos are usually sweeter and less salty. Check labels for allergens and sodium.\",\nrice_vinegar:\"Use mild apple cider vinegar or white wine vinegar diluted slightly with water; add a little sugar only if the recipe needs it.\",\n\"lemongrass\":\"Use a little lemon or lime zest plus fresh ginger. It will be brighter and less floral than lemongrass.\",\n\"lemon pepper\":\"Mix black pepper with lemon zest; add salt only if needed. Dried lemon zest can also help.\",\n\"five spice\":\"A small pinch of cinnamon plus a little fennel and star anise if available; it will not be an exact blend.\",\n\"paprika\":\"For color and mild flavor, use a little ground ancho or mild chili powder; smoked paprika needs a smoky alternative.\",\n\"black pepper\":\"White pepper can work in sauces and soups, though its flavor is different.\",\n};\nconst storage={\nbasil:\"Keep like a small bouquet with stems in a jar of water at room temperature, away from direct sun. Avoid a cold fridge, which can blacken basil leaves.\",\nparsley:\"Trim stem ends and stand in a jar with a little water in the refrigerator; loosely cover the leaves. Change water when cloudy.\",\ncilantro:\"Trim stems and stand in a jar with a little water in the refrigerator; loosely cover. Refresh the water and remove yellowing leaves.\",\nmint:\"Trim stems and keep in a small jar of water in the refrigerator, loosely covered. Remove damaged leaves and refresh the water.\",\nrosemary:\"Wrap unwashed sprigs in a barely damp paper towel, place in a loosely closed bag or container, and refrigerate.\",\nthyme:\"Refrigerate sprigs in a container or bag lined with a dry or barely damp paper towel. Wash just before use.\",\ndill:\"Trim stems and stand in a little water in the refrigerator, loosely covered. Use promptly.\",\nchives:\"Wrap loosely in a barely damp towel or place in a container in the refrigerator.\",\ncilantro:\"Trim stems and stand in a jar with a little water in the refrigerator, loosely covered. Refresh the water and remove yellowing leaves.\",\nsage:\"Wrap unwashed leaves in a barely damp paper towel, place in a container or bag, and refrigerate.\",\noregano:\"Wrap sprigs in a barely damp paper towel and refrigerate in a loosely closed bag or container.\",\ncoriander:\"Fresh cilantro leaves are delicate: store stems in a jar with a little water in the refrigerator, loosely covered.\",\nginger:\"Store fresh ginger unpeeled in a dry, sealed container in the refrigerator; freeze extra ginger for longer storage.\",\nlemongrass:\"Wrap fresh stalks and refrigerate in a sealed bag; freeze trimmed stalks if you will not use them soon.\",\nscallions:\"Stand roots in a little water in the refrigerator or wrap loosely and store in a bag; change water regularly if using a jar.\",\n\"green onion\":\"Stand roots in a little water in the refrigerator or wrap loosely and store in a bag; change water regularly if using a jar.\",\n\"basil thai\":\"Thai basil is delicate; keep stems in a jar of water at room temperature, away from direct sunlight.\",\nchili:\"Fresh chilies keep in a dry paper towel-lined container or bag in the refrigerator; discard if slimy or moldy.\",\n\"lemon pepper\":\"Keep the seasoning tightly sealed in a cool, dry cupboard, away from heat and moisture.\",\n};\nconst esc=s=>String(s).replace(/[&\u003c>\"]/g,c=>({\"&\":\"&amp;\",\"\u003c\":\"&lt;\",\">\":\"&gt;\",'\"':\"&quot;\"}[c]));\nconst card=(title,body,tag)=>`\u003carticle class=\"card\">\u003ch3>${esc(title)}\u003c/h3>\u003cp>${body}\u003c/p>\u003cspan class=\"tag\">${esc(tag)}\u003c/span>\u003c/article>`;\nconst empty=q=>`\u003cdiv class=\"empty\">Juniper checked the shelves but couldn't find a confident match for \u201c${esc(q)}.\u201d Try a common herb or food name, or tap one of the examples.\u003c/div>`;\n\n\nconst searchAliases=[\n [/\\b(chinese\\s+five[\\s-]?spice|five[\\s-]?spice\\s+powder|five[\\s-]?spice)\\b/g,\"five_spice\"],\n [/\\b(green\\s+onions?|spring\\s+onions?)\\b/g,\"scallions\"],\n [/\\b(coriander\\s+leaves|chinese\\s+parsley)\\b/g,\"cilantro\"],\n [/\\b(garbanzo\\s+beans?)\\b/g,\"chickpeas\"],\n [/\\b(aubergines?)\\b/g,\"eggplant\"],\n [/\\b(courgettes?)\\b/g,\"zucchini\"],\n [/\\b(capsicums?|bell\\s+peppers?)\\b/g,\"pepper\"],\n [/\\b(ground\\s+beef|minced\\s+beef)\\b/g,\"beef\"],\n [/\\b(ground\\s+pork|minced\\s+pork)\\b/g,\"pork\"],\n [/\\b(ground\\s+turmeric)\\b/g,\"turmeric\"],\n [/\\b(black\\s+peppercorns?|peppercorns?)\\b/g,\"black pepper\"],\n [/\\b(lemon\\s+pepper(?:\\s+seasoning)?)\\b/g,\"lemon pepper\"],\n [/\\b(garlic\\s+granules?|granulated\\s+garlic)\\b/g,\"garlic powder\"],\n [/\\b(onion\\s+granules?|granulated\\s+onion)\\b/g,\"onion powder\"],\n [/\\b(red\\s+pepper\\s+flakes?|chilli\\s+flakes?|crushed\\s+red\\s+pepper)\\b/g,\"chili flakes\"],\n [/\\b(chilli\\s+powder)\\b/g,\"chili powder\"],\n [/\\b(coriander\\s+powder)\\b/g,\"coriander\"],\n [/\\b(cumin\\s+powder)\\b/g,\"cumin\"],\n [/\\b(ground\\s+ginger)\\b/g,\"ginger\"],\n [/\\b(soya\\s+sauce)\\b/g,\"soy sauce\"],\n [/\\b(rice\\s+wine\\s+vinegar)\\b/g,\"rice vinegar\"],\n [/\\b(japanese\\s+seaweed|seaweed\\s+snacks?)\\b/g,\"nori\"],\n [/\\b(korean\\s+chili\\s+flakes?|korean\\s+red\\s+pepper\\s+flakes?)\\b/g,\"gochugaru\"],\n [/\\b(sichuan\\s+peppercorns?|szechuan\\s+pepper)\\b/g,\"sichuan pepper\"],\n [/\\b(thai\\s+lemon\\s+grass)\\b/g,\"lemongrass\"],\n [/\\b(holy\\s+basil)\\b/g,\"thai basil\"],\n [/\\b(black\\s+soy\\s+sauce)\\b/g,\"soy sauce\"]\n];\nfunction normalizeSearch(q){\n let n=q.toLowerCase().replace(/[\u2019']/g,\"\").replace(/[_-]+/g,\" \").replace(/\\s+/g,\" \").trim();\n for(const [pattern,replacement] of searchAliases)n=n.replace(pattern,replacement);\n return n;\n}\n\nconst hiddenObjectRoasts={\nchair:[\"A chair? In my herb garden? Sit down. Actually, that's your only job. Congratulations.\",\"I asked for thyme, not something with four legs and commitment issues.\",\"A chair is just a table that gave up halfway. Please leave the basil alone.\"],\ntoaster:[\"A toaster? Finally, a tiny dragon that burns bread instead of villages.\",\"Do you toast herbs in that? Don't answer. I can already smell the evidence.\",\"The toaster has one job and still launches breakfast like a tiny bread cannon.\"],\nsock:[\"A sock? Is this the laundry garden now? Does it grow in pairs?\",\"That sock has seen things. Mostly the inside of a washing machine, apparently.\",\"Please don't fertilize the sock. We have standards. Low ones, but still.\"],\n\"traffic cone\":[\"A traffic cone? Ah yes, the rare orange herb of road construction.\",\"Is this to keep people away from the mint, or did the mint file a complaint?\",\"I respect its bright color. I do not respect its complete lack of flavor.\"],\n\"rubber duck\":[\"A rubber duck? Finally, a garden supervisor who squeaks instead of judging me.\",\"Does it help with seasoning? No. Does it look qualified? Also no.\",\"Please ask the duck for cooking advice. I need a break.\"],\nmicrowave:[\"A microwave? The impatient oven has arrived.\",\"It heats leftovers and makes them lava on the outside, ice on the inside. A true culinary artist.\",\"Please don't microwave the basil. The basil has done nothing to you.\"],\nspoon:[\"A spoon? Revolutionary. Next you'll show me a fork and call it a culinary breakthrough.\",\"Useful for soup, terrible at digging. I've reviewed the data.\",\"The spoon has one rounded end and somehow more purpose than most of my visitors.\"],\ntoilet:[\"A toilet? This is a herb garden, not a bathroom review site. Please take your questions elsewhere.\",\"I'm not planting mint in that. I know what you're thinking. Stop thinking it.\",\"At last, a throne worthy of absolutely no one in this conversation.\"],\nbanana:[\"A banana? A fruit wearing its own removable jacket. Suspicious.\",\"It's yellow, bendy, and somehow everyone's problem when it gets too ripe.\",\"Banana bread is good. Your search history is concerning.\"],\n\"remote control\":[\"A remote control? So you can change the channel without moving. Truly humanity's finest invention.\",\"Have you tried seasoning the batteries? Don't. That was sarcasm.\",\"This object controls a television and apparently not your decision-making.\"],\nbrick:[\"A brick? Excellent. We can build a tiny house for the basil. Rent is one compliment a week.\",\"A brick has more structural integrity than this conversation.\",\"Do not grate it over pasta. I refuse to explain why.\"],\n\"paper clip\":[\"A paper clip? A tiny metal noodle with an office job.\",\"It holds papers together better than I hold my life together.\",\"Please return it to its natural habitat: the bottom of a desk drawer.\"],\n\"left shoe\":[\"A left shoe? Where's its partner? Out living a better life, I assume.\",\"That shoe has walked a thousand miles and still hasn't found the herb section.\",\"If you plant it, will it grow a right shoe? Science has questions.\"]\n};\nconst hiddenRoastFallback=[\n\"Interesting choice. I asked for seasoning and you brought me an object with absolutely no culinary qualifications.\",\n\"That is definitely an object. I can confirm this because I have eyes and a concerning amount of free time.\",\n\"Could it improve soup? Probably not. Could it improve this conversation? The bar is underground.\",\n\"I'll put that in the 'not edible, probably' category. Very exclusive. Very prestigious.\",\n\"Ah yes, the legendary ingredient known as 'why is this here?'\"\n];\nfunction hiddenObjectEasterEgg(q){\n const n=q.trim().toLowerCase().replace(/[^a-z0-9 ]/g,\"\");\n if(!n) return null;\n const key=Object.keys(hiddenObjectRoasts).find(k=>n===k||n.includes(k)||k.includes(n));\n if(!key && !/(chair|toaster|sock|cone|duck|microwave|spoon|toilet|banana|remote|brick|paper clip|shoe)/.test(n)) return null;\n const choices=key?hiddenObjectRoasts[key]:hiddenRoastFallback;\n return card(\"Juniper says\u2026\",esc(choices[Math.floor(Math.random()*choices.length)]),\"A very questionable search\");\n}\n\nfunction guide(q){const easter=hiddenObjectEasterEgg(q);if(easter)return easter;let n=normalizeSearch(q);let found=Object.entries(herbs).filter(([k,v])=>{const key=normalizeSearch(k.replace(/_/g,\" \"));return !n||key.includes(n)||n.includes(key)||normalizeSearch(v[0]).includes(n)});return found.length?found.map(([k,v])=>card(v[0],`\u003cb>Flavor:\u003c/b> ${esc(v[1])}\u003cbr>\u003cb>Best with:\u003c/b> ${esc(v[2])}\u003cbr>${esc(v[3])}`,\"Herb & seasoning\")).join(\"\"):empty(q)}\nfunction matcher(q){const easter=hiddenObjectEasterEgg(q);if(easter)return easter;let n=normalizeSearch(q);let found=Object.entries(pairs).filter(([k])=>{const key=normalizeSearch(k.replace(/_/g,\" \"));return n.includes(key)||key.includes(n)});if(n.includes(\"potat\"))found=pairs.potato?[[\"potatoes\",pairs.potato]]:found;if(n.includes(\"strawber\"))found=[[\"strawberries\",pairs.strawber]];if(!n||!found.length)return empty(q||\"a food\");return found.map(([k,v])=>card(k[0].toUpperCase()+k.slice(1),`\u003cb>Try:\u003c/b> ${esc(v[0])}\u003cbr>${esc(v[1])}`,\"Flavor pairing\")).join(\"\")}\nfunction swap(q){const easter=hiddenObjectEasterEgg(q);if(easter)return easter;let n=normalizeSearch(q);let k=Object.keys(swaps).find(k=>{const key=normalizeSearch(k.replace(/_/g,\" \"));return n.includes(key)||key.includes(n)});return k?card(`If you're out of ${k}`,esc(swaps[k]),\"Substitution ideas\")+`\u003cdiv class=\"empty\">Swaps change the flavor. Start with a smaller amount and adjust to taste.\u003c/div>`:empty(q)}\nfunction store(q){const easter=hiddenObjectEasterEgg(q);if(easter)return easter;let n=normalizeSearch(q);let k=Object.keys(storage).find(k=>{const key=normalizeSearch(k.replace(/_/g,\" \"));return n.includes(key)||key.includes(n)});return k?card(k[0].toUpperCase()+k.slice(1),esc(storage[k]),\"Fresh storage\")+`\u003cdiv class=\"empty\">Discard herbs that are slimy, moldy, or smell unpleasant. Storage time varies with freshness and refrigerator temperature.\u003c/div>`:empty(q)}\nfunction wire(fid,iid,rid,fn){document.getElementById(fid).addEventListener(\"submit\",e=>{e.preventDefault();document.getElementById(rid).innerHTML=fn(document.getElementById(iid).value)})}\nwire(\"guide-form\",\"guide-search\",\"guide-results\",guide);wire(\"match-form\",\"match-search\",\"match-results\",matcher);wire(\"swap-form\",\"swap-search\",\"swap-results\",swap);wire(\"storage-form\",\"storage-search\",\"storage-results\",store);\ndocument.querySelectorAll(\".nav button\").forEach(b=>b.addEventListener(\"click\",()=>{document.querySelectorAll(\".nav button\").forEach(x=>x.setAttribute(\"aria-selected\",String(x===b)));document.querySelectorAll('[id^=\"panel-\"]').forEach(p=>p.classList.add(\"hidden\"));document.getElementById(\"panel-\"+b.dataset.tab).classList.remove(\"hidden\")}));\ndocument.querySelectorAll(\".examples\").forEach(g=>g.querySelectorAll(\"button\").forEach(b=>b.addEventListener(\"click\",()=>{let i=document.getElementById(g.dataset.fill);i.value=b.textContent;i.closest(\"form\").requestSubmit()})));\ndocument.getElementById(\"guide-results\").innerHTML=guide(\"\");document.getElementById(\"match-results\").innerHTML=matcher(\"chicken\");document.getElementById(\"swap-results\").innerHTML=swap(\"basil\");document.getElementById(\"storage-results\").innerHTML=store(\"basil\");\n})();\n\u003c/script>\u003c/body>\u003c/html>";
const gardenFrame=document.getElementById("herbGardenFrame");
const gardenIframe=document.getElementById("herbGardenIframe");
// Load Juniper's complete searchable garden inside the existing Herb Garden room.
gardenIframe.srcdoc = gardenDocument;

const dinnerFinder=document.getElementById('dinnerFinder');
const dinnerSearchForm=document.getElementById('dinnerSearchForm');
const dinnerSearchInput=document.getElementById('dinnerSearchInput');
const dinnerResults=document.getElementById('dinnerResults');
const dinnerRecipes=[
{title:'Ginger-Soy Chicken & Rice Bowls',terms:'chicken rice quick asian around the world',time:'30 minutes',ingredients:'Chicken, rice, soy sauce, ginger, garlic, a little honey or sugar, and optional broccoli or carrots.',steps:'Cook rice. Cut chicken into even pieces and cook in a skillet until it reaches 165°F (74°C). Add garlic, ginger, soy sauce, and a little honey with a splash of water; simmer until glossy. Serve over rice with vegetables.'},
{title:'Tofu & Bok Choy Stir-Fry',terms:'tofu bok choy vegetarian vegan quick asian around the world',time:'20 minutes',ingredients:'Firm tofu, bok choy, garlic, ginger, soy sauce, oil, and rice to serve.',steps:'Pat tofu dry and cube it. Brown in a hot skillet with a little oil. Add garlic, ginger, and chopped bok choy; cook until tender-crisp. Stir in soy sauce and a splash of water. Serve with rice.'},
{title:'Shrimp Alfredo',terms:'shrimp seafood pasta italian quick',time:'25 minutes',ingredients:'Pasta, peeled shrimp, butter, garlic, cream, grated Parmesan, black pepper, and optional parsley.',steps:'Cook pasta and reserve a little pasta water. Sauté garlic in butter, add shrimp and cook until opaque and safely cooked. Stir in cream and Parmesan over low heat. Toss with pasta, loosening with pasta water as needed. Avoid boiling the cheese sauce.'},
{title:'Egg & Vegetable Noodles',terms:'egg noodles vegetables vegetarian quick asian around the world',time:'15 minutes',ingredients:'Noodles, eggs, mixed vegetables, garlic, soy sauce, and a little oil.',steps:'Cook noodles. Scramble eggs in a skillet and set aside. Stir-fry vegetables with garlic until tender. Add noodles, eggs, and soy sauce; toss until hot.'},
{title:'Black Bean & Veggie Tacos',terms:'black beans vegetarian vegan mexican around the world quick',time:'20 minutes',ingredients:'Black beans, tortillas, bell pepper or corn, cumin, paprika, lime, and optional cabbage, salsa, or cheese.',steps:'Warm beans with cumin, paprika, and a splash of water. Sauté vegetables until tender. Fill warm tortillas with beans and vegetables, then add lime and your favorite toppings.'},
{title:'Greek-Inspired Lemon Chickpea Orzo',terms:'greek mediterranean chickpeas orzo lemon spinach feta vegetarian budget cozy pasta around the world',time:'25 minutes',ingredients:'Orzo or small pasta, canned chickpeas, broth or water, lemon, spinach, olive oil, and optional feta.',steps:'Warm olive oil in a pan and stir in the orzo for a minute. Add broth according to the pasta package directions and simmer, stirring, until tender. Stir in drained chickpeas and spinach until hot and wilted. Finish with lemon and optional feta.'},
{title:'Mexican-Inspired Chicken Tinga Tostadas',terms:'mexican chicken tostadas tomato smoky around the world',time:'30 minutes',ingredients:'Cooked shredded chicken, onion, garlic, canned tomatoes, chipotle or smoked paprika, tostadas or tortillas, and optional lettuce, avocado, and lime.',steps:'Soften sliced onion in a pan. Add garlic, tomatoes, and a little chipotle or smoked paprika; simmer until saucy. Stir in cooked shredded chicken and heat thoroughly. Spoon onto tostadas and add fresh toppings.'},
{title:'Japanese-Inspired Teriyaki Salmon',terms:'japanese salmon seafood rice around the world',time:'25 minutes',ingredients:'Salmon fillets, soy sauce, a little honey or sugar, rice vinegar or lemon, garlic or ginger, rice, and vegetables.',steps:'Mix soy sauce, honey, vinegar, and ginger. Cook salmon in a skillet or oven until it reaches 145°F (63°C) or flakes easily. Simmer the sauce separately until slightly thickened, then spoon over salmon. Serve with rice and vegetables.'},
{title:'Quick Chickpea Masala',terms:'indian chickpeas vegetarian vegan curry quick around the world budget',time:'25 minutes',ingredients:'Canned chickpeas, onion, garlic, ginger, canned tomatoes, curry powder or garam masala, and optional coconut milk or yogurt.',steps:'Cook chopped onion until soft. Add garlic, ginger, and spices; stir for 30 seconds. Add tomatoes and drained chickpeas, then simmer 10–15 minutes. Add a splash of coconut milk if desired and serve with rice or flatbread.'},
{title:'Pesto White Bean Pasta',terms:'italian pasta vegetarian beans quick around the world',time:'20 minutes',ingredients:'Pasta, canned white beans, pesto, cherry tomatoes or spinach, and optional Parmesan.',steps:'Cook pasta and reserve a little cooking water. Warm beans and tomatoes or spinach in a skillet. Stir in pesto and pasta, adding pasta water until lightly sauced. Finish with Parmesan if desired.'},
{title:'Moroccan-Inspired Sweet Potato & Lentil Stew',terms:'moroccan lentil sweet potato vegetarian vegan stew cozy around the world',time:'40 minutes',ingredients:'Sweet potato, canned or cooked lentils, onion, canned tomatoes, broth, cumin, paprika, and cinnamon.',steps:'Cook onion until soft. Add diced sweet potato, spices, tomatoes, and broth. Simmer until the potato is tender, then stir in lentils and heat through. Add water or broth if it becomes too thick.'},
{title:'Cajun-Inspired Red Beans & Rice',terms:'cajun beans rice vegetarian vegan louisiana around the world comfort',time:'30 minutes',ingredients:'Cooked red beans, rice, onion, celery or bell pepper, garlic, paprika, thyme, and a little cayenne if desired.',steps:'Cook rice separately. Sauté chopped onion and celery or pepper until soft. Add garlic, paprika, thyme, beans, and a splash of broth or water. Simmer 10–15 minutes, mash a few beans to thicken, and serve over rice.'},
{title:'Creamy Lemon Pea & Spinach Gnocchi',terms:'gnocchi pasta vegetarian quick lemon peas spinach cozy italian around the world',time:'20 minutes',ingredients:'Shelf-stable or refrigerated gnocchi, peas, spinach, garlic, lemon, cream or broth, and optional Parmesan.',steps:'Cook gnocchi according to package directions. Sauté garlic briefly, add peas and a splash of cream or broth, then stir in spinach until wilted. Add gnocchi, lemon zest or juice, and Parmesan if using.'}
];
let lastDinnerPickByCategory = {};
function renderDinnerResults(query, pickOne=false, categoryKey=''){
 const q=(query||'').trim().toLowerCase();
 // Translate common cuisine and mood searches into terms already used by recipes.
 const dinnerSearchAliases={
  'thai':'thai asian curry coconut rice noodles quick', 'thailand':'thai asian curry coconut rice noodles',
  'easy':'quick budget vegetarian pasta rice beans', 'easiest':'quick budget pasta rice beans',
  'fast':'quick 15 minutes 20 minutes 25 minutes', 'quick':'quick 15 minutes 20 minutes 25 minutes',
  'simple':'quick budget pasta rice beans', 'cheap':'budget beans lentils rice chickpeas', 'budget':'budget beans lentils rice chickpeas',
  'cozy':'cozy comfort stew soup pasta beans', 'comfort':'cozy comfort stew soup pasta beans', 'comfort food':'cozy comfort stew soup pasta beans',
  'fresh':'fresh light salad lemon vegetables chickpeas', 'light':'fresh light salad lemon vegetables', 'healthy':'fresh light vegetables beans chickpeas tofu',
  'italian':'italian pasta pesto alfredo gnocchi', 'mexican':'mexican taco tostada black beans chicken', 'japanese':'japanese teriyaki salmon rice',
  'asian':'asian japanese thai soy ginger noodles rice tofu', 'chinese':'asian soy ginger noodles rice', 'korean':'asian soy ginger rice noodles',
  'indian':'indian curry masala chickpeas', 'mediterranean':'mediterranean greek lemon chickpeas orzo',
  'vegetarian':'vegetarian vegan beans chickpeas tofu pasta', 'vegan':'vegan vegetarian beans chickpeas tofu',
  'seafood':'seafood shrimp salmon', 'one pan':'one pan skillet stew gnocchi', 'one-pan':'one pan skillet stew gnocchi',
  'pasta night':'pasta italian alfredo pesto gnocchi', 'taco night':'mexican taco black beans chicken', 'surprise me':'quick cozy fresh italian mexican japanese'
 };
 const alias=dinnerSearchAliases[q]||'';
 const searchTerms=(q+' '+alias).trim().split(/\s+/).filter(word=>word.length>2);
 const found=dinnerRecipes.filter(r=>{
  if(!q)return true;
  const hay=(r.title+' '+r.terms+' '+r.ingredients+' '+r.time).toLowerCase();
  return hay.includes(q)||searchTerms.some(word=>hay.includes(word));
 });
 if(!found.length){dinnerResults.innerHTML='<div class="dinner-empty">No exact match yet. Try an ingredient such as chicken, shrimp, beans, pasta, or a cuisine like Mexican or Japanese.</div>';return;}
 if(pickOne && found.length>1){
   const previous=lastDinnerPickByCategory[categoryKey];
   const alternatives=found.filter(r=>r.title!==previous);
   const pool=alternatives.length?alternatives:found;
   const chosen=pool[Math.floor(Math.random()*pool.length)];
   lastDinnerPickByCategory[categoryKey]=chosen.title;
   found.splice(0,found.length,chosen);
 } else if(pickOne && found.length===1){lastDinnerPickByCategory[categoryKey]=found[0].title;}
 dinnerResults.innerHTML=found.map((r)=>'<article class="dinner-card"><h4>'+r.title+'</h4><p><strong>⏱️ '+r.time+'</strong></p><p><strong>Ingredients:</strong> '+r.ingredients+'</p><details><summary>👩‍🍳 Open cooking steps</summary><p>'+r.steps+'</p></details></article>').join('');
}
dinnerSearchForm.addEventListener('submit',e=>{e.preventDefault();renderDinnerResults(dinnerSearchInput.value);});
// Use one delegated click handler for category chips so Quick always shows one card.
document.addEventListener('click',function(e){
 const button=e.target.closest('#dinnerFinder button[data-dinner-search]');
 if(!button)return;
 e.preventDefault();
 e.stopPropagation();
 const category=button.dataset.dinnerSearch;
 dinnerSearchInput.value=category;
 const q=category.toLowerCase();
 const matches=dinnerRecipes.filter(r=>{
  const hay=(r.title+' '+r.terms+' '+r.ingredients).toLowerCase();
  return hay.includes(q)||q.split(/\s+/).some(word=>word.length>2&&hay.includes(word));
 });
 if(!matches.length){
  dinnerResults.innerHTML='<div class="dinner-empty">No matching dinner yet. Try another category.</div>';
  return;
 }
 const previous=lastDinnerPickByCategory[category];
 const choices=matches.filter(r=>r.title!==previous);
 const pool=choices.length?choices:matches;
 const chosen=pool[Math.floor(Math.random()*pool.length)];
 lastDinnerPickByCategory[category]=chosen.title;
 dinnerResults.innerHTML='<p class="dinner-category-note">One pick for '+category+' — tap the category again for another idea.</p><article class="dinner-card"><h4>'+chosen.title+'</h4><p><strong>⏱️ '+chosen.time+'</strong></p><p><strong>Ingredients:</strong> '+chosen.ingredients+'</p><details><summary>👩‍🍳 Open cooking steps</summary><p>'+chosen.steps+'</p></details></article>';
},true);

function openRoom(key){
 const room=rooms[key];
 if(!room)return;
 activeRoom=key;
 document.body.classList.toggle('ham-cafe',key==='cafe');
 document.body.classList.toggle('prep-room',key==='prep');
 document.body.classList.toggle('rook-trash',key==='trash');
 document.body.classList.toggle('dinner-room',key==='dinner');
 title.textContent=room.title;
 desc.textContent=room.desc;
 list.replaceChildren();
 tipBox.hidden=true;
 tipBox.textContent='';
 const isHerbGarden = key === 'herb';
 const isPantry = key === 'pantry';
 const isFridge = key === 'fridge';
 const isBaking = key === 'baking';
 const isDinner = key === 'dinner';
 const isCafe = key === 'cafe';
 const isTrash = key === 'trash';
 const isPrep = key === 'prep';
 const isSecret = key === 'secret';
 document.getElementById('secretArchive').hidden = !isSecret;
 if(isSecret) resetSecretPanels();
 document.getElementById('prepStation').hidden = !isPrep;
 if(isPrep){document.getElementById('prepSearchInput').value='';document.getElementById('prepSearchResults').innerHTML='<p>“Good prep makes the cooking part easier. Let’s get everything ready first.” — Chef Saffron</p>';document.getElementById('prepSecretResult').textContent='';document.getElementById('prepArchiveResult').textContent='';}
 document.getElementById('rookReuseSearch').hidden = !isTrash;
  document.getElementById('rookHiddenClue').hidden = !isTrash;
 if(isTrash){document.getElementById('rookReuseInput').value='';document.getElementById('rookReuseResults').innerHTML='<p>“Every object leaves clues. Give me an item to investigate.” — Rook</p>';document.getElementById('rookSecretResult').textContent='';}
 dinnerFinder.hidden = !isDinner;
 cafeSearchWrap.hidden = !isCafe;
 if(isCafe){cafeSearchInput.value='';cafeSearchResults.innerHTML='<p>Search café sections such as smoothies, matcha, tea, treats, or around the world.</p>';}
 if(isDinner){ dinnerSearchInput.value=''; dinnerResults.innerHTML='<div class="dinner-empty">Choose a dinner category above or search for an ingredient to get started. Category buttons show one recipe at a time; text search can show multiple matches.</div>'; }
 fridgeSearchWrap.hidden = !isFridge;
 archivistSearchWrap.hidden = !isBaking;
 archivistSearchInput.value='';
 archivistSearchStatus.textContent='';
 bakingSecretResult.textContent='';
 fridgeIngredientSearch.value='';
 fridgeSearchStatus.textContent='';
 gardenFrame.hidden = !isHerbGarden;
 pantrySearch.hidden = !isPantry;
 pantryPassport.hidden = !isPantry;
 substitutionLab.hidden = !isPantry;
 storageGuide.hidden = !isPantry;
 flavorGuide.hidden = !isPantry;
 list.hidden = isHerbGarden || isSecret;
 desc.hidden = isHerbGarden || isSecret;
 if (!isPantry) { pantrySearchResult.hidden=true; pantrySearchResult.textContent=''; pantrySearchInput.value=''; }
 if (!isHerbGarden && !isFridge) room.items.forEach((entry,index)=>{
  const li=document.createElement('li');
  const button=document.createElement('button');
  button.type='button'; button.className='tip-choice'; button.dataset.tipIndex=String(index); button.textContent=entry[0];
  li.appendChild(button); list.appendChild(li);
 });
 if(isFridge){
  list.innerHTML='<li class="fridge-empty">🔎 Start typing an ingredient above to find its guide.</li>';
 }
 panel.classList.add('show');
 panel.scrollIntoView({behavior:'smooth',block:'nearest'});
}
const pantryKnowledge={
 'rice':{name:'Rice',storage:'Keep uncooked rice sealed in a cool, dry pantry. Brown rice usually keeps for less time than white rice because it contains more natural oils. Follow package directions.',use:'Make rice bowls, congee, pilaf, fried rice with properly chilled leftovers, or serve alongside stews and curries.',line:'“A pantry MVP. Tiny grains, enormous career.”'},
 'flour':{name:'All-Purpose Flour',storage:'Keep sealed in a cool, dry place. Whole-grain flours often keep longer in airtight packaging in the refrigerator or freezer.',use:'Use for many breads, cakes, cookies, pancakes, and sauces. Spoon into measuring cups and level rather than packing.',line:'“The reason cookies exist and counters look like a snowstorm.”'},
 'whole wheat flour':{name:'Whole-Wheat Flour',storage:'Because it contains more natural oils, whole-wheat flour can turn rancid sooner than white flour. Store airtight in a cool place or refrigerator/freezer.',use:'Use in breads, muffins, pancakes, and some cookies; it can make baked goods denser.',line:'“More whole grain, same ability to redecorate your shirt.”'},
 'cornmeal':{name:'Cornmeal',storage:'Keep tightly sealed, cool, and dry. Whole-grain cornmeal may keep longer refrigerated or frozen.',use:'Use for cornbread, polenta, coatings, and grits-style dishes.',line:'“Corn, but make it versatile.”'},
 'cornstarch':{name:'Cornstarch',storage:'Keep sealed and dry to prevent clumps. Use a clean, dry spoon.',use:'Whisk into a cool liquid before adding to hot sauces or soups to thicken smoothly.',line:'“A tiny amount of powder with a surprisingly large job title.”'},
 'baking powder':{name:'Baking Powder',storage:'Keep tightly closed in a cool, dry place. Moisture reduces its effectiveness; follow the package date.',use:'Helps quick breads, cakes, and pancakes rise. Do not confuse it with baking soda.',line:'“The tiny lift coach for your muffins.”'},
 'baking soda':{name:'Baking Soda',storage:'Store airtight and dry, away from strong odors. For baking, use a fresh supply and follow the recipe.',use:'Leavening in recipes with acidic ingredients; also useful for some household cleaning when appropriate.',line:'“Not interchangeable with baking powder. Chemistry has rules.”'},
 'yeast':{name:'Dried Yeast',storage:'Follow the package instructions. Unopened yeast is generally stored cool and dry; opened yeast often lasts longer refrigerated or frozen in airtight packaging.',use:'Use for yeast breads, pizza dough, and rolls. Water that is too hot can damage yeast.',line:'“Tiny organisms, big bread energy.”'},
 'sugar':{name:'Granulated Sugar',storage:'Keep airtight, dry, and away from pests and strong odors.',use:'Sweeten baking, drinks, sauces, and marinades; measure carefully.',line:'“Sugar is not a personality. It does make a decent cookie.”'},
 'brown sugar':{name:'Brown Sugar',storage:'Keep airtight so it does not dry into a brick. Follow package guidance.',use:'Adds moisture and caramel-like flavor to cookies, sauces, and marinades.',line:'“If it becomes a brick, it has chosen architecture.”'},
 'powdered sugar':{name:'Powdered Sugar',storage:'Keep sealed and dry to prevent lumps.',use:'Use for icing, frosting, dusting desserts, and some confectionery.',line:'“Snowfall, but make it dessert.”'},
 'honey':{name:'Honey',storage:'Keep tightly closed at room temperature in a dry place. Crystallization is natural; gently warm the container in warm water if needed.',use:'Sweeten tea, dressings, sauces, marinades, and baking. Never give honey to infants under 12 months.',line:'“Sticky, sweet, and very committed to the jar.”'},
 'maple syrup':{name:'Maple Syrup',storage:'After opening, refrigerate according to the label to help prevent mold.',use:'Use on pancakes, oatmeal, yogurt, roasted vegetables, and in dressings.',line:'“Pancakes have entered the chat.”'},
 'oats':{name:'Oats',storage:'Keep sealed away from moisture, heat, and strong odors. Refrigerate or freeze for longer storage if needed.',use:'Make oatmeal, overnight oats, granola, oat flour, or add to baking.',line:'“Breakfast, snacks, baking. Alarmingly employable.”'},
 'quinoa':{name:'Quinoa',storage:'Keep dry quinoa sealed in a cool, dry place. Rinse before cooking if the package recommends it.',use:'Use as a grain-bowl base, salad ingredient, or side dish.',line:'“A tiny seed with big bowl ambitions.”'},
 'barley':{name:'Pearled Barley',storage:'Store dry and sealed in a cool, dry pantry. Check package directions and cooking time.',use:'Add to soups, stews, salads, and grain bowls.',line:'“Soup’s chewy little supporting actor.”'},
 'couscous':{name:'Couscous',storage:'Keep dry couscous sealed and away from moisture.',use:'Usually steams quickly; serve with vegetables, chickpeas, stews, or herbs.',line:'“Fast, fluffy, and very pleased with itself.”'},
 'bulgur':{name:'Bulgur Wheat',storage:'Store sealed in a cool, dry place.',use:'Use in tabbouleh-style salads, pilafs, soups, and grain bowls.',line:'“Wheat that has already done some of the work.”'},
 'pasta':{name:'Dry Pasta',storage:'Keep sealed in a cool, dry place away from moisture and pests. Refrigerate cooked pasta promptly in a covered container.',use:'Pair with tomato sauce, pesto, vegetables, beans, seafood, or olive oil and garlic.',line:'“Pasta plus sauce is a plan. Six forgotten condiments is a cry for help.”'},
 'noodles':{name:'Dried Noodles',storage:'Store dried noodles sealed and dry; follow package directions, especially for egg noodles.',use:'Use in soups, stir-fries, noodle salads, and many regional dishes.',line:'“Long, twisty, and full of dinner potential.”'},
 'breadcrumbs':{name:'Breadcrumbs',storage:'Keep sealed and dry; follow the package directions. Freeze for longer storage if suitable.',use:'Use for coatings, meatballs, veggie patties, and crunchy toppings.',line:'“Crunch is a texture, not a personality. But it helps.”'},
 'panko':{name:'Panko Breadcrumbs',storage:'Keep dry and sealed after opening.',use:'Use for light, crisp coatings on vegetables, tofu, fish, or chicken.',line:'“Breadcrumbs with extra crunch confidence.”'},
 'dried beans':{name:'Dried Beans',storage:'Keep sealed in a cool, dry pantry. Sort and rinse before cooking; follow safe soaking and cooking instructions for the bean type.',use:'Use in soups, stews, chili, salads, and rice dishes.',line:'“Budget-friendly, filling, and quietly carrying the team.”'},
 'canned beans':{name:'Canned Beans',storage:'Store unopened cans in a dry pantry. Avoid cans that are bulging, leaking, badly rusted, or deeply dented at seams. Refrigerate leftovers in a separate covered container.',use:'Add to soups, tacos, salads, curries, and grain bowls. Rinse if you want to reduce some sodium.',line:'“Already cooked. Efficiency deserves applause.”'},
 'lentils':{name:'Dried Lentils',storage:'Keep sealed and dry. Sort and rinse before cooking and follow package directions.',use:'Add to soups, dals, curries, salads, and sauces.',line:'“Tiny legumes. Surprisingly useful. Respect the small ones.”'},
 'chickpeas':{name:'Chickpeas',storage:'Store dried chickpeas sealed and dry; refrigerate unused canned chickpeas in a covered container.',use:'Make hummus, curries, roasted snacks, salads, and stews.',line:'“Hummus is just one of their many career paths.”'},
 'split peas':{name:'Split Peas',storage:'Keep dry split peas sealed and away from moisture.',use:'Cook into hearty soups, stews, and dals.',line:'“Soup ingredients with a long-term plan.”'},
 'peanut butter':{name:'Peanut Butter',storage:'Follow the label; natural varieties may need refrigeration after opening. Prevent cross-contact if allergies are a concern.',use:'Spread on toast, blend into sauces, dressings, noodles, and smoothies.',line:'“A sandwich staple with sauce potential.”'},
 'tahini':{name:'Tahini',storage:'Stir if separated and follow label directions; refrigerate after opening if directed.',use:'Use in hummus, dressings, sauces, dips, and baking.',line:'“Sesame paste: creamy, nutty, and occasionally messy.”'},
 'coconut milk':{name:'Canned Coconut Milk',storage:'Store unopened cans in a cool, dry pantry. Refrigerate unused contents in a covered container rather than the opened can.',use:'Use in curries, soups, stews, desserts, and rice dishes.',line:'“One can, many tropical dinner possibilities.”'},
 'tomato paste':{name:'Tomato Paste',storage:'Store unopened cans or tubes according to the label. Refrigerate opened paste in a covered container or freeze portions.',use:'Add concentrated tomato flavor to soups, stews, sauces, and braises.',line:'“A spoonful can make a sauce taste like it has a plan.”'},
 'canned tomatoes':{name:'Canned Tomatoes',storage:'Keep unopened cans in a cool, dry place; refrigerate leftovers in a separate covered container.',use:'Use for pasta sauce, shakshuka, soups, stews, and curries.',line:'“The off-season tomato backup squad.”'},
 'stock cubes':{name:'Bouillon Cubes or Powder',storage:'Keep dry and tightly closed; follow package storage instructions. Check sodium levels if relevant.',use:'Add to soups, grains, sauces, and braises, adjusting added salt.',line:'“Flavor shortcut. Read the salt label before going wild.”'},
 'soy sauce':{name:'Soy Sauce',storage:'Follow the label; many varieties benefit from refrigeration after opening for best quality. Check for wheat and soy allergens.',use:'Season stir-fries, marinades, dipping sauces, soups, and rice dishes.',line:'“Salty, savory, and ready to rescue a bland bowl.”'},
 'miso':{name:'Miso Paste',storage:'Refrigerate after opening unless the label says otherwise; use a clean utensil.',use:'Stir into soups, dressings, marinades, glazes, and sauces. Avoid boiling hard when preserving delicate aroma.',line:'“Fermented flavor with main-character energy.”'},
 'rice vinegar':{name:'Rice Vinegar',storage:'Store sealed according to the label, away from heat and sunlight.',use:'Use in sushi rice, pickles, dressings, dipping sauces, and stir-fry sauces.',line:'“A bright little splash can wake up a whole dish.”'},
 'mirin':{name:'Mirin',storage:'Follow the label for storage after opening. Some products contain alcohol; check the label.',use:'Adds sweetness and gloss to Japanese-style sauces, glazes, and simmered dishes.',line:'“Sweet, shiny sauce energy.”'},
 'sesame oil':{name:'Sesame Oil',storage:'Keep tightly capped away from heat and light; refrigerate after opening if the label recommends it.',use:'Use toasted sesame oil mainly as a finishing flavor; use a suitable neutral oil for high-heat cooking.',line:'“A little goes a long way. A LOT goes sesame.”'},
 'dried shiitake':{name:'Dried Shiitake Mushrooms',storage:'Keep fully dry in an airtight container in a cool pantry. Rehydrate and handle according to cooking instructions.',use:'Add deep savory flavor to soups, broths, noodles, and braises.',line:'“Umami, now in convenient shelf-stable form.”'},
 'nori':{name:'Nori Seaweed',storage:'Keep sealed and dry; moisture quickly softens crisp sheets.',use:'Use for sushi rolls, rice balls, snacks, and crumbled toppings.',line:'“Seaweed that hates a damp cupboard. Fair.”'},
 'dried seaweed':{name:'Dried Seaweed',storage:'Store sealed and dry and follow package instructions for soaking or cooking.',use:'Add suitable varieties to soups, salads, rice, and noodle dishes.',line:'“A little ocean flavor without the ocean commute.”'},
 'sushi rice':{name:'Short-Grain Rice',storage:'Keep uncooked rice sealed, cool, and dry. Cooked rice needs prompt cooling and refrigeration if not served immediately.',use:'Use for sushi, onigiri, rice bowls, and other dishes calling for sticky short-grain rice.',line:'“Sticky rice is a feature, not a defect.”'},
 'glutinous rice flour':{name:'Glutinous Rice Flour',storage:'Keep sealed and dry; despite the name, glutinous rice flour does not contain gluten. Check packaging for cross-contact if needed.',use:'Use for chewy rice cakes, mochi-style sweets, and thickening recipes that specify it.',line:'“Chewy dessert science. The name is misleading; the texture is not.”'},
 'tapioca starch':{name:'Tapioca Starch',storage:'Store airtight and dry.',use:'Use in chewy desserts, some gluten-free baking, and to thicken suitable fillings or sauces.',line:'“The secret behind a lot of delightful chew.”'},
 'fish sauce':{name:'Fish Sauce',storage:'Follow the label for storage after opening and keep the cap clean. Contains fish.',use:'Add small amounts to Southeast Asian-inspired soups, dipping sauces, curries, and marinades.',line:'“A little funky, a lot savory. Measure with confidence.”'},
 'oyster sauce':{name:'Oyster Sauce',storage:'Refrigerate after opening if the label directs; contains oyster and may contain other allergens.',use:'Use in stir-fries, vegetable sauces, noodles, and savory marinades.',line:'“A spoonful of savory depth. Check the shellfish label first.”'},
 'chili crisp':{name:'Chili Crisp',storage:'Follow label storage directions; use a clean, dry spoon and check for signs of spoilage.',use:'Spoon over noodles, eggs, dumplings, rice, vegetables, or soups.',line:'“Crunchy heat for people who think dinner needs a plot twist.”'},
 'gochujang':{name:'Gochujang',storage:'Refrigerate after opening if the label directs; use a clean utensil.',use:'Use in Korean-inspired marinades, stews, sauces, and dressings. Add gradually; it can be spicy and salty.',line:'“Fermented chili paste. A little goes a long way.”'},
 'doenjang':{name:'Doenjang',storage:'Refrigerate after opening according to the package.',use:'Use in Korean soups, stews, marinades, and vegetable dips.',line:'“Deep, savory, fermented flavor doing the most.”'},
 'curry powder':{name:'Curry Powder',storage:'Keep tightly closed in a cool, dark, dry place. Replace when aroma fades.',use:'Season soups, roasted vegetables, rice, lentils, and sauces. Blends vary by region and brand.',line:'“A blend, not one universal recipe. Spice has geography.”'},
 'garam masala':{name:'Garam Masala',storage:'Keep airtight and away from heat, sunlight, and steam.',use:'Often added to Indian dishes near the end of cooking for aroma; blend recipes vary.',line:'“Warm, fragrant, and not a single fixed formula.”'},
 'turmeric':{name:'Turmeric',storage:'Keep ground turmeric sealed in a cool, dry, dark place.',use:'Use in dals, curries, rice, soups, and spice blends. It stains easily.',line:'“Golden color. Your cutting board has been warned.”'},
 'cumin':{name:'Cumin',storage:'Store whole or ground cumin airtight away from heat and sunlight.',use:'Use in beans, lentils, chili, curries, roasted vegetables, and spice rubs.',line:'“Earthy, warm, and extremely good at making beans interesting.”'},
 'coriander seeds':{name:'Coriander Seed',storage:'Keep whole seeds airtight in a cool, dry place; grind as needed for stronger aroma.',use:'Use in spice blends, pickles, curries, and roasted vegetables.',line:'“Cilantro’s seed form, with its own personality.”'},
 'paprika':{name:'Paprika',storage:'Keep sealed and away from heat and sunlight to protect color and flavor.',use:'Use in stews, eggs, roasted vegetables, rubs, and sauces. Smoked and sweet types differ.',line:'“Red powder, many possible moods.”'},
 'cinnamon':{name:'Cinnamon',storage:'Store airtight in a cool, dry, dark place.',use:'Use in oats, baked goods, warm drinks, tagines, and some savory spice blends.',line:'“Dessert aroma has entered the building.”'},
 'black pepper':{name:'Black Pepper',storage:'Keep peppercorns sealed and dry; grind as needed for strong flavor.',use:'Season nearly anything savory and some sweet recipes.',line:'“The tiny black punctuation mark of cooking.”'},
 'bay leaves':{name:'Bay Leaves',storage:'Keep dried leaves sealed away from light and moisture. Remove whole leaves before serving.',use:'Infuse soups, beans, sauces, and stews while simmering.',line:'“Flavor the pot. Do not eat the leaf. We have boundaries.”'},
 'vanilla extract':{name:'Vanilla Extract',storage:'Keep tightly closed in a cool, dark cupboard; follow label guidance.',use:'Flavor cakes, cookies, custards, oatmeal, and drinks.',line:'“A few drops of bakery magic.”'},
 'cocoa powder':{name:'Cocoa Powder',storage:'Keep sealed, cool, and dry; avoid moisture and strong odors.',use:'Use for brownies, cakes, hot cocoa, sauces, and some savory mole-style dishes.',line:'“Chocolate flavor before the sugar shows up.”'},
 'chocolate chips':{name:'Chocolate Chips',storage:'Store sealed in a cool, dry place away from strong odors. Avoid heat that causes melting or bloom.',use:'Use in cookies, muffins, pancakes, trail mix, and desserts.',line:'“A handful for the recipe. A handful for quality control.”'},
 'dried cranberries':{name:'Dried Fruit',storage:'Reseal tightly after opening and follow the package directions.',use:'Add to oats, salads, baked goods, rice pilafs, and snack mixes.',line:'“Fruit that packed a tiny suitcase.”'},
 'raisins':{name:'Raisins',storage:'Keep sealed to limit drying and moisture exposure; follow label directions.',use:'Use in oatmeal, baking, trail mix, pilafs, and chutneys.',line:'“Grapes with a long, wrinkly backstory.”'},
 'nuts':{name:'Nuts and Seeds',storage:'Store airtight. Many nuts keep their flavor longer refrigerated or frozen because their oils can turn rancid.',use:'Add to salads, oatmeal, baking, sauces, and snacks. Check allergies and avoid cross-contact.',line:'“Crunchy, useful, and very serious about allergy labels.”'},
 'chia seeds':{name:'Chia Seeds',storage:'Keep sealed, cool, and dry; refrigerate or freeze if you need longer storage.',use:'Use in chia pudding, oatmeal, smoothies, and some baking. Add liquid and allow time to gel.',line:'“Tiny seeds that turn liquid into pudding. Suspiciously useful.”'},
 'flaxseed':{name:'Flaxseed',storage:'Whole seeds keep longer than ground flax; store ground flax airtight in the refrigerator or freezer.',use:'Add ground flax to oatmeal, smoothies, baking, or recipes that call for it.',line:'“Small seed, big fiber energy.”'},
 'olive oil':{name:'Olive Oil',storage:'Keep capped in a cool, dark place away from the stove. Discard if it smells rancid or unpleasant.',use:'Use for dressings, sautéing, roasting, and finishing dishes. Choose oil to suit the recipe and heat.',line:'“Good oil deserves better than a sunny windowsill.”'},
 'vegetable oil':{name:'Neutral Cooking Oil',storage:'Keep capped away from heat and sunlight. Follow the label and discard rancid oil.',use:'Use for baking, frying, and cooking when a neutral flavor is useful.',line:'“The quiet background actor of the pantry.”'},
 'coconut flakes':{name:'Dried Coconut',storage:'Keep sealed and dry; refrigerate or freeze for longer storage if the package suggests it.',use:'Add to granola, curries, desserts, oatmeal, and baked goods.',line:'“A tropical cameo for your cookies.”'},
 'dried mushrooms':{name:'Dried Mushrooms',storage:'Keep airtight and completely dry. Rehydrate and cook according to package directions.',use:'Use in broths, risotto, noodles, soups, and sauces.',line:'“A flavor shortcut from the forest aisle.”'},
 'dried shrimp':{name:'Dried Shrimp',storage:'Keep sealed and follow package storage directions; refrigerate or freeze if the label recommends. Contains shellfish.',use:'Used in some East and Southeast Asian soups, stir-fries, rice dishes, and pastes. Rehydrate or cook as directed.',line:'“Small ingredient, big savory impact. Shellfish warning included.”'},
 'tamarind paste':{name:'Tamarind Paste',storage:'Follow the label for refrigeration after opening; use a clean utensil.',use:'Adds tang to chutneys, soups, sauces, curries, and many South and Southeast Asian dishes.',line:'“Sour, sweet, and here to wake up the sauce.”'},
 'palm sugar':{name:'Palm Sugar',storage:'Keep dry and sealed; hard blocks may need careful grating or dissolving.',use:'Sweetens sauces, curries, desserts, and drinks in many Asian cuisines.',line:'“Sweetness with a passport.”'},
 'dried chilies':{name:'Dried Chilies',storage:'Keep airtight, cool, and dry; protect from moisture and pests.',use:'Rehydrate, toast carefully, or grind according to the recipe. Heat varies widely.',line:'“Spicy little mystery packets. Start small.”'},
 'sambal oelek':{name:'Sambal Oelek',storage:'Refrigerate after opening if the label directs.',use:'Add to noodles, soups, stir-fries, marinades, and dipping sauces.',line:'“Chili paste for when dinner needs volume.”'},
 'black vinegar':{name:'Chinese Black Vinegar',storage:'Follow the label for storage after opening.',use:'Use in dipping sauces, noodles, dumplings, braises, and dressings. Flavors vary by style.',line:'“Tangy, dark, and not the same as every vinegar.”'},
 'dashi':{name:'Dashi Powder or Stock Base',storage:'Keep dry dashi powder sealed and follow package directions; refrigerate prepared stock promptly.',use:'Use as a base for miso soup, noodle broths, simmered vegetables, and sauces.',line:'“A fast track to savory broth. Read the ingredient label.”'},
 'canned coconut milk':{name:'Canned Coconut Milk',storage:'Keep unopened cans cool and dry. Transfer leftovers to a covered container and refrigerate.',use:'Use in curries, soups, desserts, and rice dishes.',line:'“Creamy pantry backup with global range.”'},
 'canned corn':{name:'Canned Corn',storage:'Store unopened cans in a dry pantry; refrigerate leftovers in a separate covered container.',use:'Add to soups, salads, fritters, rice, salsas, and casseroles.',line:'“Golden kernels, many possible plans.”'},
 'canned tuna':{name:'Canned Tuna',storage:'Keep unopened cans in a cool, dry place. Refrigerate leftovers in a separate covered container.',use:'Use in sandwiches, pasta, rice bowls, salads, and patties.',line:'“Shelf-stable protein with lunch ambitions.”'},
 'crackers':{name:'Crackers',storage:'Reseal tightly and keep dry so they stay crisp.',use:'Serve with cheese, soups, dips, or crush for a crumb topping.',line:'“Crunch is temporary. Seal the bag.”'},
 'tortillas':{name:'Shelf-Stable Tortillas',storage:'Follow the package instructions; refrigerate or freeze if directed, especially after opening.',use:'Use for tacos, wraps, quesadillas, enchiladas, and quick pizzas.',line:'“A flatbread with excellent adaptability.”'},
 'instant noodles':{name:'Instant Noodles',storage:'Store unopened packages dry and follow the packet instructions. Check seasoning sachets for allergens and sodium.',use:'Upgrade with vegetables, egg, tofu, beans, or leftover cooked protein; handle add-ins safely.',line:'“Fast dinner. The seasoning packet is not a dare.”'},
 'dried pasta':{name:'Dry Pasta',storage:'Keep sealed and dry away from pests and moisture.',use:'Use in pasta dishes, soups, and casseroles.',line:'“A pantry staple with a long shelf life when stored well.”'},
 'canned chickpeas':{name:'Canned Chickpeas',storage:'Keep unopened cans dry; transfer unused contents to a covered container and refrigerate.',use:'Make hummus, salads, curries, and roasted chickpeas.',line:'“Convenience with a hummus-shaped future.”'}
};
function searchPantry(q){
 const query=q.trim().toLowerCase();
 if(!query){pantrySearchResult.textContent='Type an ingredient first, and I will pretend this was the plan all along.';pantrySearchResult.hidden=false;return;}
 const aliases={"white rice":"rice","brown rice":"rice","jasmine rice":"rice","basmati rice":"rice","sticky rice":"sushi rice","short grain rice":"sushi rice","rice flour":"glutinous rice flour","all purpose flour":"flour","plain flour":"flour","wholemeal flour":"whole wheat flour","chickpea":"chickpeas","garbanzo beans":"chickpeas","black beans":"dried beans","kidney beans":"dried beans","pinto beans":"dried beans","canned black beans":"canned beans","soybean paste":"doenjang","korean chili paste":"gochujang","chili paste":"sambal oelek","chilli paste":"sambal oelek","oyster sauce":"oyster sauce","fish sauce":"fish sauce","light soy sauce":"soy sauce","dark soy sauce":"soy sauce","toasted sesame oil":"sesame oil","sesame seeds":"nuts","sunflower seeds":"nuts","almond":"nuts","walnut":"nuts","peanut":"peanut butter","tapioca flour":"tapioca starch","corn flour":"cornstarch","corn starch":"cornstarch","bicarb soda":"baking soda","bicarbonate of soda":"baking soda","powdered sugar":"powdered sugar","icing sugar":"powdered sugar","caster sugar":"granulated sugar","dried noodles":"noodles","ramen":"instant noodles","ramen noodles":"instant noodles","rice noodles":"noodles","glass noodles":"noodles","black vinegar":"black vinegar","shaoxing wine":"mirin","dried shrimp":"dried shrimp","dried prawns":"dried shrimp","nori sheets":"nori","wakame":"dried seaweed","kombu":"dried seaweed","dried shiitake mushrooms":"dried shiitake","shiitake":"dried shiitake","coconut cream":"coconut milk","tomato puree":"tomato paste","tomato purée":"tomato paste","passata":"canned tomatoes","chicken bouillon":"stock cubes","vegetable bouillon":"stock cubes","stock powder":"stock cubes","olive oil":"olive oil","vegetable oil":"vegetable oil","chili flakes":"dried chilies","chilli flakes":"dried chilies","red pepper flakes":"dried chilies","curry paste":"gochujang","tahini paste":"tahini"};
 let key=aliases[query];
 const pantryKeys=Object.keys(pantryKnowledge).sort((a,b)=>b.length-a.length);
 if(!key) key=pantryKeys.find(k=>k===query||pantryKnowledge[k].name.toLowerCase()===query);
 if(!key) key=pantryKeys.find(k=>query.includes(k)||pantryKnowledge[k].name.toLowerCase().includes(query));
 if(!key) key=pantryKeys.find(k=>pantryKnowledge[k].name.toLowerCase().split(/[ ,()/-]+/).some(word=>word.length>3&&query.includes(word)));
 if(!key){pantrySearchResult.textContent='I do not have a dedicated card for “'+q.trim()+'” yet. Try a staple such as rice, flour, oats, lentils, or pasta; an Asian pantry ingredient such as soy sauce, miso, nori, gochujang, fish sauce, or rice vinegar; or a global staple such as couscous, quinoa, tahini, tamarind, or coconut milk. “The pantry is large. My tiny clipboard is doing its best.”';pantrySearchResult.hidden=false;return;}
 const item=pantryKnowledge[key];
 pantrySearchResult.textContent='🦖 '+item.name+'\n\n🫙 Storage: '+item.storage+'\n\n🍽️ Ways to use it: '+item.use+'\n\n💬 Lil Dino: '+item.line;
 pantrySearchResult.hidden=false;
}

const substitutions={
 'buttermilk':{swap:'1 cup milk + 1 tablespoon lemon juice or white vinegar. Stir and let stand 5–10 minutes.',note:'Best for pancakes, muffins, and many quick breads. It may be a little thinner than cultured buttermilk.'},
 'egg':{swap:'For many baked goods, try ¼ cup unsweetened applesauce per egg, or ¼ cup mashed banana if its flavor fits.',note:'These work best in moist cakes, muffins, and quick breads; they do not replace eggs well in omelets, meringues, or recipes relying on eggs for structure.'},
 'eggs':{swap:'For many baked goods, try ¼ cup unsweetened applesauce per egg, or ¼ cup mashed banana if its flavor fits.',note:'These work best in moist cakes, muffins, and quick breads; they do not replace eggs well in omelets, meringues, or recipes relying on eggs for structure.'},
 'butter':{swap:'For many cakes, muffins, and quick breads, use a similar amount of neutral oil; start with about ¾ cup oil for every 1 cup butter.',note:'Oil adds moisture but not butter flavor, and it will not cream with sugar like solid butter. This is not a universal swap for pastry or cookies.'},
 'sour cream':{swap:'Plain unsweetened Greek yogurt, in an equal amount, is often a good substitute.',note:'It gives a similar tang and creamy texture. Full-fat yogurt is usually closest; avoid sweetened or flavored yogurt.'},
 'plain yogurt':{swap:'Sour cream or plain unsweetened Greek yogurt can often work in equal amounts, depending on the recipe.',note:'Thickness and tang can vary. For marinades and sauces, add gently and avoid boiling if the dairy may split.'},
 'lemon juice':{swap:'Lime juice in an equal amount is often the closest swap. For some recipes, mild vinegar can provide acidity.',note:'The flavor will change; vinegar is sharper and lacks citrus aroma. Use the substitute that suits the dish.'},
 'lime juice':{swap:'Lemon juice in an equal amount is often the closest swap.',note:'The dish will taste a little different, but acidity is similar.'},
 'cornstarch':{swap:'Use about twice as much all-purpose flour as cornstarch for thickening a sauce, then simmer long enough to cook the flour.',note:'Flour gives a cloudier, less glossy result. This swap is not suitable for every custard or gluten-free recipe.'},
 'all-purpose flour':{swap:'For some sauces, cornstarch can thicken instead; for baking, use a recipe-specific flour alternative rather than swapping blindly.',note:'Flour provides structure, so the best alternative depends on what you are making.'},
 'baking powder':{swap:'If you have baking soda and an acid, a common emergency substitute for 1 teaspoon baking powder is ¼ teaspoon baking soda plus ½ teaspoon cream of tartar.',note:'Measure carefully. Baking soda alone is not a direct substitute, and the recipe’s acidity matters.'},
 'baking soda':{swap:'Baking powder can sometimes replace baking soda, but you generally need more and the result may change.',note:'Because baking soda and baking powder have different strengths and chemistry, the recipe matters. A direct 1:1 swap is not reliable.'},
 'honey':{swap:'Maple syrup can often replace honey in sauces and some baking in a similar amount.',note:'Maple syrup is thinner and has its own flavor; moisture and browning may change in baked goods.'},
 'maple syrup':{swap:'Honey can often replace maple syrup in sauces or toppings in a similar amount.',note:'Honey is usually sweeter and more floral, so the flavor will change.'},
 'heavy cream':{swap:'For some sauces and soups, try half-and-half or milk enriched with a little butter.',note:'This will not whip like heavy cream, and the result may be thinner. It is not a reliable swap for whipped cream.'},
 'cream cheese':{swap:'For dips and some fillings, thick plain Greek yogurt or strained cottage cheese blended smooth may work.',note:'Texture, tang, and richness will differ. These are not reliable one-for-one swaps in cheesecake.'},
 'rice vinegar':{swap:'Mild apple cider vinegar or white wine vinegar can work in a similar amount; start with a little less and adjust to taste.',note:'The flavor is sharper and less delicate, so taste before adding more.'},
 'soy sauce':{swap:'Tamari is often a close alternative; check the label because many tamari products are gluten-free but not all products are identical.',note:'Coconut aminos are another option but are usually sweeter and less salty. Check allergens and dietary needs.'}
};
function findSubstitution(raw){
 const q=raw.trim().toLowerCase().replace(/[.!?]+$/,'');
 if(!q){swapResult.textContent='Tell me which ingredient your recipe needs first. I cannot substitute an empty bowl. — Lil Dino';swapResult.hidden=false;return;}
 const aliases={'an egg':'egg','one egg':'egg','eggs':'eggs','butter milk':'buttermilk','heavy whipping cream':'heavy cream','cream':'heavy cream','plain flour':'all-purpose flour','all purpose flour':'all-purpose flour','bicarb soda':'baking soda','bicarbonate of soda':'baking soda','lemon':'lemon juice','lime':'lime juice'};
 const key=aliases[q]||Object.keys(substitutions).sort((a,b)=>b.length-a.length).find(k=>q===k||q.includes(k));
 if(!key){swapResult.textContent='I do not have a tested quick-swap note for “'+raw.trim()+'” yet. Try buttermilk, egg, butter, sour cream, lemon juice, cornstarch, baking powder, heavy cream, rice vinegar, or soy sauce.\n\nLil Dino: “I would rather ask what the recipe needs than confidently ruin your dinner.”';swapResult.hidden=false;return;}
 const item=substitutions[key];
 swapResult.textContent=['🔄 Missing: '+key.charAt(0).toUpperCase()+key.slice(1),'','✅ Try this: '+item.swap,'','🧪 What may change: '+item.note,'','💬 Lil Dino: “A substitute is a plan B, not a legally binding promise. Check what your recipe needs.”'].join('\n');
 swapResult.hidden=false;
}
const swapInput=document.getElementById('swapInput');
const swapResult=document.getElementById('swapResult');
document.getElementById('swapForm').addEventListener('submit',event=>{event.preventDefault();findSubstitution(swapInput.value);});
document.querySelectorAll('[data-swap-example]').forEach(button=>button.addEventListener('click',()=>{swapInput.value=button.dataset.swapExample;findSubstitution(swapInput.value);}));


const storageInput=document.getElementById('storageInput');
const storageResult=document.getElementById('storageResult');
const storageNotes={
 'potatoes':{title:'Potatoes',where:'Store uncut potatoes in a cool, dark, well-ventilated place. Keep them away from onions if possible; do not store raw potatoes in the refrigerator as a default.',fresh:'Avoid potatoes that are extensively green, badly shriveled, or rotten. Remove small sprouts and eyes generously; discard potatoes that are very green or bitter.'},
 'flour':{title:'Flour',where:'Keep flour sealed in a cool, dry place. Whole-grain flour generally keeps longer when refrigerated or frozen in an airtight container. Follow package guidance.',fresh:'Discard flour with moisture, mold, insects, or an unusual rancid smell.'},
 'opened coconut milk':{title:'Opened Coconut Milk',where:'Transfer leftovers from the can to a clean, covered container and refrigerate promptly. Use within the timeframe on the package; freeze if you need longer storage and the product is suitable for freezing.',fresh:'Discard if moldy, unexpectedly fizzy, or noticeably off-smelling. Separation alone can be normal; stir and check the label.'},
 'coconut milk':{title:'Canned Coconut Milk',where:'Store unopened cans in a cool, dry pantry. After opening, transfer leftovers to a covered container and refrigerate promptly; follow the label for use-by guidance.',fresh:'Do not use a bulging, leaking, or badly damaged can.'},
 'berries':{title:'Berries',where:'Refrigerate berries dry and unwashed in a breathable container. Wash just before eating and remove damaged berries.',fresh:'Discard moldy berries and any berries that are slimy or smell fermented. Check the whole container for mold spread.'},
 'bread':{title:'Bread',where:'Keep bread sealed at room temperature for short-term use. Refrigeration can make it stale faster; freeze extra bread in a sealed bag for longer storage.',fresh:'Discard the loaf if you see mold; do not just cut away a moldy spot from soft bread.'},
 'eggs':{title:'Eggs',where:'Keep shell eggs in their carton on an interior refrigerator shelf at 40°F (4°C) or below, rather than in the door.',fresh:'Refrigerate promptly and follow the carton date and food-safety guidance. Discard eggs with cracked shells or an unusual odor after cracking.'},
 'leftovers':{title:'Leftovers',where:'Refrigerate perishable leftovers within 2 hours (within 1 hour if the temperature is above 90°F/32°C). Use shallow containers and keep the refrigerator at 40°F (4°C) or below. Most cooked leftovers should be used within 3–4 days or frozen.',fresh:'When in doubt, throw it out; smell and appearance cannot reliably prove leftovers are safe. Reheat leftovers to 165°F (74°C).'},
 'soy sauce':{title:'Soy Sauce',where:'Store tightly capped in a cool, dark pantry unless the label recommends refrigeration. Refrigeration after opening can help preserve flavor.',fresh:'Follow the bottle directions and discard if you notice mold, an unusual odor, or contamination.'},
 'rice':{title:'Uncooked Rice',where:'Keep uncooked rice sealed in a cool, dry pantry. Store cooked rice promptly in shallow containers in the refrigerator and use within 3–4 days, or freeze.',fresh:'Cool and refrigerate cooked rice promptly; do not leave it at room temperature for long periods.'},
 'onions':{title:'Onions',where:'Store whole dry onions in a cool, dry, well-ventilated place. Refrigerate cut onion in a covered container.',fresh:'Discard onions that are moldy, leaking, or extensively soft and rotten.'},
 'garlic':{title:'Garlic',where:'Store whole garlic bulbs in a cool, dry, well-ventilated place. Refrigerate peeled or chopped garlic and follow safe handling guidance; do not keep garlic in oil at room temperature.',fresh:'Discard moldy or mushy cloves.'}
};
function lookupStorage(raw){
 const q=raw.trim().toLowerCase().replace(/[.!?]+$/,'');
 if(!q){storageResult.textContent='Pick an ingredient first. My storage clipboard is ready.';storageResult.hidden=false;return;}
 const aliases={'potato':'potatoes','potatoes':'potatoes','flours':'flour','coconut milk opened':'opened coconut milk','canned coconut milk':'coconut milk','strawberries':'berries','strawberry':'berries','eggs in shell':'eggs','cooked rice':'rice','onion':'onions','garlic cloves':'garlic','leftover food':'leftovers'};
 let key=aliases[q]||Object.keys(storageNotes).sort((a,b)=>b.length-a.length).find(k=>q===k||q.includes(k));
 if(!key && q.includes('coconut milk'))key='opened coconut milk';
 if(!key){storageResult.textContent='I do not have a storage card for “'+raw.trim()+'” yet. Try potatoes, flour, opened coconut milk, berries, bread, eggs, leftovers, soy sauce, rice, onions, or garlic.\\n\\n💬 Lil Dino: “I would rather admit I need a better label than guess with your dinner.”';storageResult.hidden=false;return;}
 const item=storageNotes[key];
 storageResult.textContent='🫙 '+item.title+'\\n\\n📍 Where & how: '+item.where+'\\n\\n🔎 Freshness check: '+item.fresh+'\\n\\n💬 Lil Dino: “Storage advice is useful. A suspicious smell is not a personality test—when in doubt, toss it.”';
 storageResult.hidden=false;
}
document.getElementById('storageForm').addEventListener('submit',event=>{event.preventDefault();lookupStorage(storageInput.value);});
document.querySelectorAll('[data-storage-example]').forEach(button=>button.addEventListener('click',()=>{storageInput.value=button.dataset.storageExample;lookupStorage(storageInput.value);}));


const flavorInput=document.getElementById('flavorInput');
const flavorResult=document.getElementById('flavorResult');
const flavorNotes={
 'strawberries':{title:'Strawberries',pairs:'🍋 Lemon or balsamic vinegar for brightness; 🍫 dark chocolate for bittersweet contrast; 🌿 basil or mint for a fresh herbal note; 🥛 cream or yogurt for richness.',idea:'Try strawberries with basil and a little lemon in a fruit salad.',note:'“Chocolate-dipped strawberries are popular for a reason. I will pretend this was my discovery.”'},
 'tomatoes':{title:'Tomatoes',pairs:'🧄 garlic and 🫒 olive oil; 🌿 basil or oregano; 🧀 mozzarella or Parmesan; 🌶️ black pepper or chili flakes; 🍋 a splash of vinegar for brightness.',idea:'Toss ripe tomatoes with olive oil, garlic, basil, and a pinch of salt.',note:'“Tomato, garlic, basil. A classic trio. Unlike the three mystery jars in the back.”'},
 'chicken':{title:'Chicken',pairs:'🍋 lemon and 🧄 garlic; 🌿 thyme or rosemary; 🌶️ paprika and black pepper; 🥢 ginger, soy sauce, and scallions; 🍯 honey with mustard for sweet-tangy balance.',idea:'For an easy direction, combine garlic, lemon, black pepper, and thyme.',note:'“Chicken is a blank canvas. Please do not interpret that as permission to use every spice at once.”'},
 'mushrooms':{title:'Mushrooms',pairs:'🧄 garlic and 🧈 butter; 🌿 thyme; 🥢 soy sauce or miso for savory depth; 🍋 a little lemon to brighten; 🧀 Parmesan.',idea:'Sauté mushrooms with garlic and thyme, then finish with a small splash of lemon.',note:'“Mushrooms already bring the earthy flavor. Let them have the spotlight for once.”'},
 'chickpeas':{title:'Chickpeas',pairs:'🍋 lemon and 🧄 garlic; 🌿 cumin, coriander, or paprika; 🥣 tahini; 🍅 tomatoes; 🌿 parsley or mint; 🥥 coconut milk with curry spices.',idea:'Toss roasted chickpeas with cumin, paprika, olive oil, and lemon after cooking.',note:'“Chickpeas are versatile. They are also excellent at pretending to be the main character.”'},
 'potatoes':{title:'Potatoes',pairs:'🧄 garlic and 🌿 rosemary; 🧈 butter and chives; 🌶️ paprika and black pepper; 🧀 cheddar; 🥒 sour cream or yogurt; 🍋 vinegar for a sharp contrast.',idea:'Roast potatoes with oil, garlic, rosemary, and black pepper.',note:'“Potatoes work with almost anything. That is not a challenge to put candy on them.”'},
 'shrimp':{title:'Shrimp',pairs:'🍋 lemon or lime; 🧄 garlic; 🧈 butter; 🌶️ chili flakes; 🌿 parsley or cilantro; 🥥 coconut milk with ginger for a different direction.',idea:'Sauté shrimp with garlic and a little butter, then finish with lemon and parsley. Cook shrimp until opaque and firm.',note:'“Shrimp cooks quickly. Blink dramatically, but do not walk away from the pan.”'},
 'chocolate':{title:'Chocolate',pairs:'🍓 strawberries or raspberries; ☕ coffee; 🍊 orange; 🥜 peanut or hazelnut; 🌶️ a tiny pinch of chili; 🧂 a little salt to sharpen the flavor.',idea:'Add a small pinch of salt or a little coffee to deepen a chocolate dessert.',note:'“Chocolate and coffee: proof that excellent teamwork exists.”'},
 'eggs':{title:'Eggs',pairs:'🧀 cheddar, feta, or Parmesan; 🧄 chives and scallions; 🍅 tomatoes; 🌶️ black pepper or chili crisp; 🍄 mushrooms; 🥬 spinach.',idea:'Try scrambled eggs with chives and a little Parmesan.',note:'“Eggs are adaptable. Please give them a break from being called boring.”'},
 'rice':{title:'Rice',pairs:'🥢 soy sauce, sesame oil, and scallions; 🧄 garlic and ginger; 🥥 coconut milk with lime; 🫘 beans and cumin; 🌿 cilantro; 🍋 citrus.',idea:'For a simple savory bowl, add scallions, a little soy sauce, and sesame oil.',note:'“Rice is the reliable friend who makes the whole meal work.”'},
 'carrots':{title:'Carrots',pairs:'🍯 honey or maple; 🍋 lemon or orange; 🌿 thyme or dill; 🧄 garlic; 🌶️ cumin; 🥛 yogurt with herbs.',idea:'Roast carrots with olive oil, cumin, and a squeeze of lemon.',note:'“Carrots can be sweet or savory. Range. Character development.”'},
 'avocado':{title:'Avocado',pairs:'🍋 lime or lemon; 🌶️ chili; 🧅 red onion; 🍅 tomato; 🌿 cilantro; 🥚 eggs; 🥣 yogurt or tahini.',idea:'Mash avocado with lime, salt, and chili flakes for a quick topping.',note:'“A ripe avocado gives you a very small window. Plan accordingly.”'},
 'bananas':{title:'Bananas',pairs:'🥜 peanut butter; 🍫 chocolate; 🥣 oats and cinnamon; 🥛 yogurt; 🍯 honey; 🥥 coconut.',idea:'Add banana, cinnamon, and peanut butter to oatmeal.',note:'“Banana and peanut butter: breakfast doing the bare minimum, beautifully.”'}
};
function lookupFlavor(raw){
 const q=raw.trim().toLowerCase().replace(/[.!?]+$/,'');
 if(!q){flavorResult.textContent='Pick an ingredient first. I cannot pair a blank with anything except disappointment.';flavorResult.hidden=false;return;}
 const aliases={'strawberry':'strawberries','tomato':'tomatoes','mushroom':'mushrooms','potato':'potatoes','prawn':'shrimp','prawns':'shrimp','garbanzo beans':'chickpeas','banana':'bananas','carrot':'carrots','avocados':'avocado'};
 const key=aliases[q]||Object.keys(flavorNotes).sort((a,b)=>b.length-a.length).find(k=>q===k||q.includes(k));
 if(!key){flavorResult.textContent='I do not have a pairing card for “'+raw.trim()+'” yet. Try strawberries, tomatoes, chicken, mushrooms, chickpeas, potatoes, shrimp, chocolate, eggs, rice, carrots, avocado, or bananas.\n\n💬 Lil Dino: “I could make something up, but we are trying to improve dinner, not start a kitchen rumor.”';flavorResult.hidden=false;return;}
 const item=flavorNotes[key];
 flavorResult.textContent='🍽️ '+item.title+' pairs well with:\n'+item.pairs+'\n\n✨ Easy idea: '+item.idea+'\n\n💬 Lil Dino: “'+item.note.replace(/^“|”$/g,'')+'”';
 flavorResult.hidden=false;
}
document.getElementById('flavorForm').addEventListener('submit',event=>{event.preventDefault();lookupFlavor(flavorInput.value);});
document.querySelectorAll('[data-flavor-example]').forEach(button=>button.addEventListener('click',()=>{flavorInput.value=button.dataset.flavorExample;lookupFlavor(flavorInput.value);}));

function smartPantrySearch(raw){
 const q=raw.trim();
 if(!q){pantrySmartResults.hidden=false;pantrySmartResults.innerHTML='<article class="pantry-smart-card"><h4>🦖 Lil Dino needs an ingredient first</h4><p>Try miso, strawberries, bulgur, soy sauce, or buttermilk.</p></article>';return;}
 // Keep the familiar ingredient card and bring matching tool answers directly beneath it.
 searchPantry(q);
 const n=q.toLowerCase().replace(/[’']/g,'').replace(/[_-]+/g,' ').replace(/\s+/g,' ').trim();
 const escHTML=v=>String(v??'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
 const international=/miso|gochujang|doenjang|nori|soy sauce|sesame oil|fish sauce|oyster sauce|rice vinegar|tamarind|coconut milk|tahini|couscous|quinoa|bulgur|chickpea|lentil|palm sugar|dashi|sambal|black vinegar|dried shrimp|curry|garam masala|harissa|zaatar|panko|mirin|lemongrass|gochugaru|sichuan|kimchi/.test(n);
 const storageAliases={'potato':'potatoes','strawberries':'berries','strawberry':'berries','onion':'onions','cooked rice':'rice','opened coconut milk':'opened coconut milk','coconut milk':'coconut milk','egg':'eggs','leftover food':'leftovers'};
 const storageKey=storageAliases[n]||Object.keys(storageNotes).sort((a,b)=>b.length-a.length).find(k=>n===k||n.includes(k)||k.includes(n));
 const flavorAliases={'strawberry':'strawberries','tomato':'tomatoes','mushroom':'mushrooms','potato':'potatoes','prawn':'shrimp','prawns':'shrimp','garbanzo beans':'chickpeas','banana':'bananas','carrot':'carrots','avocados':'avocado'};
 const flavorKey=flavorAliases[n]||Object.keys(flavorNotes).sort((a,b)=>b.length-a.length).find(k=>n===k||n.includes(k)||k.includes(n));
 const swapAliases={'eggs':'egg','butter milk':'buttermilk','plain flour':'all-purpose flour','bicarb soda':'baking soda','lemon':'lemon juice','lime':'lime juice'};
 const swapKey=swapAliases[n]||Object.keys(substitutions).sort((a,b)=>b.length-a.length).find(k=>n===k||n.includes(k));
 const cards=[];
 const base=pantrySearchResult.textContent.trim();
 if(base) cards.push('<article class="pantry-smart-card"><h4>🦖 Lil Dino’s Ingredient Notes</h4><p>'+escHTML(base)+'</p></article>');
 if(storageKey){lookupStorage(q);cards.push('<article class="pantry-smart-card"><h4>🫙 Storage & Freshness</h4><p>'+escHTML(storageResult.textContent)+'</p></article>');}
 if(flavorKey){lookupFlavor(q);cards.push('<article class="pantry-smart-card pink"><h4>🍓 Flavor Pairings</h4><p>'+escHTML(flavorResult.textContent)+'</p></article>');}
 if(swapKey){findSubstitution(q);cards.push('<article class="pantry-smart-card gold"><h4>🔄 Substitution Ideas</h4><p>'+escHTML(swapResult.textContent)+'</p></article>');}
 if(international){
   const passportMessage='🌏 Pantry Passport: '+q+' connects to ingredients or food traditions found in cuisines around the world. Regional uses vary, so explore specific cuisines rather than assuming one ingredient represents an entire region.';
   cards.push('<article class="pantry-smart-card blue"><h4>🌏 Around the World</h4><p>'+escHTML(passportMessage)+'</p><p style="margin-top:8px">Tap the Pantry Passport collection below to explore more ingredients from different regions.</p></article>');
 }
 if(cards.length===1){cards.push('<article class="pantry-smart-card"><h4>✨ More tools are growing</h4><p>I have ingredient notes for this search. Storage, pairing, and substitution cards appear when I have a matching guide for the ingredient.</p></article>');}
 pantrySmartResults.innerHTML=cards.join('');
 pantrySmartResults.hidden=false;
 // Keep the individual browse tools available, but put the combined answers right under the search.
 storageGuide.hidden=true;flavorGuide.hidden=true;substitutionLab.hidden=true;pantryPassport.hidden=true;
 pantrySearchResult.hidden=true;
 pantrySmartResults.scrollIntoView({behavior:'smooth',block:'nearest'});
}
document.getElementById('pantrySearchForm').addEventListener('submit',event=>{event.preventDefault();smartPantrySearch(pantrySearchInput.value);});
document.querySelectorAll('[data-pantry-example]').forEach(button=>button.addEventListener('click',()=>{pantrySearchInput.value=button.dataset.pantryExample;smartPantrySearch(pantrySearchInput.value);}));
document.querySelectorAll('[data-passport-ingredient]').forEach(button=>button.addEventListener('click',()=>{pantrySearchInput.value=button.dataset.passportIngredient;smartPantrySearch(pantrySearchInput.value);pantrySearchResult.scrollIntoView({behavior:'smooth',block:'nearest'});}));

fridgeIngredientSearch.addEventListener('input',()=>{
 if(activeRoom!=='fridge')return;
 const query=fridgeIngredientSearch.value.trim().toLowerCase();
 list.replaceChildren(); tipBox.hidden=true;
 if(!query){list.innerHTML='<li class="fridge-empty">🔎 Start typing an ingredient above to find its guide.</li>';fridgeSearchStatus.textContent='';return;}
 const safetySearch=/\b(gun|guns|firearm|firearms|weapon|weapons|rifle|pistol|handgun|ammo|ammunition|bomb|bombs|explosive|explosives|grenade|poison|poisons|toxic chemical|overdose|suicide|self[- ]harm|hurt myself|kill myself|shooting|stab|stabbing)\b/i.test(query);
 if(safetySearch){
  const li=document.createElement('li');const button=document.createElement('button');button.type='button';button.className='tip-choice';button.dataset.safetySearch=query;button.textContent='💚 A gentle note from the Fridge Crew';li.appendChild(button);list.appendChild(li);fridgeSearchStatus.textContent='A special safety-aware Easter egg. Tap to read the crew’s message.';return;
 }
 const matches=rooms.fridge.items.map((entry,index)=>({entry,index})).filter(x=>x.entry[0].toLowerCase().includes(query)||x.entry[1].toLowerCase().includes(query));
 if(!matches.length){
  const silly=/\b(missing\ snack\ stash|invisible\ sandwich|remote\ control\ car|cursed\ cookbook|dinosaur\ fossil|washing\ machine|computer\ mouse|laundry\ basket|stuffed\ animal|treasure\ chest|cutting\ board|measuring\ cup|phone\ charger|rocking\ chair|magic\ potion|traffic\ cone|water\ bottle|dish\ sponge|empty\ plate|pencil\ case|dish\ towel|dragon\ egg|flower\ pot|headphones|lego\ brick|pillowcase|pirate\ hat|right\ shoe|skateboard|sunglasses|teddy\ bear|toothbrush|wizard\ hat|hairbrush|house\ key|left\ shoe|oven\ mitt|pizza\ box|backpack|dinosaur|keyboard|scissors|soda\ can|umbrella|battery|bicycle|blanket|glasses|hamster|pot\ lid|shampoo|spatula|toy\ car|cactus|camera|candle|eraser|flower|pencil|pillow|remote|wallet|alien|glove|phone|plant|whisk|book|coin|fork|lamp|lego|oven|rock|shoe|soap|tape|hat|key|chair|toaster|sock|traffic cone|cone|rubber duck|duck|microwave|spoon|toilet|remote control|remote|brick|paper clip|left shoe|shoe|lamp|pillow|book|phone|keyboard|umbrella|rock|rocking chair|teddy bear|hamster|dinosaur|cactus|sunglasses|backpack|pencil|eraser|wallet|bicycle|skateboard|soap|shampoo|flower pot|flowerpot|pizza box|lego|lego brick)\b/i.test(query);
  if(silly){const li=document.createElement('li');const button=document.createElement('button');button.type='button';button.className='tip-choice';button.dataset.randomThing=query;button.textContent='🎲 Ask the Fridge Crew about “'+query+'”';li.appendChild(button);list.appendChild(li);fridgeSearchStatus.textContent='You found a random-object Easter egg. Tap to see the crew’s reaction!';return;}
  list.innerHTML='<li class="fridge-empty">No exact match yet. Try a shorter name, such as “tofu,” “greens,” or “mushroom.” Or try a random object for a silly Easter egg. 🥚</li>';fridgeSearchStatus.textContent='No ingredient match found.';return;
 }
 matches.forEach(({entry,index})=>{const li=document.createElement('li');const button=document.createElement('button');button.type='button';button.className='tip-choice';button.dataset.tipIndex=String(index);button.textContent=entry[0];li.appendChild(button);list.appendChild(li);});
 fridgeSearchStatus.textContent=matches.length+' matching ingredient guide'+(matches.length===1?'':'s')+'. Tap one to open its four sections and matching character voices.';
});

const prepSearchInput=document.getElementById('prepSearchInput');
const prepSearchResults=document.getElementById('prepSearchResults');
function searchPrep(query){
 const q=String(query == null ? '' : query).trim().toLowerCase();
 if(!prepSearchResults) return;
 prepSearchResults.replaceChildren();
 if(!q){prepSearchResults.innerHTML='<p>Try an ingredient or skill above to get started.</p>';return;}
 const prepItems=(rooms && rooms.prep && Array.isArray(rooms.prep.items) ? rooms.prep.items : []).filter(entry=>Array.isArray(entry) && typeof entry[0]==='string' && typeof entry[1]==='string');
 const aliases={onion:['onion','shallot','scallion','green onion'],ginger:['ginger'],garlic:['garlic'],bok:['bok choy','napa cabbage','cabbage','leafy greens'],lemongrass:['lemongrass','lemon grass','thai curry'],rice:['rice','noodles','noodle'],tofu:['tofu','mushroom'],knife:['knife','cutting','dice','chop','slice','mince','safety'],measure:['measure','conversion','cup','tablespoon','teaspoon','gram','weight','garlic equivalents','produce yields','yield','head of garlic','clove'],meat:['meat','chicken','poultry','seafood','raw'],wash:['wash','produce','greens','clean'],pan:['pan','mise en place','preheat','ready'],carrot:['carrot','parsnip','root vegetable'],broccoli:['broccoli','cauliflower','floret'],pepper:['bell pepper','chili pepper','capsicum'],potato:['potato','sweet potato'],tomato:['tomato','cherry tomato'],cucumber:['cucumber','zucchini'],mushroom:['mushroom','shiitake'],herb:['herb','cilantro','parsley','basil'],citrus:['lemon','lime','citrus'],chicken:['chicken','poultry'],beef:['beef','steak','ground beef'],pork:['pork','bacon','sausage'],turkey:['turkey'],fish:['fish','fillet','salmon'],shrimp:['shrimp','prawn'],seafood:['seafood','mussel','clam'],egg:['egg','eggs'],tofu:['tofu','tempeh'],asian:['lemongrass','galangal','daikon','lotus root','rice noodles','scallion'],weight:['weight','weights','grams','gram','g flour','brown sugar','granulated sugar','ingredient weight'],terms:['sauté','saute','simmer','sear','whisk','fold','beat','blanch','drain','pat dry','season to taste','cooking terms'],chiffonade:['chiffonade','ribbons','herb ribbons'],julienne:['julienne','matchsticks','batonnet'],dice:['dice','diced','cubed'],mince:['mince','minced'],chop:['chop','chopped'],slice:['slice','sliced']};
 const tokens=Object.keys(aliases).filter(k=>q.includes(k)||aliases[k].some(a=>q.includes(a)));
 const matches=prepItems.filter(entry=>{const text=(entry[0]+' '+entry[1]).toLowerCase();return text.includes(q)||tokens.some(t=>aliases[t].some(a=>text.includes(a))||text.includes(t));});
 const measurementQuery=/measure|conversion|garlic equivalent|head of garlic|clove|produce yield|yield|teaspoon|tablespoon|tsp|tbsp|weight|grams|gram|flour|sugar/.test(q);
 const ranked=measurementQuery?matches.slice().sort((a,b)=>{const score=e=>{const title=e[0].toLowerCase();if(/garlic, ginger|ingredient equivalents/.test(title)&&/garlic|clove|head/.test(q))return 0;if(/produce yield/.test(title)&&/produce|yield|lemon|onion|carrot|pepper/.test(q))return 0;if(/ingredient weights/.test(title)&&/weight|gram|flour|sugar|onion|carrot|pepper/.test(q))return 0;if(/cooking terms/.test(title)&&/sauté|saute|simmer|sear|whisk|fold|beat|blanch|drain|pat dry|season/.test(q))return 0;if(/julienne|chop|mince|dice|chiffonade/.test(title)&&/julienne|matchstick|batonnet|chop|mince|dice|chiffonade|ribbon|slice/.test(q))return 0;if(/measurements & conversions|quick kitchen spoon/.test(title))return 1;return 2;};return score(a)-score(b);}):matches;
 const shown=ranked.length?ranked.slice(0,5):prepItems.filter(entry=>(entry[0]+' '+entry[1]).toLowerCase().split(/[^a-z0-9]+/).some(word=>word.length>3&&q.includes(word))).slice(0,4);
 if(!shown.length){prepSearchResults.innerHTML='<article class="prep-result-card"><h4>🔎 No exact match yet</h4><p>Try a broader term such as “chop,” “wash,” “measurements,” “ginger,” or “rice.” Chef Saffron is still building her prep notes.</p></article>';return;}
 prepSearchResults.innerHTML=shown.map(entry=>'<article class="prep-result-card"><h4>'+entry[0].replace(/&/g,'&amp;').replace(/</g,'&lt;')+'</h4><p>'+entry[1].replace(/&/g,'&amp;').replace(/</g,'&lt;')+'</p></article>').join('');
}
// Robust Prep Counter search: delegate events and surface errors in the result area.
document.addEventListener('submit',event=>{
 if(!event.target || event.target.id!=='prepSearchForm') return;
 event.preventDefault();
 const input=document.getElementById('prepSearchInput');
 const output=document.getElementById('prepSearchResults');
 try {
  if(typeof searchPrep!=='function') throw new Error('Search function did not load.');
  searchPrep(input ? input.value : '');
 } catch(err) {
  if(output) output.innerHTML='<article class="prep-result-card"><h4>⚠️ Chef Saffron found a search hiccup</h4><p>The search encountered an error: '+String(err && err.message ? err.message : err).replace(/[&<>]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;'}[c]))+'. Please tell us this message so we can fix the exact cause.</p></article>';
 }
}, true);
document.addEventListener('click',event=>{
 const button=event.target && event.target.closest ? event.target.closest('[data-prep-query]') : null;
 if(!button) return;
 const input=document.getElementById('prepSearchInput');
 const output=document.getElementById('prepSearchResults');
 try {
  if(input) input.value=button.dataset.prepQuery || '';
  if(typeof searchPrep!=='function') throw new Error('Search function did not load.');
  searchPrep(input ? input.value : '');
 } catch(err) {
  if(output) output.innerHTML='<article class="prep-result-card"><h4>⚠️ Chef Saffron found a search hiccup</h4><p>The search encountered an error: '+String(err && err.message ? err.message : err).replace(/[&<>]/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;'}[c]))+'. Please tell us this message so we can fix the exact cause.</p></article>';
 }
});
let prepPepperTaps=0;
document.getElementById('prepPepperButton').addEventListener('click',()=>{if(activeRoom!=='prep')return;prepPepperTaps++;const result=document.getElementById('prepSecretResult');if(prepPepperTaps<3){result.textContent=prepPepperTaps===1?'The tiny pepper has a little mark on its stem…':'It looks like a tiny chef’s hat is drawn on the back. One more inspection?';return;}result.textContent='🌶️ SECRET DISCOVERED — Chef Saffron’s pocket note: “A cook who prepares well can improvise without panic. But never rush a knife, never guess whether food is cooked safely, and never let a garnish distract you from the timer.” At the bottom, in smaller writing: “P.S. If Rook asks, this pepper was never here.”';document.getElementById('prepPepperButton').textContent='🌶️ Secret discovered!';document.getElementById('prepPepperButton').disabled=true;});
let prepArchiveTaps=0;
document.getElementById('prepArchiveButton').addEventListener('click',()=>{if(activeRoom!=='prep')return;prepArchiveTaps++;const result=document.getElementById('prepArchiveResult');if(prepArchiveTaps===1){result.textContent='The paper is older than the Prep Counter. There is a faded symbol: a key crossed with a spoon.';return;}if(prepArchiveTaps===2){result.textContent='Under the symbol, someone wrote: “When the kitchen forgets, the ingredients remember.” The last line is sealed with a smudged mark.';return;}result.innerHTML='🗝️ <strong>ARCHIVE CLUE FOUND — Fragment 01</strong><br>“Before the Archive was locked, recipes were used to preserve more than instructions. Each one kept a memory of the person, place, or promise that created it.”<br><em>In the margin, in Chef Saffron’s handwriting:</em> “I didn’t write this. But I know that key symbol… and I’m not telling Rook until we know who left it.”';document.getElementById('prepArchiveButton').textContent='📜 Fragment discovered!';document.getElementById('prepArchiveButton').disabled=true;});

document.querySelectorAll('.hotspot').forEach(button=>{
 button.addEventListener('click',()=>openRoom(button.dataset.room));
});
const archivistFragments={
 'ash flour':{title:'📜 Fragment I — Ash Flour',text:'The Archivist lowers their voice: “This is not a standard baking ingredient. The phrase appears in a recipe fragment with its measurements deliberately scraped away. In the margin, someone wrote: ‘A recipe can survive even when its author is erased.’”\n\nArchive clue: the missing page was removed from a collection catalogued before the guilds began controlling rare recipes.'},
 'winter sugar':{title:'📜 Fragment II — Winter Sugar',text:'The Archivist: “Winter sugar is not a recognized ingredient name in the ordinary baking records. Here it is a code phrase, repeated beside a note about sweetness being used to preserve a memory—not a fruit.”\n\nArchive clue: three different copies use the same phrase, but each copy has a different author’s name crossed out.'},
 'third bell':{title:'📜 Fragment III — The Third Bell',text:'The Archivist checks the page number twice. “This fragment contains an instruction to begin only after the third bell. No oven temperature. No ingredient list. Just a warning not to let the guild’s record-keeper see the finished page.”\n\nArchive clue: someone expected the recipe to be confiscated.'},
 'missing page':{title:'📜 Fragment IV — The Missing Page',text:'The Archivist: “The binding has a clean tear, not the ragged edge of age. Someone removed this page carefully. The surviving line reads: ‘Share the recipe freely, or it will become a weapon of power.’”\n\nArchive clue: the page was removed intentionally, and the archive’s official index pretends it never existed.'},
 'forbidden recipe':{title:'📜 Rare Discovery — The Recipe That Shouldn’t Exist',text:'For a moment, the Archivist says nothing. Then: “I found a reference to a recipe erased from every official catalog. It was not forbidden because it was dangerous to cook. It was forbidden because it could connect people, places, and histories the guilds wanted kept separate.”\n\nA final note appears beneath the torn edge: ‘When the fragments are gathered, look for the name that was removed from the first page.’\n\n📚 The Forbidden Recipe Archive — Record status: deliberately erased. This is only a clue; the recipe itself remains incomplete.'}
};
document.getElementById('archivistSearchForm').addEventListener('submit',event=>{
 event.preventDefault();
 if(activeRoom!=='baking')return;
 const q=archivistSearchInput.value.trim().toLowerCase();
 const fragmentAliases={
  'ash flour':['ash','ash flour','scraped measurements','erased author'],
  'winter sugar':['winter','winter sugar','sweetness memory','crossed out name'],
  'third bell':['bell','third bell','third chime','confiscated recipe'],
  'missing page':['missing page','torn page','clean tear','removed page','erased index'],
  'forbidden recipe':['forbidden recipe','shouldn’t exist','shouldnt exist','erased recipe','forbidden archive','guilds','recipe archive']
};
 const key=Object.keys(archivistFragments).find(k=>(q===k || q.includes(k) || (fragmentAliases[k]||[]).some(alias=>q.includes(alias))));
 if(key){
  const fragment=archivistFragments[key];
  tipBox.textContent=fragment.title+'\n\n'+fragment.text;
  tipBox.hidden=false;
  archivistSearchStatus.textContent='A sealed archive fragment has been recovered.';
  tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});
  return;
 }
 const bakingGuides=[
  {title:'🌾 Flour & Measuring',keys:['flour','all-purpose','all purpose','measure flour','measuring flour'],text:'For 1 cup all-purpose flour, use about 120 g. Spoon flour lightly into the measuring cup and level the top—don’t scoop straight from the bag or pack it down. Too much flour can make cakes, cookies, and muffins dry.'},
  {title:'🧁 Baking Powder',keys:['baking powder','powder for baking','leavening'],text:'Baking powder helps baked goods rise. If it is old, your cake or muffins may rise poorly. Store it tightly closed in a cool, dry place. Baking powder and baking soda are different and are not interchangeable 1:1.'},
  {title:'🥄 Baking Soda',keys:['baking soda','bicarbonate of soda'],text:'Baking soda needs an acidic ingredient in the recipe to help produce lift. It is stronger than baking powder, so don’t swap them 1:1 without adjusting the recipe.'},
  {title:'🧈 Butter',keys:['butter','melted butter','softened butter'],text:'Use butter in the form your recipe asks for. Softened butter can be creamed with sugar to trap air; melted butter usually gives a denser, chewier result. One US stick is ½ cup (8 tablespoons, about 113 g).'},
  {title:'🥚 Eggs',keys:['egg','eggs','egg substitute'],text:'Eggs can add structure, moisture, richness, and lift. Use the size specified by the recipe when possible. Replacing eggs depends on what you’re baking, so a swap that works in muffins may not work in a sponge cake.'},
  {title:'🥛 Buttermilk Substitution',keys:['buttermilk','milk substitute','lemon juice'],text:'To make a quick substitute for 1 cup buttermilk, put 1 tablespoon lemon juice or vinegar in a measuring cup, add milk to the 1-cup line, and let it stand for 5–10 minutes. This works well in many pancakes, muffins, and quick breads.'},
  {title:'🔥 Oven Temperature & Preheating',keys:['oven','oven temperature','preheat','temperature','baking time'],text:'Preheat the oven before the pan goes in. Use the temperature in your recipe and the center rack unless it says otherwise. Ovens vary, so start checking near the earliest suggested time; avoid opening the door repeatedly.'},
  {title:'🍪 Cookies',keys:['cookie','cookies','spread','flat cookies'],text:'Cookies that spread too much may have warm dough, too little flour, or a very warm baking sheet. If the recipe allows, chill the dough and use a cool pan. Measure flour by spooning it into the cup and leveling it.'},
  {title:'🧁 Muffins & Overmixing',keys:['muffin','muffins','overmix','mixing'],text:'For tender muffins, stir wet and dry ingredients together only until no large dry patches remain. A few small lumps are fine. Overmixing can develop gluten and make muffins tough.'},
  {title:'⚖️ Baking Measurements',keys:['measurement','measurements','conversion','conversions','tablespoon','teaspoon','cups','grams'],text:'US quick chart: 1 cup = 16 tablespoons = 48 teaspoons; 8 tablespoons = ½ cup; 4 tablespoons = ¼ cup; 12 tablespoons = ¾ cup; 1 tablespoon = 3 teaspoons; 1 US stick butter = ½ cup = 8 tablespoons = about 113 g. One US cup all-purpose flour is about 120 g, while 1 cup granulated sugar is about 200 g. Grams-to-cups depend on the ingredient, so use a kitchen scale when accuracy matters. Ask the helper things like “8 tablespoons to cups,” “3 teaspoons,” or “100 g flour in cups.”'},
  {title:'🔄 Ingredient Substitutions',keys:['substitution','substitute','swap','swaps','replacement'],text:'A substitution can change taste, moisture, texture, and rise. Tell the search the ingredient you’re missing for more specific guidance. Don’t assume baking soda, baking powder, flour types, or liquid sweeteners can be swapped in equal amounts.'},
  {title:'🍰 Cakes',keys:['cake','cakes','sponge cake','birthday cake','layer cake','pound cake'],text:'For a tender cake, measure flour carefully, use the ingredient temperatures listed, and avoid overmixing after adding flour. Grease and line pans as directed. Check doneness with a toothpick near the center; a few moist crumbs can be fine, but wet batter means it needs longer.'},
  {title:'🧁 Cupcakes',keys:['cupcake','cupcakes'],text:'Fill cupcake wells about two-thirds full unless the recipe says otherwise. Bake on the center rack and begin checking near the earliest time listed. Let cupcakes cool completely before frosting, or the frosting may melt.'},
  {title:'🍫 Brownies',keys:['brownie','brownies','fudgy brownies','cakey brownies'],text:'For fudgy brownies, avoid overbaking; the center should no longer look like raw batter, and a tester may have moist crumbs. Let the pan cool before slicing for cleaner edges. The balance of fat, flour, eggs, and chocolate affects fudgy versus cakey texture.'},
  {title:'🍞 Bread & Quick Breads',keys:['bread','quick bread','banana bread','zucchini bread','loaf'],text:'Quick breads use baking powder or baking soda rather than yeast. Mix only until the ingredients come together, and check the center for doneness. Yeast breads are different: kneading and rising times help develop their structure.'},
  {title:'🥐 Yeast & Rising',keys:['yeast','active dry yeast','instant yeast','proofing','rise dough','dough rising'],text:'Yeast needs moisture, food, and suitable warmth to work. Very hot liquid can damage it; follow the package or recipe temperature guidance. Let dough rise until it reaches the size or texture described, since room temperature changes rising time.'},
  {title:'🍥 Frosting & Icing',keys:['frosting','icing','buttercream','glaze','cream cheese frosting'],text:'Let cakes and cupcakes cool completely before frosting. Add powdered sugar gradually to thicken buttercream, or add a tiny amount of liquid to loosen it. Cream-cheese frosting is perishable and should be refrigerated.'},
  {title:'🥧 Pies & Pie Crust',keys:['pie','pies','pie crust','pastry crust','tart'],text:'Keep pie dough cool and handle it gently to reduce toughness. Chill it if the recipe directs, and avoid stretching the dough into the pan. For fruit pies, bubbling filling is a useful sign that the center has heated through.'},
  {title:'🍪 Pastry & Puff Pastry',keys:['pastry','puff pastry','phyllo','filo'],text:'Keep puff pastry cold so its layers can rise in the oven. Handle it gently and follow package thawing directions. Phyllo is much thinner and usually needs sheets layered with fat; it is not a direct substitute for puff pastry.'},
  {title:'🍰 Cheesecake',keys:['cheesecake','cheese cake'],text:'Use the ingredient temperatures and mixing method in your recipe. Avoid whipping in excess air, which can contribute to cracks. Cool gradually as directed; cheesecake needs refrigeration and is often best after several hours of chilling.'},
  {title:'🍬 Sugar & Sweeteners',keys:['sugar','granulated sugar','brown sugar','powdered sugar','icing sugar','honey','maple syrup','molasses'],text:'Sugar adds sweetness but also affects moisture, browning, spread, and texture. Brown sugar contains molasses and adds moisture; powdered sugar is finely ground and often contains starch. Liquid sweeteners can change a recipe’s moisture, so use a tested substitution.'},
  {title:'🍫 Cocoa & Chocolate',keys:['cocoa','cocoa powder','chocolate','chocolate chips','dark chocolate','white chocolate'],text:'Cocoa powder and melted chocolate contribute differently: chocolate adds cocoa butter and richness, while cocoa powder is more concentrated and drier. Natural and Dutch-process cocoa are not always interchangeable because acidity matters in some recipes.'},
  {title:'🌼 Vanilla & Extracts',keys:['vanilla','vanilla extract','almond extract','extract'],text:'Extracts add concentrated flavor, so measure them rather than pouring freely. Vanilla can round out cakes, cookies, custards, and frosting. Avoid replacing a large amount of liquid in a recipe with extract.'},
  {title:'🥛 Milk, Cream & Dairy',keys:['milk','whole milk','heavy cream','heavy whipping cream','sour cream','yogurt','cream cheese'],text:'Dairy adds moisture, fat, acidity, and tenderness depending on the product. Sour cream and yogurt can add moisture and acidity, but they are not automatic equal-volume replacements for every dairy ingredient. Refrigerate perishable dairy promptly.'},
  {title:'🫒 Oil vs. Butter',keys:['oil','vegetable oil','olive oil','butter versus oil','oil vs butter'],text:'Oil stays liquid at room temperature and often makes cakes moist; butter contributes flavor and can trap air when creamed with sugar. They are not always equal-volume substitutes because butter contains water and milk solids.'},
  {title:'🧂 Salt & Spices',keys:['salt','cinnamon','nutmeg','spices','pumpkin spice'],text:'Salt helps balance sweetness and bring out flavor. Spices lose aroma over time, so store them sealed away from heat and light. Measure strong spices carefully and adjust only when you understand how they affect the recipe.'},
  {title:'🍌 Fruit in Baking',keys:['fruit','berries','blueberries','strawberries','banana','applesauce','apple'],text:'Fresh or frozen fruit can add moisture to batters. Frozen berries can often be added without thawing; fold gently to reduce streaking. Fruit purées such as applesauce change moisture and structure, so replacing all the fat with purée may make the result denser.'},
  {title:'🧁 Pan Size & Preparation',keys:['pan size','cake pan','baking pan','grease pan','parchment paper','lining pan'],text:'Use the pan size specified whenever possible. A smaller or deeper pan may need more time, while a larger, shallower pan may bake faster. Grease or line the pan as directed, and do not fill it to the rim.'},
  {title:'🌡️ How to Tell When It’s Done',keys:['done','doneness','toothpick test','undercooked','overbaked','raw in middle'],text:'Use the recipe’s visual cues and timing, not time alone. Cakes often spring back lightly and a tester near the center should not carry wet batter. Breads may need a longer bake than their browned crust suggests; follow recipe-specific checks.'},
  {title:'❄️ Cooling & Storing Baked Goods',keys:['cooling','cool cake','store cake','store cookies','freeze baked goods','freezing cake'],text:'Follow the recipe’s cooling instructions before removing or slicing baked goods. Store items according to their ingredients: cream-cheese frosting, custards, and other perishable fillings need refrigeration. Wrap cooled items well before freezing and label them with the date.'},
  {title:'🍰 General Baking Basics',keys:['baking','bake','basics','help'],text:'Read the full recipe first, preheat the oven, and measure ingredients before mixing. Follow directions for ingredient temperature and mixing time. Let baked goods cool as directed; cutting too early can affect texture.'}
 ];
 const normalized=q.replace(/[’']/g,'').replace(/[^a-z0-9 ]/g,' ').replace(/\s+/g,' ').trim();
 // Everyday US volume conversions and common ingredient-weight conversions.
 const volumeMatch=normalized.match(/(\d+(?:\.\d+)?)\s*(tablespoons?|tbsp|teaspoons?|tsp|cups?|fluid ounces?|fl oz|pints?|quarts?|gallons?)\b/);
 if(volumeMatch && /\b(equal|equals|convert|conversion|to|in|how many|what is|whats|equivalent|make|makes)\b/.test(normalized)){
  const amount=Number(volumeMatch[1]);
  const unit=volumeMatch[2].replace(/s$/,'').replace('tablespoon','tbsp').replace('teaspoon','tsp').replace('cup','cup').replace('fluid ounce','fl oz').replace('fl oz','fl oz');
  const toCups={'tbsp':1/16,'tsp':1/48,'cup':1,'fl oz':1/8,'pint':2,'quart':4,'gallon':16};
  const key=unit==='tbsp'?'tbsp':unit==='tsp'?'tsp':unit;
  const cups=amount*toCups[key];
  const fmt=n=>Number(n.toFixed(4)).toString();
  let answer='';
  if(key==='tbsp') answer=`${amount} tablespoon${amount===1?'':'s'} = ${fmt(amount*3)} teaspoon${amount*3===1?'':'s'} = ${fmt(amount/16)} US cup${amount/16===1?'':'s'}.`;
  else if(key==='tsp') answer=`${amount} teaspoon${amount===1?'':'s'} = ${fmt(amount/3)} tablespoon${amount/3===1?'':'s'} = ${fmt(amount/48)} US cup${amount/48===1?'':'s'}.`;
  else if(key==='cup') answer=`${amount} US cup${amount===1?'':'s'} = ${fmt(amount*16)} tablespoon${amount*16===1?'':'s'} = ${fmt(amount*48)} teaspoon${amount*48===1?'':'s'} = ${fmt(amount*8)} fluid ounces.`;
  else if(key==='fl oz') answer=`${amount} US fluid ounce${amount===1?'':'s'} = ${fmt(amount*2)} tablespoon${amount*2===1?'':'s'} = ${fmt(amount/8)} US cup${amount/8===1?'':'s'}.`;
  else if(key==='pint') answer=`${amount} US pint${amount===1?'':'s'} = ${fmt(amount*2)} US cup${amount*2===1?'':'s'} = ${fmt(amount*32)} tablespoon${amount*32===1?'':'s'}.`;
  else if(key==='quart') answer=`${amount} US quart${amount===1?'':'s'} = ${fmt(amount*4)} US cup${amount*4===1?'':'s'} = ${fmt(amount*64)} tablespoon${amount*64===1?'':'s'}.`;
  else if(key==='gallon') answer=`${amount} US gallon${amount===1?'':'s'} = ${fmt(amount*16)} US cup${amount*16===1?'':'s'} = ${fmt(amount*256)} tablespoon${amount*256===1?'':'s'}.`;
  tipBox.textContent='🥄 Baking Measurement Helper\n\n'+answer+'\n\nThese are US customary volume measurements. For grams, the weight depends on the ingredient; ask for a specific ingredient such as “100 g flour in cups.”';
  tipBox.hidden=false;archivistSearchStatus.textContent='Volume conversion found.';tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});return;
 }
 if(/\b(stick|sticks)\s+(of\s+)?butter\b/.test(normalized) || /\b(what is|whats|how much|convert).*(butter).*(cup|tablespoon|gram)/.test(normalized)){
  tipBox.textContent='🧈 US Butter Quick Reference\n\n1 US stick butter = ½ cup = 8 tablespoons = 24 teaspoons = about 113 g.\n2 sticks = 1 cup = 16 tablespoons = about 227 g.\n\nButter weights are approximate; package sizes can differ by country.';
  tipBox.hidden=false;archivistSearchStatus.textContent='Butter measurement found.';tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});return;
 }
 // Ingredient-specific gram conversions and common baking swaps.
 const weightPerCup={
  'flour':120,'all purpose flour':120,'all-purpose flour':120,'plain flour':120,'whole wheat flour':128,
  'granulated sugar':200,'white sugar':200,'sugar':200,'brown sugar':220,'packed brown sugar':220,'powdered sugar':120,'icing sugar':120,
  'cocoa powder':85,'cocoa':85,'butter':227,'chocolate chips':170,'rolled oats':90,'oats':90,'honey':340,'water':240,'milk':240,'rice':185,'almond flour':96
 };
 const conversionMatch=normalized.match(/(\d+(?:\.\d+)?)\s*(?:g|gram|grams)\s+(?:of\s+)?(.+?)(?:\s+(?:in|to|into)\s+(?:us\s+)?cups?)?$/);
 if(conversionMatch && /\b(cup|cups|convert|conversion|in cups|to cups)\b/.test(normalized)){
  const grams=Number(conversionMatch[1]);
  let ingredient=conversionMatch[2].replace(/\b(in|to|into)\s+(?:us\s+)?cups?\b/g,'').trim();
  ingredient=ingredient.replace(/^(of\s+)/,'');
  const weightKey=Object.keys(weightPerCup).find(k=>ingredient===k || ingredient.includes(k) || k.includes(ingredient));
  if(weightKey && grams>=0){
   const cups=grams/weightPerCup[weightKey];
   const tablespoons=cups*16;
   const fraction=(Math.round(cups*16)/16);
   let cupText;
   if(fraction===0)cupText='less than 1/16 cup';
   else if(Math.abs(cups-fraction)<0.008){const whole=Math.floor(fraction);const num=Math.round((fraction-whole)*16);const gcd=(a,b)=>b?gcd(b,a%b):a;const d=gcd(num,16);cupText=(whole?whole+' ':'')+(num?(num/d)+'/'+(16/d)+' cup':'cup');}
   else cupText=cups.toFixed(3)+' cups (about '+tablespoons.toFixed(1)+' tablespoons)';
   tipBox.textContent='⚖️ '+grams+' g of '+ingredient+'\n\nApproximately '+cupText+'. This estimate uses about '+weightPerCup[weightKey]+' g per US cup for '+weightKey+'. Ingredient brands, packing, and measuring methods can change the result; a kitchen scale is most accurate.';
   tipBox.hidden=false;archivistSearchStatus.textContent='Measurement conversion found.';tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});return;
  }
 }
 const swapGuides=[
  {keys:['egg','eggs','replace egg','egg swap','egg substitute'],title:'🥚 Egg swaps',text:'For moist cakes, muffins, and quick breads, try ¼ cup unsweetened applesauce per egg, or ¼ cup mashed banana if its flavor fits. These swaps do not work well for every recipe, especially meringues, soufflés, or recipes where eggs provide most of the structure.'},
  {keys:['butter','replace butter','butter swap','butter substitute'],title:'🧈 Butter swaps',text:'In many cakes and quick breads, neutral oil can sometimes replace melted butter, but the result may be less buttery and have a different texture. Butter contains water and milk solids, so it is not a universal equal-volume swap. Tell me what you are baking for a more specific suggestion.'},
  {keys:['buttermilk','replace buttermilk','buttermilk swap'],title:'🥛 Buttermilk swap',text:'For 1 cup buttermilk, add 1 tablespoon lemon juice or white vinegar to a measuring cup, then add milk to the 1-cup line. Stir and wait 5–10 minutes. This works well in many pancakes, muffins, and quick breads.'},
  {keys:['sour cream','replace sour cream','sour cream swap'],title:'🥣 Sour cream swap',text:'Plain unsweetened yogurt can often replace sour cream in cakes, muffins, and quick breads in the same amount. Greek yogurt is thicker; if needed, stir in a little milk to loosen it. Flavor and texture may vary.'},
  {keys:['milk','replace milk','milk swap'],title:'🥛 Milk swap',text:'In many baking recipes, unsweetened, unflavored plant milk can replace dairy milk in a similar amount. Choose one that fits the flavor of the recipe. Sweetened or strongly flavored varieties can change the result.'},
  {keys:['baking powder','replace baking powder','baking powder swap'],title:'🧁 Baking powder swap',text:'Baking powder and baking soda are not interchangeable 1:1. Baking soda needs an acid in the recipe, and changing the leavening can affect taste and rise. If you tell me the recipe and amount, I can help assess options.'},
  {keys:['flour','replace flour','flour swap','flour substitute'],title:'🌾 Flour swaps',text:'Flours behave differently. Whole-wheat flour can make baked goods denser; almond or coconut flour usually cannot replace all-purpose flour cup-for-cup. For best results, use a recipe written for the flour you have.'}
 ];
 const swapQuery=swapGuides.find(g=>g.keys.some(k=>normalized===k || normalized.includes(k)) && /swap|substitut|replace|instead|out of|missing|alternative/.test(normalized));
 if(swapQuery){tipBox.textContent=swapQuery.title+'\n\n'+swapQuery.text;tipBox.hidden=false;archivistSearchStatus.textContent='Ingredient swap advice found.';tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});return;}
 const guide=bakingGuides.find(g=>g.keys.some(k=>normalized===k || normalized.includes(k) || k.includes(normalized)));
 if(guide){
  tipBox.textContent=guide.title+'\n\n'+guide.text+'\n\n— Baking Corner Notes';
  tipBox.hidden=false;
  archivistSearchStatus.textContent='Baking help found.';
  tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});
  return;
 }
 archivistSearchStatus.textContent='No match yet. Try flour, sugar, chocolate, cake, cupcakes, brownies, bread, frosting, pie crust, yeast, oven temperature, measurements, or a secret clue like “torn page”.';
});
list.addEventListener('click',event=>{
 const button=event.target.closest('button[data-tip-index],button[data-random-thing],button[data-safety-search]');
 if(!button)return;
 if(button.dataset.safetySearch){
  tipBox.hidden=false;
  const safetyVoices=[
   {name:'💚 Lil Dino says',line:'“A WEAPON? In my fridge? I was prepared for lemons, suspicious leftovers, and one yogurt with a mysterious past—not an action-movie audition. Hammy, please return the drama to the cinema.”'},
   {name:'💜 Juniper says',line:'“I asked the garden for thyme, not a thriller plot. This fridge is for keeping food fresh, not storing dangerous surprises. Let’s keep the real world safer than the punchline.”'},
   {name:'🧡 Chef Saffron says',line:'“That ingredient is NOT on today’s menu. The only thing we’re firing in this kitchen is up the stove—and even that requires supervision. Let’s keep dangerous things away from the kitchen.”'},
   {name:'📜 The Archivist says',line:'“Entry rejected: this is a refrigerator, not an armory. The archive recommends lemons, leftovers, and considerably fewer action-movie props.”'},
   {name:'🐹 Ham says',line:'“I searched for snacks and somehow found the bonus level. I am a tiny hamster, not a tiny action hero. Can we go back to crackers?”'}
  ];
  const voice=safetyVoices[Math.floor(Math.random()*safetyVoices.length)];
  tipBox.innerHTML='<div class="tip-card"><h3>'+voice.name+'</h3><p>'+voice.line+'</p><h3>💚 A real-world note</h3><p>This is a fictional Easter egg, not a judgment about you or why you searched. If you or someone you know is struggling or needs someone to talk to in the U.S., call or text <strong>988</strong> for free, confidential support through the 988 Suicide & Crisis Lifeline.</p><p>If someone is in immediate danger, contact local emergency services.</p></div>';
  tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});return;
 }
 if(button.dataset.randomThing){
  const q=button.dataset.randomThing.toLowerCase();
  const reactions={
   chair:'💚 Lil Dino: A chair? In the fridge? Sit down and think about your choices.\n💜 Juniper: It belongs in a room with a table, not beside the tofu.\n📜 The Archivist: I have documented stranger things. Unfortunately.\n🐹 Ham: Is it a snack chair? I would like to file a request.',
   toaster:'💚 Lil Dino: A toaster? The fridge is for keeping food cold, not launching hot bread into the air.\n🧡 Chef Saffron: Keep appliances outside the fridge, please.\n🐹 Ham: Tiny bread cannon detected. I support this from a safe distance.',
   sock:'💚 Lil Dino: A sock? This is a refrigerator, not the laundry basket.\n💜 Juniper: I refuse to identify whether it is fresh produce.\n🐹 Ham: If it smells like cheese, that does not make it cheese.',
   'rubber duck':'💚 Lil Dino: A rubber duck? Finally, a fridge inspector with absolutely no qualifications.\n📜 The Archivist: I will record this incident under “unexplained poultry-shaped object.”\n🐹 Ham: Can it approve snacks? No? Then why is it here?',
   spoon:'🧡 Chef Saffron: A spoon belongs in a drawer, not in the fridge by itself.\n💚 Lil Dino: Unless it is chilling with dessert. I will allow one exception.\n🐹 Ham: I was told there would be pudding.',
   banana:'💚 Lil Dino: A banana! Finally, a real food. But the fridge may darken its peel; let it ripen on the counter first if it is still green.\n💜 Juniper: Once ripe, you can refrigerate it to slow further ripening, even if the peel darkens.\n🐹 Ham: This Easter egg is technically a snack. Excellent.',
   microwave:'🧡 Chef Saffron: The microwave goes on a counter, not in the fridge.\n💚 Lil Dino: I am not explaining why we cannot chill the entire appliance.\n🐹 Ham: Does it make leftovers warm? I have a follow-up question.',
   toilet:'💚 Lil Dino: No. Just no. This is a kitchen.\n📜 The Archivist: I am closing this record for the sake of public morale.\n🐹 Ham: I am not taste-testing anything associated with this search.',
   brick:'💚 Lil Dino: A brick? Not edible. Not fridge-friendly. Strong candidate for a garden wall, though.\n💜 Juniper: It could support a raised herb bed. Keep it away from the lettuce.\n🐹 Ham: Too crunchy. Zero stars.',
   'remote control':'💚 Lil Dino: A remote control? The fridge does not have channels.\n📜 The Archivist: I have pressed every button. The yogurt remains unchanged.\n🐹 Ham: Can it open the snack drawer? Asking for a friend.',
   'paper clip':'📜 The Archivist: A paper clip is for organizing documents, not organizing leftovers.\n💚 Lil Dino: Please do not use it to seal food containers.\n🐹 Ham: Tiny metal noodle. Would not eat.',
   'left shoe':'💚 Lil Dino: A left shoe? The fridge is not a closet.\n💜 Juniper: Please find its partner before either of them gets near the produce.\n🐹 Ham: If there is a right shoe, I am not eating either one.',
   "lamp":"💚 Lil Dino: A lamp? The fridge is not a reading nook.\n📜 The Archivist: Logged under: objects that require electricity, not refrigeration.\n🐹 Ham: Does it light up the snack drawer? Important question.",
   "pillow":"💜 Juniper: A pillow belongs somewhere dry and comfortable, far from the produce drawer.\n💚 Lil Dino: Unless your lettuce needs a nap. It does not.\n🐹 Ham: Finally, a soft object I cannot eat. Growth.",
   "book":"📜 The Archivist: A book in the fridge? I appreciate preserving knowledge, but this is not the library.\n💚 Lil Dino: Please don't refrigerate the plot.\n🐹 Ham: Does it have pictures of snacks?",
   "phone":"💚 Lil Dino: Your phone does not need to chill beside the cheese.\n📜 The Archivist: I refuse to document another screen with condensation.\n🐹 Ham: Can it order snacks? Then we may negotiate.",
   "keyboard":"📜 The Archivist: A keyboard is not a food storage container.\n💚 Lil Dino: Crumbs belong on the keyboard, apparently, but not the other way around.\n🐹 Ham: I only press keys that spell S-N-A-C-K.",
   "umbrella":"💜 Juniper: An umbrella is for rain, not refrigerator humidity.\n💚 Lil Dino: Unless the lettuce forecast says showers. It doesn't.\n🐹 Ham: Can it shield me from salad?",
   "rock":"💚 Lil Dino: A rock. Cold already, probably. Still not an ingredient.\n💜 Juniper: It could be useful in a garden, but not on the carrots.\n🐹 Ham: Too crunchy. No snack potential.",
   "rocking chair":"💚 Lil Dino: A rocking chair? The fridge is not a porch.\n📜 The Archivist: The chair rocked. The yogurt did not.\n🐹 Ham: I require a tiny rocking chair for quality control.",
   "teddy bear":"🐹 Ham: A teddy bear! Finally, a colleague who understands hugging snacks.\n💚 Lil Dino: It is a toy, Ham. Not a food group.\n📜 The Archivist: Plush visitor recorded. No refrigeration required.",
   "hamster":"🐹 Ham: A hamster? I would like to point out that I am the official snack inspector.\n💚 Lil Dino: Nobody is putting a pet in the fridge.\n🧡 Chef Saffron: Animals stay safely out of food storage areas.",
   "dinosaur":"💚 Lil Dino: A dinosaur? Finally, someone who understands my brand.\n📜 The Archivist: If fossilized, it still does not belong beside the yogurt.\n🐹 Ham: Does it know where the snacks are?",
   "cactus":"💜 Juniper: A cactus needs suitable light and care, not a spot between the eggs and milk.\n💚 Lil Dino: Please do not store your houseplants with your groceries.\n🐹 Ham: Spiky. I shall admire it from over here.",
   "sunglasses":"💚 Lil Dino: Sunglasses? The fridge light is not that bright.\n📜 The Archivist: Accessory filed under “not chilled dairy.”\n🐹 Ham: I look fabulous in tiny sunglasses, though.",
   "backpack":"💚 Lil Dino: Your backpack has no business camping beside the cabbage.\n📜 The Archivist: Please remove all mystery crumbs before returning it to normal storage.\n🐹 Ham: I checked. No snacks. One star.",
   "pencil":"📜 The Archivist: A pencil belongs with paper, not pickles.\n💚 Lil Dino: Please don't label food by carving into it.\n🐹 Ham: Can it draw me a cookie?",
   "eraser":"💚 Lil Dino: An eraser cannot erase food waste. Use the leftovers instead.\n📜 The Archivist: The search has been recorded and cannot be rubbed out.\n🐹 Ham: Can it erase the evidence of my snack?",
   "wallet":"💚 Lil Dino: Your wallet is not a lunchbox.\n📜 The Archivist: Money may be useful for groceries; it is not itself a refrigerator ingredient.\n🐹 Ham: I accept payment in crackers.",
   "bicycle":"💚 Lil Dino: A bicycle in the fridge? That's an ambitious way to save on parking.\n💜 Juniper: Please keep outdoor equipment away from food.\n🐹 Ham: I am not riding it to fetch snacks.",
   "skateboard":"💚 Lil Dino: The fridge is not a skate park. The shelves are not ramps.\n📜 The Archivist: No tricks were performed during this inspection.\n🐹 Ham: I would fall off immediately. Next question.",
   "soap":"🧡 Chef Saffron: Soap belongs near the sink, away from uncovered food.\n💚 Lil Dino: Please don't wash your apples with a bar of hand soap.\n🐹 Ham: I will not be taste-testing the bubbles.",
   "shampoo":"💚 Lil Dino: Shampoo is for hair, not for marinating cabbage.\n🧡 Chef Saffron: Keep personal-care products separate from food.\n🐹 Ham: I have no hair-care qualifications.",
   "flower pot":"💜 Juniper: A flowerpot belongs with plants and soil, not ready-to-eat food.\n💚 Lil Dino: The basil has requested a different neighbor.\n🐹 Ham: Is there a snack buried in the dirt? Do not answer that.",
   "pizza box":"💚 Lil Dino: A pizza box is not a fridge ingredient, but leftover pizza inside it should be wrapped or placed in a covered container.\n🧡 Chef Saffron: Refrigerate perishable leftovers within two hours; use them within 3–4 days.\n🐹 Ham: Now this search has potential.",
   "lego brick":"💚 Lil Dino: A LEGO brick? Please keep tiny plastic bricks away from the food.\n📜 The Archivist: A small construction project has been denied refrigerator access.\n🐹 Ham: Not edible. I checked with my eyes.",
   "scissors":"🧡 Chef Saffron: Scissors belong in a clean utensil drawer, not loose in the fridge.\n💚 Lil Dino: They can open packaging. They cannot improve leftovers by intimidation.\n🐹 Ham: Sharp objects are outside my snack expertise.",
   "tape":"📜 The Archivist: Tape may label a container, but do not let adhesive touch the food.\n💚 Lil Dino: Please do not tape the fridge shut. We need the cheese.\n🐹 Ham: I am unable to chew through office supplies.",
   "key":"💚 Lil Dino: A key? This fridge is already unlocked. Please stop trying to open the yogurt.\n📜 The Archivist: No secret compartment has been found.\n🐹 Ham: Does it unlock the snack cabinet?",
   "candle":"💚 Lil Dino: A candle belongs on a safe surface, not in the fridge beside the butter.\n📜 The Archivist: Mood lighting rejected. Refrigerator lighting remains adequate.\n🐹 Ham: I will celebrate when there is cake.",
   "toy car":"💚 Lil Dino: Vroom? More like remove it from the fridge.\n📜 The Archivist: Vehicle parked illegally beside the pickles.\n🐹 Ham: I request a snack-sized race track.",
   "traffic cone":"💚 Lil Dino: A traffic cone? The lettuce lane is now closed.\n💜 Juniper: Please direct your gardening equipment elsewhere.\n🐹 Ham: I am too small to operate heavy traffic.",
   "wizard hat":"📜 The Archivist: A wizard hat has appeared. No spell can make it a vegetable.\n💚 Lil Dino: If it conjures dinner, we can talk.\n🐹 Ham: I cast Snackus Maximus.",
   "pirate hat":"💚 Lil Dino: Arrr, remove that hat from the fridge before it starts charging the cheese rent.\n📜 The Archivist: No treasure map found among the condiments.\n🐹 Ham: I claim the snack hoard!",
   "alien":"📜 The Archivist: Extraterrestrial visitor logged. Please declare any intergalactic perishables.\n💚 Lil Dino: We have enough mysteries without refrigerating an alien.\n🐹 Ham: Are space snacks better?",
   "dragon egg":"💚 Lil Dino: A dragon egg? Keep it away from the milk. We are not hatching anything in here.\n📜 The Archivist: Incubation conditions unknown. Record sealed.\n🐹 Ham: If it hatches, I am naming it Crumb.",
   "treasure chest":"📜 The Archivist: A treasure chest is not a food-safe storage container.\n💚 Lil Dino: If it contains leftovers, put them in a proper covered container.\n🐹 Ham: I hope the treasure is crackers.",
   "magic potion":"💚 Lil Dino: A magic potion? Label it clearly and do not store unknown substances with food.\n🧡 Chef Saffron: Non-food chemicals must stay separate from ingredients.\n🐹 Ham: I will not taste mystery liquids.",
   "cursed cookbook":"📜 The Archivist: This cookbook is cursed. The recipe calls for three onions and a legally questionable amount of glitter.\n💚 Lil Dino: Keep books out of the fridge. Keep glitter out of dinner.\n🐹 Ham: Does the curse include endless snacks?",
   "invisible sandwich":"🐹 Ham: I cannot see it, but I am willing to perform a visual inspection.\n💚 Lil Dino: That's not how invisible works, Ham.\n📜 The Archivist: Sandwich existence remains unverified.",
   "dinosaur fossil":"📜 The Archivist: A fossil has entered the record. It does not need to be chilled beside the eggs.\n💚 Lil Dino: Unless this is a very strange museum, take it out.\n🐹 Ham: Ancient snack? Probably not.",
   "missing snack stash":"🐹 Ham: I have no idea what you mean by my snack stash. The crumbs are circumstantial.\n💚 Lil Dino: Ham, you're holding the empty cookie jar.\n📜 The Archivist: Evidence logged. Case remains suspicious.",
   "toothbrush":"💚 Lil Dino: A toothbrush belongs in the bathroom, far from uncovered food.\n🧡 Chef Saffron: Keep personal-care items separate from food preparation and storage.\n🐹 Ham: I brush my teeth after snacks. Sometimes.",
   "hairbrush":"💚 Lil Dino: A hairbrush is not a fridge accessory.\n📜 The Archivist: Hair-related evidence will not be stored beside the dairy.\n🐹 Ham: I have fur. I use absolutely no brush.",
   "phone charger":"💚 Lil Dino: A phone charger cannot charge the strawberries.\n📜 The Archivist: Electrical accessories do not belong in food storage.\n🐹 Ham: Can it charge my snack battery?",
   "house key":"💚 Lil Dino: A house key? The door is over there.\n📜 The Archivist: Key filed under “not an ingredient.”\n🐹 Ham: Does it unlock the treat drawer?",
   "stuffed animal":"🐹 Ham: A stuffed animal! A friend who never steals snacks. Suspicious.\n💚 Lil Dino: Keep toys out of food storage, please.\n📜 The Archivist: Plush visitor logged.",
   "blanket":"💜 Juniper: A blanket is cozy, but it does not belong on the refrigerator shelves.\n💚 Lil Dino: The vegetables do not need a duvet.\n🐹 Ham: I do, though.",
   "pillowcase":"💚 Lil Dino: A pillowcase is not a produce bag unless it's clean and specifically repurposed for food-safe storage—which this search does not establish.\n🧡 Chef Saffron: Use clean, food-safe containers or bags.\n🐹 Ham: Too many fabric questions.",
   "empty plate":"🧡 Chef Saffron: An empty plate can go in a cupboard. Cover food before refrigerating it.\n💚 Lil Dino: This is a plate with no plot.\n🐹 Ham: I see no snack. One star.",
   "fork":"🧡 Chef Saffron: A fork belongs in a drawer unless it's part of a covered meal.\n💚 Lil Dino: It cannot stab the fridge into being more organized.\n🐹 Ham: I request a fork for my enormous imaginary cake.",
   "spatula":"🧡 Chef Saffron: Clean the spatula and put it away; don't leave utensils loose among stored food.\n💚 Lil Dino: It is not a tiny refrigerator paddle.\n🐹 Ham: Can it flip pancakes toward me?",
   "whisk":"🧡 Chef Saffron: A whisk belongs with your baking tools, not loose beside the milk.\n💚 Lil Dino: Stirring the fridge will not make it colder.\n🐹 Ham: I support whisking batter. I support eating batter less recklessly.",
   "measuring cup":"💚 Lil Dino: A measuring cup is for ingredients, not for measuring how much fridge space you've wasted.\n🧡 Chef Saffron: Store clean equipment in a drawer or cupboard.\n🐹 Ham: Measure one cup of snacks. Repeat as needed.",
   "cutting board":"🧡 Chef Saffron: Clean and store the cutting board after use; keep raw-meat prep separate from ready-to-eat foods.\n💚 Lil Dino: The board is not a shelf.\n🐹 Ham: I only cut snacks with my eyes.",
   "oven mitt":"💚 Lil Dino: An oven mitt is for hot pans, not cold cucumbers.\n🧡 Chef Saffron: Keep clean oven mitts in a dry drawer.\n🐹 Ham: I am already wearing imaginary mittens.",
   "dish sponge":"🧡 Chef Saffron: A sponge belongs at the sink and needs regular cleaning or replacement.\n💚 Lil Dino: Do not store it beside uncovered food.\n🐹 Ham: It looks like a snack. I will trust the label.",
   "dish towel":"💚 Lil Dino: A dish towel is not a blanket for your lettuce.\n🧡 Chef Saffron: Use clean towels and keep them away from raw-food drips.\n🐹 Ham: Towels are not edible. A difficult day.",
   "pot lid":"💚 Lil Dino: A pot lid is not a fridge roof.\n🧡 Chef Saffron: Cover stored food with a suitable lid or container.\n🐹 Ham: I was hoping it was a tiny cymbal.",
   "oven":"🧡 Chef Saffron: The oven stays in the kitchen, outside the refrigerator. Please don't move appliances around food.\n💚 Lil Dino: I am not chilling an entire oven.\n🐹 Ham: Too hot to be a snack.",
   "washing machine":"💚 Lil Dino: The washing machine belongs in the laundry room, not beside the yogurt.\n📜 The Archivist: Cycle completed: one confused search.\n🐹 Ham: Does it wash snack crumbs off?",
   "laundry basket":"💚 Lil Dino: A laundry basket in the fridge? That's a new level of meal prep.\n💜 Juniper: Keep laundry separate from food and food-contact surfaces.\n🐹 Ham: I refuse to sort socks.",
   "shoe":"💚 Lil Dino: A shoe is not a container, even if it has a roomy toe box.\n💜 Juniper: Please keep outdoor footwear away from produce.\n🐹 Ham: I will not eat anything that has walked outside.",
   "left shoe":"💚 Lil Dino: A left shoe? The fridge is not a closet.\n💜 Juniper: Please find its partner before either of them gets near the produce.\n🐹 Ham: If there is a right shoe, I am not eating either one.",
   "right shoe":"💚 Lil Dino: Ah, the missing partner. Now please reunite the shoes outside the fridge.\n📜 The Archivist: Pair restored. Refrigeration still unnecessary.\n🐹 Ham: No snack inside. Case closed.",
   "plant":"💜 Juniper: A houseplant needs its own care routine, not a spot beside the groceries.\n💚 Lil Dino: Keep potting soil away from food.\n🐹 Ham: I will admire the leaves from snack-safe distance.",
   "flower":"💜 Juniper: Flowers can be beautiful, but keep decorative stems and vase water separate from food.\n💚 Lil Dino: The fridge is not a bouquet cooler unless you're deliberately chilling flowers.\n🐹 Ham: Petals are not my preferred garnish.",
   "lego":"💚 Lil Dino: A LEGO brick? Please keep tiny plastic bricks away from food.\n📜 The Archivist: Construction has been denied refrigerator access.\n🐹 Ham: Not edible. I checked with my eyes.",
   "wallet":"💚 Lil Dino: Your wallet is not a lunchbox.\n📜 The Archivist: Money may buy groceries; it is not itself a refrigerator ingredient.\n🐹 Ham: I accept payment in crackers.",
   "computer mouse":"📜 The Archivist: A computer mouse has been found. No cheese was involved, despite the name.\n💚 Lil Dino: It belongs beside the computer, not the cheese.\n🐹 Ham: I refuse to chase it.",
   "headphones":"💚 Lil Dino: Headphones belong with your devices, not your dairy.\n📜 The Archivist: Audio equipment cannot improve the flavor of leftovers.\n🐹 Ham: Play snack music, perhaps.",
   "camera":"📜 The Archivist: Photograph the meal if you wish, but store the camera elsewhere.\n💚 Lil Dino: Please don't put your camera in the fridge for a cool shot.\n🐹 Ham: I prefer photos of snacks I can actually eat.",
   "glasses":"💚 Lil Dino: Glasses help you see the ingredients. They do not belong inside the fridge.\n📜 The Archivist: Visual aid returned to its owner.\n🐹 Ham: I can see snacks perfectly well. Sometimes.",
   "hat":"💚 Lil Dino: A hat belongs on your head or a hook, not beside the eggs.\n📜 The Archivist: Headwear has been denied food-storage status.\n🐹 Ham: My ears are my hat.",
   "glove":"🧡 Chef Saffron: A clean kitchen glove may be used for food tasks, but store it separately and keep reusable ones clean.\n💚 Lil Dino: A random glove is not a produce bag.\n🐹 Ham: Tiny gloves for tiny paws, please.",
   "battery":"💚 Lil Dino: A battery is definitely not an ingredient. Keep batteries and other non-food items away from food.\n📜 The Archivist: Power source logged outside the pantry inventory.\n🐹 Ham: Does it power a snack machine?",
   "remote":"💚 Lil Dino: A remote control? The fridge does not have channels.\n📜 The Archivist: I have pressed every button. The yogurt remains unchanged.\n🐹 Ham: Can it open the snack drawer?",
   "pencil case":"📜 The Archivist: A pencil case belongs with stationery, not stored food.\n💚 Lil Dino: Unless it's full of carrots. It isn't.\n🐹 Ham: No pencils for me, thank you.",
   "water bottle":"💚 Lil Dino: A reusable water bottle can be chilled if clean and closed. The bottle itself is not a mystery ingredient.\n🧡 Chef Saffron: Keep it clean and store it so it cannot leak onto food.\n🐹 Ham: Hydration is important between snacks.",
   "soda can":"💚 Lil Dino: A soda can can be chilled, but that doesn't make it an ingredient guide.\n📜 The Archivist: Carbonation contained. Mystery solved.\n🐹 Ham: I prefer a snack with a crunch.",
   "coin":"📜 The Archivist: A coin is not a garnish. Please do not put it in food.\n💚 Lil Dino: It belongs in a wallet, not the fridge.\n🐹 Ham: I accept cookies instead of currency.",
   "remote control car":"💚 Lil Dino: A remote-control car is not a fridge organizer.\n📜 The Archivist: Tiny vehicle removed from the dairy district.\n🐹 Ham: I request a snack delivery vehicle."
  };
  const keys=Object.keys(reactions);const key=keys.find(k=>q===k||q.includes(k)||k.includes(q))||'default';
  const fallback='💚 Lil Dino: “'+button.dataset.randomThing+'” is not an ingredient. I checked.\n💜 Juniper: Let us keep non-food objects out of the fridge unless there is a sensible reason.\n📜 The Archivist: Random-object incident recorded.\n🐹 Ham: I have no idea what that is, so I will not taste it.';
  tipBox.textContent='🎲 THE FRIDGE CREW: RANDOM OBJECT EDITION\n\n'+(reactions[key]||fallback);
  tipBox.hidden=false;tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});return;
 }
 const room=rooms[activeRoom];
 const entry=room && room.items[Number(button.dataset.tipIndex)];
 if(!entry)return;
 // Dinner mood buttons rotate through distinct suggestions on repeated taps.
 if(activeRoom==='dinner'){
  const idx=Number(button.dataset.tipIndex);
  const dinnerIdeas={
   0:[
    'Try veggie-and-egg fried rice, a quesadilla with beans and cheese, or pasta tossed with garlic, olive oil, and vegetables.',
    'Make a 15-minute chickpea salad wrap with cucumber, tomato, and yogurt-lemon sauce; use canned beans to keep it quick.',
    'Sauté frozen vegetables with cooked noodles, soy sauce, and scrambled egg or tofu for a fast one-pan meal.',
    'Toast tortillas with black beans and cheese, then top with salsa, shredded cabbage, and lime.'
   ],
   1:[
    'Make a hearty soup, baked potato with toppings, or simple pasta bake. Add vegetables and a protein to make it more filling.',
    'Simmer lentils with carrots, onion, broth, and herbs; serve with toast or rice.',
    'Bake potatoes until tender and top with broccoli, cheese, beans, or leftover cooked chicken.',
    'Make a cozy tomato-and-white-bean skillet with garlic and herbs; serve with crusty bread.'
   ],
   2:[
    'Build a grain bowl with greens, chopped vegetables, beans or chicken, and a lemon dressing.',
    'Toss cucumber, tomato, chickpeas, and feta with lemon, olive oil, and herbs; serve with pita or rice.',
    'Make a bright rice bowl with edamame or tofu, shredded carrots, cucumber, and sesame-lime dressing.',
    'Fill lettuce cups with seasoned beans or chicken, crunchy vegetables, avocado, and lime.'
   ],
   3:[
    'Season with garlic, cumin, paprika, chili, or curry powder. Add a little at a time and taste as you go.',
    'Cook chicken or chickpeas with smoked paprika, cumin, garlic, and tomatoes; serve over rice.',
    'Make spicy peanut noodles with noodles, peanut butter, soy sauce, lime, and chili flakes to taste.',
    'Sauté peppers and onions with black beans, cumin, and chipotle or smoked paprika; serve in bowls or tortillas.'
   ],
   4:[
    'Combine cooked pasta with sautéed vegetables and tomato sauce or olive oil, garlic, and herbs.',
    'Toss pasta with pesto, white beans, and cherry tomatoes; loosen the sauce with a splash of pasta water.',
    'Make lemony spinach pasta with peas, garlic, Parmesan, and a little pasta water.',
    'Stir roasted vegetables into tomato pasta sauce and finish with basil or oregano.'
   ],
   6:[
    '🍓 Strawberry-banana smoothie: Blend 1 banana, a handful of strawberries, and ½–¾ cup milk or yogurt until smooth. Add a splash more liquid if needed.',
    '🥭 Mango lassi: Blend ripe mango with plain yogurt and a splash of cold water or milk. Add a pinch of cardamom if you like.',
    '🫐 Mixed berry smoothie: Blend blueberries, strawberries, and raspberries with yogurt or milk. Frozen berries make it extra cold.',
    '🍌 Peanut-butter banana smoothie: Blend banana, milk, and a spoonful of peanut butter until creamy. Label the peanut allergen clearly.',
    '🍍 Pineapple-coconut smoothie: Blend pineapple with coconut milk or yogurt. Add lime for a brighter flavor.',
    '🍑 Peach-yogurt smoothie: Blend ripe or frozen peaches with yogurt and a little milk until silky.',
    '🥝 Kiwi-banana smoothie: Blend peeled kiwi and banana with water, milk, or yogurt. Taste before adding sweetener.',
    '🍉 Watermelon slush smoothie: Blend chilled seedless watermelon with ice and a squeeze of lime. Serve immediately.',
    '🍫 Chocolate-banana smoothie: Blend banana, milk, cocoa, and yogurt for a creamy chocolate drink.',
    '🥥 Tropical smoothie: Blend mango, pineapple, and coconut milk. Add ice or frozen fruit for a thicker texture.',
    '🍓 Strawberry-oat smoothie: Blend strawberries, banana, milk, and a spoonful of rolled oats until smooth.',
    '🫐 Blueberry-vanilla smoothie: Blend blueberries, yogurt, and a little vanilla. Add milk to reach your preferred thickness.',
    '🍐 Pear-ginger smoothie: Blend ripe pear, yogurt, and a tiny pinch of fresh ginger. Start with very little ginger.',
    '🍊 Orange creamsicle smoothie: Blend orange segments or juice with yogurt and banana for a creamy citrus flavor.',
    '🍒 Cherry-almond smoothie: Blend pitted cherries with yogurt or milk and a tiny drop of almond extract, if desired.',
    '🥭 Mango-passionfruit smoothie: Blend mango with passionfruit pulp or juice and yogurt or coconut milk.',
    '🍇 Grape-berry smoothie: Blend seedless grapes with berries and yogurt. Add liquid gradually to keep it drinkable.',
    '🥬 Green smoothie: Blend banana, spinach, pineapple, and water or milk. The fruit gives it a mellow, sweet flavor.',
    '🥑 Avocado-banana smoothie: Blend ripe avocado, banana, milk, and a little lime for a thick, creamy drink.',
    '🍎 Apple-pie smoothie: Blend apple, banana, yogurt, and a pinch of cinnamon. Use a high-powered blender for a smoother texture.',
    '🍓 Strawberry-matcha smoothie: Blend strawberries, milk, yogurt, and a small amount of matcha. Add matcha gradually to taste.',
    '🍠 Ube-inspired smoothie: Blend milk or coconut milk with a little prepared ube halaya or food-grade ube flavoring. Check sweetness before adding sugar.',
    '🇯🇵 Japanese-inspired matcha banana smoothie: Blend banana, milk, yogurt, and a small amount of matcha until smooth.',
    '🇰🇷 Korean melon smoothie: Blend ripe Korean melon or honeydew with yogurt and ice for a delicate fruit flavor.',
    '🇮🇳 Mango lassi smoothie bowl: Blend mango and yogurt thickly, pour into a bowl, and top with fruit or a little chopped pistachio.',
    '🇵🇭 Ube-coconut smoothie: Blend prepared ube with coconut milk and ice; adjust sweetness carefully.',
    '🇹🇭 Thai-inspired mango-coconut smoothie: Blend ripe mango with coconut milk and a squeeze of lime.',
    '🇻🇳 Avocado smoothie inspiration: Blend ripe avocado with milk or a non-dairy alternative and sweeten lightly if desired.',
    '🌏 Café passport smoothie: Choose a fruit, a creamy base, and one flavor accent—such as mango + coconut, strawberry + matcha, or banana + sesame paste.',
    '🧊 Ham’s thick-smoothie trick: Use frozen fruit and add liquid a little at a time. Stop and scrape down the blender only after switching it off.',
    '🥛 Ham’s dairy-free option: Try oat, soy, or coconut drink instead of dairy milk; flavor and thickness will vary by product.',
    '🍯 Ham’s sweetness rule: Blend first, taste, then add a little honey, sugar, or syrup only if needed.',
    '🧼 Smoothie cleanup: Rinse the blender right after use, then wash the jar, lid, and blade assembly according to its instructions.',
    '❄️ Make-ahead tip: Freeze smoothie ingredients in single-serve packs. Blend with liquid when ready, rather than storing a finished smoothie for long periods.',
    '⚠️ Allergy note: Check labels for milk, soy, peanuts, tree nuts, and other allergens, and avoid cross-contact when preparing drinks.'
   ],
   5:[
    'Fill tortillas with beans, cooked meat or vegetables; add salsa, cabbage, cheese, and lime.',
    'Make black bean tacos with cumin, sautéed peppers, avocado, and lime crema or plain yogurt.',
    'Try quick fish or shrimp tacos with cabbage slaw, lime, and a little chili sauce.',
    'Use leftover roasted vegetables in tacos with pinto beans, salsa, cheese, and pickled onions.'
   ],
   6:[
    'Roast chopped vegetables and a suitable protein on a sheet pan. Cut pieces evenly and cook each item to a safe temperature.',
    'Roast sausage or chickpeas with broccoli, bell pepper, and red onion; toss with oil and seasoning first.',
    'Bake salmon fillets with green beans and small potato pieces on a sheet pan, timing each ingredient so it cooks safely.',
    'Roast cauliflower, sweet potato, and chickpeas with cumin and paprika; serve with yogurt sauce.'
   ],
   7:[
    'Tonight’s idea: crispy chicken wraps with lettuce and a simple side salad. Swap in beans or roasted vegetables if you prefer.',
    'Surprise idea: ginger-soy tofu bowls with rice and crunchy vegetables.',
    'Surprise idea: lemon chickpea orzo with spinach and herbs.',
    'Surprise idea: shrimp or white-bean garlic pasta with lemon and parsley.',
    'Surprise idea: loaded baked potatoes with broccoli, cheese, and black beans.'
   ]
  };
  const ideas=dinnerIdeas[idx];
  if(ideas){
   window.dinnerMoodCycle=window.dinnerMoodCycle||{};
   const previous=window.dinnerMoodCycle[idx];
   let next;
   if(idx===7){
    const options=ideas.map((_,i)=>i).filter(i=>i!==previous);
    next=options[Math.floor(Math.random()*options.length)];
   }else{
    next=previous===undefined?0:(previous+1)%ideas.length;
   }
   window.dinnerMoodCycle[idx]=next;
   tipBox.textContent='🧡 Chef Saffron says: “Let’s make something delicious!”\n\n'+entry[0]+'\n\n'+ideas[next];
   tipBox.hidden=false;
   list.querySelectorAll('.tip-choice').forEach(choice=>choice.setAttribute('aria-pressed',String(choice===button)));
   tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});
   return;
  }
 }
 // Ham’s Cozy Café helpers rotate through practical drink and treat ideas.
 if(activeRoom==='cafe'){
  const idx=Number(button.dataset.tipIndex);
  const cafeAlternatives={
   0:[
    '🐹 Ham’s coffee note: Brew coffee according to the package. Add milk or a little sweetener to taste; start small and adjust.',
    '☕ Iced vanilla latte: Stir a little vanilla syrup into chilled espresso or strong coffee, add milk, and pour over ice.',
    '🍫 Cozy cocoa: Warm 1 cup milk or an unsweetened alternative with 1–2 teaspoons cocoa and sweetener to taste. Whisk smooth and let cool before sipping.',
    '🍵 Matcha latte: Whisk ½–1 teaspoon matcha with a little warm water until smooth, then add warm or cold milk. Sweeten if desired.',
    '🫖 London fog-inspired tea: Steep Earl Grey tea, add warm milk, and a little vanilla. Let it cool before making an iced version.',
    '🥛 Café au lait: Combine brewed coffee and warm milk to your taste. A sprinkle of cinnamon is optional.',
    '🍯 Honey cinnamon coffee: Stir a little honey and cinnamon into hot coffee; mix well so the spice does not clump.',
    '🌰 Mocha: Mix cocoa and a little sugar into hot coffee, then add milk. Top with foam if you like.',
    '🧊 Cold-brew style: Steep coarse coffee grounds in cold water in the refrigerator, then strain well and dilute to taste. Follow safe storage guidance and keep chilled.',
    '🍵 Ginger tea: Steep sliced fresh ginger in hot water, then add lemon or honey to taste. Cool before serving over ice.',
    '🧊 Iced caramel coffee: Stir caramel syrup into chilled coffee, add milk if you like, and pour over ice.',
    '🍮 Vietnamese egg-coffee-inspired treat: Try a trusted recipe for whipped egg-yolk coffee, and use pasteurized eggs or a safe cooked method.',
    '☕ Americano: Add hot water to espresso, adjusting the strength to taste.',
    '🥛 Vanilla steamer: Warm milk with a little vanilla and sweetener; serve comfortably warm.',
    '🍵 Genmaicha: Brew Japanese green tea blended with roasted rice according to the package directions.',
    '🍃 Jasmine tea: Steep jasmine tea in water at the temperature recommended on the package, then enjoy hot or chilled.',
    '🫖 Chai latte: Brew spiced black tea strongly, then add warm milk and sweetener to taste.',
    '🍫 White mocha: Stir white chocolate into hot coffee and add milk for a creamy café-style drink.',
    '🥥 Coconut latte: Add a splash of coconut milk to coffee and sweeten if desired.',
    '🌿 Peppermint tea: Steep peppermint tea according to package directions; serve hot or chilled.',
    '🍋 Earl Grey lemonade: Chill Earl Grey tea and mix with lemonade for a bright tea cooler.',
    '🌸 Rose milk tea: Add a small amount of food-grade rose syrup to chilled tea and milk; taste as you go.',
    '🌰 Hazelnut coffee: Add a little hazelnut syrup to coffee and finish with milk if desired.',
    '🍯 Honey latte: Stir honey into warm espresso or strong coffee before adding milk.',
    '🍵 Sencha iced tea: Brew Japanese sencha as directed, chill promptly, and serve over ice.',
    '🌾 Barley tea: Brew roasted barley tea according to the package and serve chilled; check ingredients for allergies.',
    '🧋 Brown sugar milk tea: Combine brewed black tea, milk, and brown sugar syrup; chill and serve with optional prepared toppings.',
    '🍠 Taro milk tea: Mix milk with prepared taro powder or cooked taro following a trusted recipe; serve cold.',
    '🌺 Rosehip tea: Steep rosehip tea according to package directions and add a little honey if you like.',
    '🍎 Apple-cinnamon tea: Steep an apple-cinnamon tea bag or simmer apple slices with cinnamon, then strain.',
    '🧉 Café-style iced matcha: Shake matcha with a little water until smooth, add milk, and pour over ice.',
    '🍯 Turmeric golden milk: Warm milk with a small pinch of turmeric and cinnamon; sweeten lightly if desired.',
    '🥜🍫 Snickers-style iced frappé: Blend chilled coffee, milk, ice, chocolate syrup, caramel, and a small spoonful of peanut butter until smooth. Top with whipped cream if desired; label peanut and dairy allergens.',
    '🍪 Cookie-crumble frappé: Blend milk, ice, vanilla, and chocolate sandwich cookies. Top with cookie crumbs; check labels for allergens.',
    '🍯 Salted caramel frappé: Blend chilled coffee, milk, caramel sauce, ice, and a tiny pinch of salt. Adjust sweetness to taste.',
    '🍫 Brownie batter frappé: Blend chilled coffee or milk, cocoa, chocolate syrup, and ice; top with a small brownie piece if desired.',
    '🍓 Strawberries-and-cream frappé: Blend strawberries, milk, vanilla, and ice until creamy. Use frozen berries for a thicker texture.',
    '🍵 Matcha-vanilla frappé: Blend matcha, milk, vanilla, and ice until frothy. Matcha contains caffeine.',
    '🎃 Autumn pumpkin-spice latte: Stir pumpkin purée and pumpkin-pie spices into warm milk and coffee; sweeten to taste. Refrigerate leftover pumpkin purée.',
    '🍎 Apple-crisp latte: Add a little apple syrup or apple-cinnamon syrup to coffee and milk; finish with cinnamon.',
    '🍁 Maple-cinnamon latte: Stir maple syrup and cinnamon into espresso or strong coffee, then add milk.',
    '🍂 Toasted marshmallow mocha: Mix cocoa or chocolate sauce into coffee, add milk, and finish with toasted-marshmallow flavor syrup if available.',
    '🎄 Peppermint mocha: Stir chocolate sauce and a small amount of peppermint syrup into coffee; add milk. Start with just a little peppermint.',
    '❄️ White-chocolate peppermint latte: Melt white chocolate into hot coffee, add milk, and finish with a small amount of peppermint flavor.',
    '🫚 Gingerbread latte: Add gingerbread syrup or a little ginger, cinnamon, and sweetener to coffee with milk.',
    '🌷 Lavender-vanilla latte: Add a small amount of food-grade lavender syrup and vanilla to a latte; use culinary-grade ingredients only.',
    '🌸 Cherry-blossom-inspired iced tea: Chill a mild green tea and add cherry syrup or a little cherry juice. This is a café-inspired flavor, not a traditional recipe.',
    '🍉 Summer watermelon cooler: Blend seedless watermelon with lime and ice, then strain if desired.',
    '🥥 Iced coconut mocha: Shake chilled coffee with cocoa, milk or coconut milk, and ice.',
    '🍌 Banana-bread latte: Blend or stir banana syrup or a little banana purée with coffee, milk, vanilla, and cinnamon.',
    '🍬 Cotton-candy steamer: Stir a little cotton-candy flavor syrup into warm milk; serve comfortably warm, not hot.',
    '🍊 Orange mocha: Add a little orange zest or food-grade orange syrup to cocoa or coffee for a chocolate-orange flavor.',
    '🧊 Shaken espresso: Shake espresso with ice in a sealed shaker, then pour into a cup and add milk if wanted.',
    '🍵 Genmaicha latte: Brew strong roasted-rice green tea and add warm milk for a toasty drink.',
    '🌿 Mint iced tea: Brew mint tea, chill it, and add lemon to taste.',
    '🍒 Cherry mocha: Stir a small amount of cherry syrup into cocoa or coffee with chocolate.',
    '🥛 Strawberry milk: Blend strawberries with milk and a little sweetener; refrigerate and serve cold.',
    '🍪 Cookie butter latte: Stir a small spoonful of cookie butter into hot coffee and milk until smooth; check for allergens.',
    '🧂 Salted caramel cocoa: Add caramel and a tiny pinch of salt to cocoa, then stir well.',
    '🍵 Kukicha twig tea: Brew Japanese kukicha according to the package directions for a gentle, toasty cup.',
    '🌼 Chamomile tea: Steep chamomile tea according to package directions; check suitability for anyone with plant allergies or medication concerns.',
    '🍋 Lemon ginger tea: Steep ginger tea and add lemon juice after brewing.',
    '🍫 Iced chocolate: Mix cocoa with a little warm water and sweetener until smooth, add cold milk, and serve over ice.',
    '🥜 Peanut-butter cocoa: Whisk a small spoonful of smooth peanut butter into warm cocoa until fully blended; clearly label the allergen.',
    '🍇 Grape iced tea: Stir a splash of grape juice into chilled black or green tea and serve over ice.',
    '🥭 Mango green tea: Add mango purée or nectar to chilled green tea and adjust with lime.',
    '🍐 Pear black tea: Mix a little pear nectar into chilled black tea for a mellow fruit tea.',
    '🌱 Soy latte: Add warmed soy milk to espresso or strong coffee; use a barista-style product if you prefer extra foam.',
    '🧊 Coffee tonic: Pour chilled coffee over ice and top with tonic water for a crisp, bittersweet drink.',
    '🍦 Affogato-inspired cup: Pour a small shot of espresso over a scoop of ice cream and serve immediately.',
   ],
   1:[
    '🍓 Strawberry refresher: Mash 3–4 strawberries with 1 teaspoon sugar, add 1 cup cold water or chilled tea, lemon, and ice. Taste before adding more sugar.',
    '🍋 Citrus cooler: Mix ¾ cup cold water with ¼ cup orange juice and a squeeze of lemon. Serve over ice.',
    '🍑 Peach iced tea: Stir a little peach nectar or mashed ripe peach into chilled tea. Add ice and lemon if you like; keep refrigerated.',
    '🥭 Mango lassi-inspired smoothie: Blend ripe mango with plain yogurt and a splash of milk or water until smooth. Serve cold.',
    '🍉 Watermelon lime cooler: Blend seedless watermelon, strain if desired, and add lime juice. Serve cold over ice.',
    '🫐 Berry lemonade: Mash a handful of berries into lemonade, then strain if you prefer a smooth drink.',
    '🥒 Cucumber mint water: Add cucumber slices and mint to cold water; chill for a refreshing, lightly flavored drink.',
    '🍍 Pineapple fizz: Mix pineapple juice with sparkling water and a squeeze of lime just before serving.',
    '🍵 Hibiscus cooler: Brew hibiscus tea, chill it, and add lime or a little sweetener to taste.',
    '🍐 Pear ginger spritz: Mix pear nectar with sparkling water and a tiny amount of ginger juice or grated ginger; stir and taste.',
    '🍓 Strawberry-banana smoothie: Blend strawberries, banana, and yogurt or milk until smooth.',
    '🥝 Kiwi lime cooler: Blend peeled kiwi with cold water and lime; strain if you prefer fewer seeds.',
    '🍇 Grape spritzer: Mix chilled grape juice with sparkling water just before serving.',
    '🍒 Cherry lemonade: Stir pitted cherry purée or cherry juice into lemonade and chill.',
    '🥥 Coconut lime cooler: Mix coconut water with lime juice and ice.',
    '🍊 Mandarin iced tea: Add mandarin juice to chilled tea and garnish with a slice.',
    '🍍 Pineapple coconut smoothie: Blend pineapple with coconut milk or yogurt until creamy.',
    '🍈 Honeydew cooler: Blend ripe honeydew with a squeeze of lime and a little cold water.',
    '🫐 Blueberry lavender lemonade: Add a small amount of food-grade lavender syrup and mashed blueberries to lemonade.',
    '🍑 Peach mango smoothie: Blend peach, mango, and yogurt or milk until smooth.',
    '🍋 Lime soda: Mix lime juice, cold water, and sparkling water; sweeten lightly if desired.',
    '🍓 Strawberry milk tea: Add strawberry purée to chilled black tea and milk; stir well.',
    '🍉 Watermelon mint slush: Blend seedless watermelon with mint and ice until slushy.',
    '🍊 Orange cream cooler: Mix orange juice with milk or a creamy alternative and ice; serve immediately.',
    '🥭 Mango passionfruit cooler: Mix mango nectar with passionfruit juice and cold water.',
    '🍏 Green apple spritz: Combine apple juice, sparkling water, and a squeeze of lemon.',
    '🍋 Yuzu-inspired citrus tea: Add a little yuzu juice or food-grade yuzu syrup to chilled tea; adjust sweetness.',
    '🌺 Korean yuja-cha-inspired cooler: Stir yuja citron tea marmalade into cold water and ice, following the jar directions.',
    '🍚 Korean sikhye: Serve a chilled, traditionally sweet rice drink from a trusted recipe or Korean grocery store.',
    '🥤 Japanese ramune-inspired citrus fizz: Mix lemon-lime syrup with sparkling water for a playful citrus soda.',
    '🍑 Taiwan winter-melon tea: Prepare winter-melon tea concentrate according to package directions and chill.',
    '🍋 Thai lime soda: Mix fresh lime juice, cold water, and sparkling water; sweeten to taste.',
    '🥥 Filipino buko pandan cooler: Try a trusted recipe combining young coconut, pandan flavor, and milk; keep chilled.',
    '🌿 Vietnamese kumquat tea: Mix brewed tea with kumquat or calamansi juice and sweeten lightly.',
    '🥭 Indian aam panna-inspired cooler: Try a trusted recipe for a tangy green-mango drink, served well chilled.',
    '🌹 Indian rose sharbat: Stir food-grade rose syrup into cold water or milk according to the bottle directions.',
    '🍋 Middle Eastern mint lemonade: Blend lemon juice, mint, cold water, and ice until frothy.',
    '🥛 Mexican horchata-inspired drink: Serve chilled rice-and-cinnamon drink made with a trusted recipe; keep refrigerated.',
    '🍍 Agua fresca: Blend ripe fruit with cold water, strain if desired, and sweeten lightly.',
    '🍓 Brazilian strawberry vitamina: Blend strawberries with milk or a suitable alternative until creamy.',
    '🥭 Lassi with cardamom: Blend yogurt, mango or plain yogurt, a splash of water, and a tiny pinch of cardamom.',
    '🍵 Iced hojicha: Brew roasted Japanese green tea, chill it promptly, and serve over ice.',
    '🌾 Barley tea cooler: Chill brewed roasted barley tea and add lemon if desired.',
    '🍇 Blackcurrant cooler: Mix blackcurrant cordial with cold water and ice following the label directions.',
    '🍊 Blood orange spritz: Combine blood orange juice with sparkling water and ice.',
    '🥒 Cucumber lime fizz: Muddle cucumber gently, add lime juice, cold water, and sparkling water.',
    '🍒 Cranberry orange cooler: Mix cranberry juice with orange juice and cold water over ice.',
    '🍐 Pear jasmine iced tea: Add pear nectar to chilled jasmine tea and serve over ice.',
    '🥭 Mango coconut water: Mix mango purée with coconut water and a squeeze of lime.',
    '🍋 Lemon basil cooler: Add a few gently bruised basil leaves to lemonade and chill.',
   ],
   2:[
    '🍨 Parfait cup: Layer yogurt, fruit, and granola. Add granola just before eating if you want it crunchy.',
    '🍞 Cinnamon toast: Toast bread, spread lightly with butter, and sprinkle with cinnamon sugar. Cut into snack-sized strips.',
    '🍪 Café cookie plate: Serve cookies with sliced fruit or berries and a little yogurt dip.',
    '🍌 Banana bread slice: Serve banana bread with fruit; warm gently if desired and follow the recipe’s storage guidance.',
    '🧁 Mini muffins: Bake blueberry, banana, or chocolate-chip muffins in a mini muffin pan and cool before serving.',
    '🍫 Chocolate-dipped strawberries: Dip dry strawberries in melted chocolate and chill until set. Keep refrigerated.',
    '🍎 Apple-cinnamon bowl: Warm chopped apple with cinnamon until tender; top with yogurt or oats.',
    '🥐 Café toast plate: Serve toast with jam, nut or seed butter, or cream cheese, with fruit on the side.',
    '🍰 Mug cake treat: Use a tested microwave mug-cake recipe and a microwave-safe mug; let it cool before eating.',
    '🥞 Mini pancake bites: Make small pancakes and serve with fruit, yogurt, or a little syrup.',
    '🥮 Japanese mochi-inspired treat: Serve purchased mochi or make it with a trusted recipe; follow package storage instructions.',
    '🍡 Dango-inspired skewers: Serve Japanese rice-flour dumplings with a trusted recipe, and use age-appropriate serving sizes.',
    '🍰 Japanese cheesecake bite: Offer a small slice of Japanese-style cheesecake from a trusted recipe or bakery.',
    '🍞 Korean cream bread: Serve soft bakery bread filled with lightly sweetened whipped cream; keep chilled.',
    '🍩 Korean hotteok: Make or buy a sweet filled pancake with cinnamon-sugar filling; cool before serving.',
    '🥚 Taiwanese castella cake: Serve a soft slice of Taiwanese-style castella sponge cake.',
    '🥧 Hong Kong egg tart: Serve a small custard tart inspired by Hong Kong bakeries.',
    '🥥 Vietnamese coconut jelly: Offer chilled coconut jelly made with a trusted recipe and kept refrigerated.',
    '🍮 Thai coconut custard: Serve a small portion of Thai-style coconut custard, chilled or warm as the recipe directs.',
    '🍠 Filipino ube crinkle cookie: Bake or buy purple yam cookies and let them cool before serving.',
    '🍞 Filipino ensaymada-inspired bite: Serve a soft sweet bread roll topped with butter and cheese.',
    '🍪 Indian nankhatai: Serve a small buttery Indian shortbread-style cookie from a trusted recipe or bakery.',
    '🥥 Malaysian kuih: Try a colorful steamed or layered kuih from a Malaysian bakery; varieties differ widely.',
    '🍧 Indonesian klepon-inspired treat: Serve pandan rice-flour balls filled with palm sugar from a trusted recipe; the syrup can be hot inside.',
    '🍮 Chinese mango pudding: Make a chilled mango pudding using a trusted recipe and keep refrigerated.',
    '🥐 French café croissant: Serve a plain or chocolate-filled croissant with fruit.',
    '🍪 Italian biscotti: Serve crisp biscotti with tea or coffee; dunking is optional.',
    '🍮 Spanish crema catalana-inspired cup: Serve a small custard dessert made with a trusted recipe.',
    '🥛 Mexican arroz con leche: Offer a small chilled or warm rice pudding with cinnamon.',
    '🍪 Mexican polvorones: Serve a crumbly bakery cookie, checking the recipe for nuts and allergens.',
    '🥐 Brazilian pão de queijo: Serve warm cheese bread bites and let them cool enough to eat.',
    '🍮 Brazilian brigadeiro: Serve small chocolate truffles made with a trusted recipe.',
    '🍯 Middle Eastern date bites: Stuff pitted dates with a little tahini or seed butter; label sesame and other allergens.',
    '🥜 Sesame honey toast: Spread tahini and a little honey on toast for a sesame-forward café snack.',
    '🍓 Fruit and cream cup: Layer seasonal fruit with lightly sweetened whipped cream or yogurt.',
    '🍫 Chocolate brownie bite: Cut cooled brownies into small squares and serve with fruit.',
    '🍋 Lemon loaf slice: Serve a thin slice of lemon loaf with tea.',
    '🥕 Carrot cake mini: Offer a mini carrot cake or muffin with cream-cheese frosting; refrigerate frosted leftovers.',
    '🧇 Waffle bites: Cut waffles into small pieces and serve with berries or a little syrup.',
    '🍩 Cinnamon sugar doughnut holes: Serve cooled doughnut holes tossed lightly in cinnamon sugar.',
    '🍓 Strawberry shortcake cup: Layer cake crumbs, strawberries, and whipped cream just before serving.',
    '🍎 Apple hand-pie: Serve a small baked apple pastry and allow the filling to cool before eating.',
    '🥜 Peanut butter cookie: Offer a cookie with clear peanut-allergen labeling and an alternative for guests who need it.',
    '🍌 Banana fritter: Serve a small banana fritter made from a trusted recipe, cooled before eating.',
    '🥥 Coconut macaroons: Serve coconut cookies and check labels for egg or other allergens.',
    '🍮 Vanilla pudding cup: Chill vanilla pudding in small cups and top with fruit.',
    '🍇 Yogurt bark: Freeze yogurt with fruit on a lined tray, then break into pieces; keep frozen until serving.',
    '🍪 Sesame shortbread: Add toasted sesame to a shortbread recipe for a nutty café cookie; label sesame clearly.',
    '🍠 Sweet potato cake bite: Serve a small baked sweet-potato cake or muffin inspired by East Asian bakery flavors.',
   ],
   3:[
    '🍯 Vanilla + cinnamon works well in coffee, cocoa, and warm milk. Add a pinch of cinnamon first.',
    '🍓 Strawberry + lemon brightens cold drinks. Start with a small squeeze of lemon and taste.',
    '🍫 Chocolate + peppermint suits cocoa and dessert drinks. Use only a tiny amount of peppermint extract.',
    '🫚 Honey + ginger is lovely in warm tea. Stir in a little honey and freshly grated ginger.',
    '🥭 Mango + lime gives smoothies and coolers a bright, tropical flavor.',
    '🎃 Pumpkin cream cold brew: Pour chilled cold brew over ice and top with a little pumpkin-spice cream foam. Keep dairy topping chilled.',
    '🍏 Caramel apple cooler: Mix apple juice with a splash of sparkling water and caramel syrup; serve over ice.',
    '🍒 Cherry-vanilla soda: Stir cherry syrup and vanilla into sparkling water. Add ice and a cherry if desired.',
    '🍓 Strawberry-lemon refresher: Mix strawberry purée or syrup with lemonade and cold water; serve over ice.',
    '🍊 Cranberry-orange holiday spritz: Combine cranberry juice, orange juice, and sparkling water; garnish with orange.',
    '🍋 Winter citrus cooler: Mix lemon, orange, and grapefruit juice with cold water and a little sweetener.',
    '🌿 Spring cucumber-mint cooler: Muddle cucumber and mint gently, add lime and cold water, then strain if preferred.',
    '🥭 Mango-passionfruit iced tea: Mix chilled black or green tea with mango and passionfruit juice.',
    '🍑 Peach cobbler iced latte: Combine chilled coffee, milk, peach syrup, and a dash of cinnamon.',
    '🍫 Chocolate-covered strawberry milk: Stir strawberry syrup and chocolate sauce into cold milk; mix thoroughly.',
    '🌰 Sesame + honey makes a lovely flavor direction for sweets inspired by East Asian desserts; use toasted sesame sparingly.',
    '🍵 Matcha + vanilla works in lattes, shortbread, and simple cream desserts.',
    '🥥 Coconut + pandan is a fragrant pairing used in many Southeast Asian sweets. Use food-grade pandan extract or leaves according to a recipe.',
    '🍊 Orange + cardamom can lift tea, coffee, and cakes. Begin with just a pinch of cardamom.',
    '🫐 Blueberry + lemon is great in muffins, iced tea, and yogurt bowls.'
   ],
   4:[
    '🧊 Large ice cubes melt more slowly than small ones. Chill the drink first so ice dilutes it less quickly.',
    '☕ Freeze leftover brewed coffee in an ice-cube tray, then use the cubes in iced coffee instead of plain ice.',
    '🥛 Refrigerate milk-based drinks promptly and do not leave them sitting at room temperature for long. Wash reusable straws and lids after use.',
    '🍹 Chill glasses in the refrigerator for a short time before serving cold drinks; avoid putting fragile glassware in the freezer unless it is freezer-safe.',
    '🧋 For drinks with pearls or chewy toppings, follow package instructions and prepare them close to serving time for the best texture.',
    '🍋 Add citrus slices shortly before serving for a fresher look and flavor; remove them if the drink will sit for a long time.',
    '🧼 Wash blender jars, shakers, and reusable straws promptly after smoothies or milk drinks.',
    '🌡️ Let hot drinks cool to a comfortable sipping temperature before serving, especially to children.',
    '🧊 Freeze fruit pieces to use as colorful ice-cube additions; use clean, food-safe trays.',
    '🥤 Label any make-ahead drink with the date and keep it refrigerated; discard it if storage time or safety is uncertain.'
   ],
   5:[
    '🇯🇵 Japan — Matcha latte: Whisk matcha with a little warm water until smooth, then add milk hot or cold. Matcha flavor ranges from grassy to pleasantly savory.',
    '🇯🇵 Japan — Dorayaki-inspired treat: Make two small, soft pancakes and sandwich them with sweet red bean paste. This is a home-inspired version of a classic snack.',
    '🇯🇵 Japan — Hojicha latte: Steep roasted green tea, then add warm milk and a little sweetener if desired. Hojicha has a toasty flavor.',
    '🇰🇷 Korea — Sikhye-inspired rice drink: Try a chilled, lightly sweet rice drink from a Korean grocery store, or follow a trusted recipe; it is traditionally made with malted barley and cooked rice.',
    '🇰🇷 Korea — Hotteok-inspired café bite: Serve a warm, pan-cooked sweet pancake filled with brown sugar, cinnamon, and chopped nuts. Let the filling cool before biting.',
    '🇹🇼 Taiwan — Bubble tea: Brew strong tea, chill it, add milk or fruit flavor, and serve with prepared tapioca pearls following the package directions. Use a wide straw only if appropriate and supervise young children.',
    '🇭🇰 Hong Kong — Hong Kong-style milk tea: Brew strong black tea and combine with evaporated milk or your preferred milk. Adjust strength and sweetness to taste.',
    '🇨🇳 China — Soy milk and sesame sweets: Serve warm or chilled soy milk with a sesame cookie or sesame-filled pastry inspired by Chinese bakery flavors.',
    '🇻🇳 Vietnam — Cà phê sữa đá-inspired coffee: Mix strong coffee with sweetened condensed milk and pour over ice. It is rich, sweet, and strong, so adjust the ratio to taste.',
    '🇻🇳 Vietnam — Pandan waffle: Try a fragrant green pandan waffle from a Vietnamese bakery or use a trusted recipe with food-grade pandan flavoring.',
    '🇹🇭 Thailand — Thai iced tea: Brew Thai tea mix according to its package, sweeten to taste, add milk, and serve over ice. It is often vivid orange and quite sweet.',
    '🇹🇭 Thailand — Mango sticky rice cup: Serve ripe mango with sweet coconut sticky rice. This is a dessert rather than a drink, and ripe mango makes the difference.',
    '🇵🇭 Philippines — Ube latte: Stir a little prepared ube halaya or food-grade ube flavor into milk, then serve warm or iced. Check sweetness before adding more sugar.',
    '🇵🇭 Philippines — Pandesal café plate: Serve soft pandesal rolls with butter, cheese, or jam for a simple bakery-style snack.',
    '🇮🇳 India — Masala chai: Simmer black tea with milk, ginger, and spices such as cardamom and cinnamon; strain before serving. Adjust the spices to your taste.',
    '🇮🇳 India — Mango lassi: Blend ripe mango, plain yogurt, and a splash of water or milk until smooth. Serve cold.',
    '🇲🇾 Malaysia / 🇸🇬 Singapore — Kopi-inspired coffee: Make strong coffee and add condensed or evaporated milk to taste; local kopi styles vary by shop and region.',
    '🇮🇩 Indonesia — Es cendol-inspired treat: Try a chilled coconut-milk dessert with pandan rice-flour jelly and palm sugar syrup from a trusted recipe or local shop.',
    '🇨🇳 China — Egg tart café treat: Serve small custard tarts inspired by Chinese bakery and dim sum traditions; styles differ between regions.',
    '🌏 Ham’s café passport note: These are inspirations from diverse food traditions, not one single “Asian” flavor. Explore regional recipes and local sources for the most authentic versions.'
   ],
   6:[
    '🍓 Strawberry-Banana Smoothie: Blend 1 cup strawberries, 1 banana, ½ cup yogurt, and a splash of milk until smooth.',
    '🫐 Mixed Berry Smoothie: Blend 1 cup mixed berries, ½ banana, ½ cup yogurt, and milk or oat milk to loosen.',
    '🥭 Mango Sunshine Smoothie: Blend 1 cup mango, ½ cup yogurt, and a little orange juice or milk.',
    '🍍 Pineapple-Coconut Smoothie: Blend pineapple with coconut milk and a few ice cubes; add banana for a thicker texture.',
    '🍑 Peach Cream Smoothie: Blend sliced peaches, yogurt, and milk with a pinch of cinnamon if you like.',
    '🍫 Chocolate-Banana Smoothie: Blend banana, milk, cocoa, and yogurt or a spoonful of nut butter.',
    '🥜 Peanut Butter-Banana Smoothie: Blend banana, milk, peanut butter, and yogurt. Check allergies before serving.',
    '🍓 Strawberry Cheesecake-Inspired Smoothie: Blend strawberries, yogurt, milk, and a little vanilla; add a spoonful of cream cheese for a richer version.',
    '🥬 Green Mango Smoothie: Blend mango, banana, spinach, and orange juice or water; the fruit keeps it bright and sweet.',
    '🍉 Watermelon-Lime Smoothie: Blend chilled seedless watermelon with lime juice and ice. Add yogurt for a creamier version.',
    '🥝 Kiwi-Banana Smoothie: Blend peeled kiwi, banana, yogurt, and a splash of water or milk.',
    '🍒 Cherry-Vanilla Smoothie: Blend pitted cherries, vanilla yogurt, and milk; frozen cherries make it extra thick.',
    '🍎 Apple-Cinnamon Smoothie: Blend apple, banana, yogurt, milk, and a pinch of cinnamon. Core the apple first.',
    '☕ Mocha Breakfast Smoothie: Blend chilled coffee, banana, cocoa, milk, and yogurt. Keep caffeine in mind for children.',
    '🥥 Coconut-Berry Smoothie: Blend berries, coconut milk, and banana for a creamy tropical flavor.',
    '🍊 Orange Cream Smoothie: Blend orange segments, banana, yogurt, and vanilla. Remove seeds and tough pith.',
    '🍐 Pear-Ginger Smoothie: Blend ripe pear, yogurt, milk, and a tiny amount of fresh ginger.',
    '🫐 Blueberry-Oat Smoothie: Blend blueberries, banana, yogurt or milk, and a spoonful of oats until smooth.',
    '🍌 Banana-Date Smoothie: Blend banana, one or two pitted dates, milk, and cinnamon. Dates add plenty of sweetness.',
    '🥭 Mango Lassi-Inspired Smoothie: Blend ripe mango, plain yogurt, a splash of water, and a pinch of cardamom if desired.',
    '🍵 Matcha-Banana Smoothie: Blend banana, milk, yogurt, and a small amount of matcha powder. Matcha contains caffeine.',
    '🟣 Ube-Coconut Smoothie: Blend a little prepared ube halaya or food-grade ube flavor with milk, coconut milk, and ice; check sweetness first.',
    '🍈 Melon-Yogurt Smoothie: Blend ripe honeydew or cantaloupe with yogurt and a squeeze of lime.',
    '🍌 Avocado-Banana Smoothie: Blend ripe avocado, banana, milk, and ice for a silky texture.',
    '🍓 Raspberry-Lemon Smoothie: Blend raspberries, banana, yogurt, and a small squeeze of lemon.',
    '🍍 Pineapple-Mango Smoothie: Blend pineapple, mango, and coconut water for a bright tropical smoothie.',
    '🍫 Chocolate-Strawberry Smoothie: Blend strawberries, milk, cocoa, and banana for natural sweetness.',
    '🥕 Carrot-Mango Smoothie: Blend cooked and cooled carrot, mango, orange juice, and yogurt until smooth.',
    '🍇 Grape-Berry Smoothie: Blend seedless grapes, berries, yogurt, and ice; blend thoroughly and strain if needed.',
    '🍋 Lemon-Blueberry Smoothie: Blend blueberries, banana, yogurt, and a little lemon zest for a fresh flavor.',
    '🌴 Dates-and-Tahini Smoothie: Blend dates, banana, milk, and a small spoonful of tahini for a nutty sesame note; check sesame allergies.',
    '🍠 Purple Sweet Potato Smoothie: Blend cooked, chilled purple sweet potato with banana, milk, and vanilla.',
    '🥭 Papaya-Lime Smoothie: Blend ripe papaya, yogurt, and lime juice; add water or milk to reach your preferred thickness.',
    '🍓 Strawberry-Coconut Water Smoothie: Blend strawberries, banana, and coconut water for a lighter, refreshing version.',
    '🧊 Café Frappe-Style Smoothie: Blend chilled coffee, milk, ice, and cocoa or vanilla; adjust sweetness to taste.',
    '🐹 Ham’s smoothie rule: Start with less liquid, blend, then add more until it pours the way you like. Keep dairy-based smoothies refrigerated and serve promptly.'
   ],
   7:[
    '🥜 Snickers-Inspired Frappé: Blend chilled coffee or milk, chocolate syrup, caramel, a spoonful of peanut butter, and ice. Top with whipped cream if desired; check peanut allergies.',
    '🍪 Cookies-and-Cream Frappé: Blend milk, ice, vanilla, and chocolate sandwich cookies until creamy. Finish with cookie crumbs.',
    '🍫 Brownie Batter Frappé: Blend milk, ice, chocolate syrup, and a little cocoa; add a small brownie piece for a dessert-style treat.',
    '🍯 Salted Caramel Crunch Frappé: Blend milk, caramel sauce, ice, and a tiny pinch of salt. Add toffee-style crunch as a topping if available.',
    '🍓 Strawberries-and-Cream Frappé: Blend strawberries, milk, vanilla, ice, and a little sweetener. Swirl strawberry sauce around the cup.',
    '🍫 Chocolate-Hazelnut Frappé: Blend milk, ice, cocoa, and chocolate-hazelnut spread. Check the label for tree nuts.',
    '🍌 Banana Pudding Frappé: Blend banana, milk, vanilla, ice, and a little vanilla pudding; top with crushed vanilla wafers.',
    '🍰 Birthday Cake Frappé: Blend milk, vanilla, ice, and a little cake-flavored syrup or vanilla cake crumb. Add sprinkles on top.',
    '🍬 Candy-Bar Mocha: Stir chocolate and caramel into coffee, add milk, and finish with a small sprinkle of chopped candy-bar pieces.',
    '🌰 Toasted Marshmallow Cocoa: Stir toasted-marshmallow flavor or a toasted marshmallow into hot cocoa; let it cool to a comfortable sipping temperature.',
    '🍵 Matcha White-Chocolate Latte: Whisk matcha with a little warm water, then add milk and a little melted white chocolate. Serve warm or over ice.',
    '🟣 Ube-Coconut Latte: Stir prepared ube flavor or ube halaya into milk, add a little coconut milk, and serve warm or iced.',
    '🥥 Coconut Cream Cold Brew: Pour chilled cold brew over ice and add coconut milk plus a touch of vanilla syrup.',
    '🍮 Crème Brûlée Latte: Add vanilla syrup to coffee and milk; finish with a caramelized-sugar-inspired topping, without attempting to torch a drink in its cup.',
    '🍋 Blueberry-Lemonade Refresher: Stir blueberry syrup or mashed blueberries into lemonade and cold water; strain if you prefer it smooth.',
    '🍑 Peach-Ring Refresher: Mix peach nectar, lemon juice, cold water, and ice; garnish with peach slices.',
    '🍉 Watermelon Candy Cooler: Blend seedless watermelon, lime, and ice; sweeten lightly only if needed.',
    '🍍 Pineapple-Coconut Fizz: Mix pineapple juice with coconut water and a splash of sparkling water just before serving.',
    '🌈 Rainbow Fruit Cooler: Layer chilled strawberry, mango, and blue-colored lemonade-style drinks slowly over ice for a colorful nonalcoholic café special.',
    '🍏 Caramel Apple Chiller: Mix apple juice, a little caramel sauce, and milk or oat milk over ice; stir well before drinking.',
    '🎃 Pumpkin-Spice Iced Latte: Mix chilled coffee, milk, pumpkin purée, pumpkin spice, and sweetener; blend or shake until smooth and keep refrigerated.',
    '🍎 Apple-Cinnamon Chai: Brew chai, add apple juice and cinnamon, then serve warm or chilled.',
    '🍁 Maple-Vanilla Latte: Stir a little maple syrup and vanilla into coffee, then add milk.',
    '🍂 Brown Sugar Cinnamon Shaken Espresso: Shake espresso, brown sugar, and cinnamon with ice, then top with milk. Use a sealed shaker designed for liquids and beware of pressure from hot drinks.',
    '🎄 Peppermint Mocha: Mix coffee with cocoa, milk, and a little peppermint syrup; start with a small amount because peppermint is strong.',
    '🍪 Gingerbread Cookie Latte: Add ginger, cinnamon, a little molasses or brown sugar, and milk to coffee for a gingerbread-inspired flavor.',
    '❄️ White Chocolate Peppermint Cocoa: Stir white chocolate and a little peppermint into warm milk; serve warm, not scalding.',
    '💗 Raspberry White Mocha: Add raspberry syrup and white chocolate to coffee, then finish with milk.',
    '🍫 Rocky Road Frappe: Blend milk, chocolate syrup, ice, and a little marshmallow flavor; top with marshmallows and a sprinkle of chopped nuts if safe.',
    '🧋 Brown Sugar Boba Milk: Stir brown sugar syrup into milk or tea and add prepared tapioca pearls according to package instructions. Serve pearls with an appropriate straw and supervise young children.',
    '🍯 Honey-Butter Toast Latte: Add a small amount of honey and vanilla to a latte; pair with cinnamon toast for the café-inspired flavor idea.',
    '🍇 Grape Soda Float: Pour grape soda over a small scoop of vanilla ice cream for a nostalgic float; serve immediately.',
    '🍒 Cherry-Vanilla Cream Soda: Mix cherry syrup and vanilla with sparkling water; add a splash of cream if desired.',
    '🍊 Orange Creamsicle Frappe: Blend orange juice, milk or vanilla yogurt, ice, and vanilla until creamy.',
    '🥭 Mango Sticky-Rice Shake: Blend mango, milk or coconut milk, ice, and a little vanilla; add a spoonful of cooked chilled sticky rice for a dessert-inspired texture.',
    '🍵 Hojicha Caramel Latte: Brew roasted Japanese green tea, add milk and caramel to taste, and serve warm or iced.',
    '🧁 Cinnamon Roll Frappe: Blend milk, ice, vanilla, cinnamon, and a little brown sugar; top with whipped cream if you like.',
    '🍫 Double-Chocolate Chip Frappe: Blend milk, ice, chocolate syrup, and chocolate chips until smooth; top with a few chips.',
    '🫐 Blueberry Muffin Smoothie: Blend blueberries, banana, yogurt, oats, vanilla, and milk until smooth.',
    '🍓 Strawberry Shortcake Shake: Blend strawberries, milk, vanilla ice cream or frozen yogurt, and a little shortbread crumb.',
    '🐹 Ham’s fun-drink rule: These are café-inspired ideas, not official brand recipes. Taste as you go, label common allergens, and keep milk-based drinks chilled.'
   ],
   8:[
    '🥤 Classic Vanilla Milkshake: Blend 2 cups vanilla ice cream, ½ cup cold milk, and ½ teaspoon vanilla until smooth. For a malt, add 1–2 tablespoons malted milk powder.',
    '🍫 Chocolate Diner Shake: Blend 2 cups chocolate or vanilla ice cream, ½ cup milk, and 2 tablespoons chocolate syrup. Add a little cocoa for deeper chocolate flavor.',
    '🍓 Strawberry Milkshake: Blend 2 cups vanilla ice cream, ½ cup milk, and ½ cup strawberries. Taste before adding syrup.',
    '🍪 Cookies-and-Cream Shake: Blend 2 cups vanilla ice cream, ½ cup milk, and 4 chocolate sandwich cookies. Save a cookie crumb sprinkle for the top.',
    '🥜 Chocolate Peanut Butter Shake: Blend 2 cups ice cream, ½ cup milk, 1 tablespoon peanut butter, and chocolate syrup. Check allergies before serving.',
    '🍰 Strawberry Cheesecake Shake: Blend vanilla ice cream, milk, strawberries, a spoonful of cream cheese, and a graham cracker. Finish with whipped cream if desired.',
    '🍌 Banana Pudding Shake: Blend vanilla ice cream, milk, half a banana, and vanilla wafer cookies. Top with one extra wafer.',
    '🍫 Brownie Batter Shake: Blend chocolate ice cream, milk, and a fully baked, cooled brownie. Never use raw batter containing uncooked flour or eggs.',
    '🎂 Birthday Cake Shake: Blend vanilla ice cream, milk, a little vanilla, and a small piece of baked vanilla cake. Add sprinkles for a party-shop finish.',
    '🥨 Salted Caramel Pretzel Shake: Blend vanilla ice cream, milk, and caramel sauce. Top with crushed pretzels and a tiny pinch of salt just before serving.',
    '🥭 Mango Coconut Shake: Blend mango chunks, vanilla ice cream, a splash of milk, and coconut milk for a tropical dessert shake.',
    '🍑 Peach Cobbler Shake: Blend peaches, vanilla ice cream, milk, and a pinch of cinnamon. Top with cookie crumble.',
    '🍍 Pineapple Vanilla Shake: Blend drained pineapple, vanilla ice cream, and a splash of milk until creamy.',
    '🫐 Blueberry Cheesecake Shake: Blend blueberries, vanilla ice cream, milk, and a spoonful of cream cheese. Add graham cracker crumbs on top.',
    '🍓 Strawberry Banana Shake: Blend strawberries, banana, vanilla ice cream, and milk until smooth.',
    '🐹 Ham’s malt-shop rule: Add milk a little at a time for a thicker shake. Keep dairy shakes chilled and serve promptly; label allergens and use safe alternatives when needed.'
   ]
  };  const choices=cafeAlternatives[idx];
  if(choices){
   window.hamCafeCycle=window.hamCafeCycle||{};
   const previous=window.hamCafeCycle[idx];
   const next=previous===undefined?0:(previous+1)%choices.length;
   window.hamCafeCycle[idx]=next;
   tipBox.textContent=entry[0]+'\n\n'+choices[next]+'\n\n— Ham’s Quality-Control Notes';
   tipBox.hidden=false;
   list.querySelectorAll('.tip-choice').forEach(choice=>choice.setAttribute('aria-pressed',String(choice===button)));
   tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});
   return;
  }
 }
 // Baking Corner helpers cycle through several practical answers on repeated taps.
 if(activeRoom==='baking'){
  const idx=Number(button.dataset.tipIndex);
  const bakingAlternatives={
   0:[
    'Preheat fully, gather ingredients, and prepare pans before mixing. Use the pan size the recipe specifies.',
    'Read the recipe all the way through first. Check whether butter and eggs should be cold, softened, or room temperature.',
    'Let cakes and quick breads cool in the pan for the recipe’s suggested time, then move them to a rack so the bottoms do not steam.',
    'For more even results, measure ingredients before starting and avoid opening the oven repeatedly during the early rise.'
   ],
   1:[
    'Buttermilk: add 1 tablespoon lemon juice or vinegar to a measuring cup, then add milk to the 1-cup line. Wait 5–10 minutes.',
    'Sour cream: plain unsweetened yogurt can often replace it in cakes and quick breads in the same amount.',
    'Egg: in some muffins and quick breads, ¼ cup unsweetened applesauce can replace one egg, though texture may be denser. It is not ideal for every recipe.',
    'Milk: unsweetened, unflavored plant milk can often replace dairy milk in a similar amount. Choose one that suits the recipe.',
    'Flour: whole-wheat flour may make a bake denser; almond and coconut flour usually cannot replace all-purpose flour cup-for-cup.',
    'Baking powder and baking soda are not 1:1 substitutes. Tell me the recipe and amount before changing the leavener.'
   ],
   2:[
    '1 cup = 16 tablespoons = 48 teaspoons. 1 tablespoon = 3 teaspoons.',
    '1 US stick butter = ½ cup = 8 tablespoons = about 113 g. Two sticks = 1 cup = about 227 g.',
    '1 cup all-purpose flour weighs about 120 g; spoon it into the cup and level it instead of packing it.',
    '1 cup granulated sugar weighs about 200 g; 1 cup packed brown sugar weighs about 220 g. Weights vary by ingredient and packing.',
    'For volume: 1 US pint = 2 cups; 1 US quart = 4 cups; 1 US gallon = 16 cups.',
    'For best precision, use grams when the recipe provides them. A cup of flour and a cup of sugar do not weigh the same.'
   ],
   3:[
    'Spoon flour into measuring cups and level the top; scooping directly can pack in too much.',
    'Measure liquids at eye level in a liquid measuring cup. Use dry cups for flour and sugar.',
    'Mix muffins and quick breads only until the dry streaks disappear; overmixing can make them tough.',
    'Use the center oven rack unless the recipe says otherwise, and check doneness near the earliest suggested time.',
    'If the top browns too quickly, check your oven temperature with an oven thermometer before changing the recipe.'
   ],
   4:[
    'Fruit pairings: lemon + blueberry, strawberry + rhubarb, apple + cinnamon, or pear + ginger.',
    'Chocolate pairings: chocolate + raspberry, chocolate + orange, chocolate + espresso, or chocolate + toasted coconut.',
    'Warm spice pairings: cinnamon + apple, ginger + pear, cardamom + orange, or nutmeg + banana.',
    'Nutty pairings: almond + cherry, walnut + maple, pistachio + orange, or peanut butter + chocolate.',
    'Start with a small amount of strong extracts, citrus zest, or spices, then adjust next time. Too much can overpower a bake.'
   ],
   5:[
    'Dry cake: check for overbaking and measure flour carefully. Start checking a few minutes before the recipe’s stated time.',
    'Tough muffins: overmixing after adding flour may be the cause. Stir only until combined next time.',
    'Flat cookies: warm dough, melted butter, or too little flour can cause excess spread. Chill dough if the recipe allows.',
    'Dense cake: check the leavener’s freshness and measure accurately; avoid overmixing once flour is added.',
    'A sunken cake may be underbaked, over-leavened, or affected by opening the oven too early. Check doneness before removing it.',
    '🇯🇵 Japan — Japanese iced coffee: Brew coffee directly over ice to keep its aroma bright, then serve immediately.',
    '🇯🇵 Japan — Sakura-inspired soda: Add a little food-grade cherry-blossom syrup to sparkling water; use only edible culinary products.',
    '🇯🇵 Japan — Ramune float: Pour Japanese-style ramune soda over a small scoop of vanilla ice cream.',
    '🇯🇵 Japan — Anmitsu dessert cup: Layer agar jelly, fruit, and sweet red beans, following a trusted recipe.',
    '🇰🇷 Korea — Dalgona coffee: Whip instant coffee, sugar, and hot water until fluffy, then spoon over milk; this drink contains caffeine.',
    '🇰🇷 Korea — Banana milk: Blend banana with milk until smooth and serve chilled.',
    '🇰🇷 Korea — Bingsu-inspired shaved ice: Top finely shaved ice with fruit, sweet beans, or condensed milk and serve right away.',
    '🇹🇼 Taiwan — Winter melon tea: Brew or dilute winter-melon tea concentrate according to its package and chill.',
    '🇹🇼 Taiwan — Taro sago dessert: Serve a chilled taro and small-tapioca dessert made with a trusted recipe.',
    '🇭🇰 Hong Kong — Lemon tea: Serve strong black tea with lemon slices and sweetener to taste, hot or iced.',
    '🇭🇰 Hong Kong — Pineapple bun: Serve a bakery-style pineapple bun; despite the name, it usually has no pineapple filling.',
    '🇨🇳 China — Chrysanthemum tea: Brew edible chrysanthemum tea according to package directions; check suitability for allergies.',
    '🇨🇳 China — Red bean milk: Blend a little sweet red bean paste with milk for a dessert-style drink, then chill.',
    '🇻🇳 Vietnam — Salt coffee: Try a trusted Vietnamese-style salted coffee recipe with a small amount of salted cream.',
    '🇻🇳 Vietnam — Avocado smoothie: Blend ripe avocado with milk and sweetener to taste for a creamy Vietnamese café-inspired drink.',
    '🇹🇭 Thailand — Butterfly-pea lime tea: Brew food-grade butterfly-pea flowers, chill, then add lime for a color-changing drink.',
    '🇹🇭 Thailand — Coconut ice cream: Serve Thai-style coconut ice cream with toasted peanuts or other toppings, clearly labeled for allergens.',
    '🇵🇭 Philippines — Calamansi juice: Mix calamansi juice with cold water and sweetener to taste.',
    '🇵🇭 Philippines — Mais con yelo: Layer sweet corn, shaved ice, milk, and toppings in a chilled dessert cup.',
    '🇮🇳 India — Badam milk: Blend almond paste or finely ground almonds with milk and warming spices; label tree nuts clearly.',
    '🇮🇳 India — Jal jeera-inspired cooler: Try a trusted recipe for a tangy cumin-and-mint drink served cold.',
    '🇲🇾 Malaysia — Teh tarik: Prepare strong black tea with condensed milk and carefully aerate it using a trusted method.',
    '🇸🇬 Singapore — Milo dinosaur-inspired drink: Top iced Milo or malted chocolate drink with a little extra malt powder.',
    '🇮🇩 Indonesia — Es teh manis: Serve chilled sweet black tea and adjust sweetness to taste.',
    '🇮🇩 Indonesia — Klepon: Offer pandan rice-flour balls filled with palm sugar from a trusted recipe; let the hot syrup cool.',
    '🇱🇰 Sri Lanka — Ceylon iced tea: Brew Ceylon tea, chill, and serve with lemon or a little sweetener.',
    '🇳🇵 Nepal — Masala milk tea: Brew black tea with milk and warming spices, inspired by regional chai traditions.',
    '🇧🇩 Bangladesh — Borhani-inspired yogurt drink: Explore a trusted recipe for a spiced yogurt drink, served chilled.',
    '🇲🇽 Mexico — Café de olla: Brew coffee with cinnamon and piloncillo or brown sugar; strain before serving.',
    '🇲🇽 Mexico — Champurrado: Serve a thick chocolate-and-masa drink made with a trusted recipe, warm but not scalding.',
    '🇵🇪 Peru — Chicha morada: Make a chilled purple-corn drink with fruit and spices using a trusted recipe.',
    '🇧🇷 Brazil — Cafézinho: Serve a small, strong cup of Brazilian-style coffee, sweetened to taste.',
    '🇮🇹 Italy — Affogato: Pour espresso over vanilla gelato and serve immediately.',
    '🇪🇸 Spain — Café con leche: Combine espresso or strong coffee with warm milk.',
    '🇫🇷 France — Chocolat chaud: Make a rich hot chocolate with milk and chocolate, then cool to a comfortable sipping temperature.',
    '🇹🇷 Türkiye — Turkish coffee: Prepare finely ground coffee using a trusted method and serve in small cups; grounds remain in the cup.',
    '🇲🇦 Morocco — Mint tea: Brew green tea with fresh mint and sweeten to taste; pour carefully to avoid splashes.',
    '🇬🇷 Greece — Frappé: Shake instant coffee, water, and sugar until foamy, then add cold water or milk and ice.',
    '🌏 Ham’s passport reminder: Café traditions vary by family, city, and region. These are starting points for exploring, not a claim that every place makes them the same way.',
   ],
   6:[
    'Choose a recipe you can comfortably follow, measure carefully, and change only one thing at a time.',
    'Try a flavor experiment: keep the base recipe the same and change only the fruit, spice, or extract.',
    'Practice weighing flour and sugar, then compare the results with measuring by volume.',
    'Make a one-cookie or one-muffin test when a recipe allows, then adjust chilling or baking time before the full batch.'
   ]
  };
  const alternatives=bakingAlternatives[idx];
  if(alternatives){
   window.bakingHelperCycle=window.bakingHelperCycle||{};
   const previous=window.bakingHelperCycle[idx];
   const next=previous===undefined?0:(previous+1)%alternatives.length;
   window.bakingHelperCycle[idx]=next;
   tipBox.textContent=entry[0]+'\n\n'+alternatives[next];
   tipBox.hidden=false;
   list.querySelectorAll('.tip-choice').forEach(choice=>choice.setAttribute('aria-pressed',String(choice===button)));
   tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});
   return;
  }
 }
 let tipText=entry[1];
 if(activeRoom==='fridge'){
  const ingredient=entry[0].toLowerCase();
  let voices='';
  if(/bok choy|napa cabbage|daikon|bean sprouts|enoki|shiitake|shimeji|ginger|lemongrass|thai basil|curry leaves|pandan|galangal|kimchi|miso|gochujang|tofu|tempeh|rice noodles|dumpling|chili|chilli|sambal|coconut milk|paneer|green mango|jackfruit|cilantro|scallion|seaweed|kimchi|mushroom/.test(ingredient)){
   voices='🌏 Juniper: This ingredient appears in specific regional food traditions; storage depends on whether it is fresh, cut, fermented, or packaged.\n💚 Lil Dino: Check the exact ingredient notes above. “Asian ingredient” is not one single storage category.\n🧡 Chef Saffron: Keep refrigerated foods at 40°F (4°C) or colder, follow the package instructions, and prevent raw-food cross-contamination.\n📜 The Archivist: Once opened, label the container and follow its storage directions.\n🐹 Ham: I have volunteered to inspect the snacks. The food-safety department has declined my application again.';
  } else if(/meat|chicken|beef|pork|fish|shrimp|seafood|deli|sausage|turkey/.test(ingredient)){
   voices='🧡 Chef Saffron: Keep raw meat and seafood sealed on the lowest shelf so juices cannot drip onto other food.\n📜 The Archivist: Note the purchase/opened date and freeze what you will not use in time.\n💚 Lil Dino: Separate raw ingredients from ready-to-eat foods. This is not the place for risky shelf-sharing.\n🐹 Ham: I will supervise from behind this very secure barrier. No tasting for safety!';
  } else if(/milk|dairy|cheese|yogurt|yoghurt|cream|butter|egg|paneer|labneh/.test(ingredient)){
   voices='🧡 Chef Saffron: Keep this chilled at 40°F (4°C) or colder and follow the label after opening.\n📜 The Archivist: Store it on an interior shelf when possible, not in the warmer door.\n💚 Lil Dino: Dates and proper storage beat sniff-tests alone. If you are unsure it is safe, discard it.\n🐹 Ham: I have been officially banned from using taste tests as a safety policy.';
  } else if(/leftover|cooked rice|cooked pasta|sauce|soup|curry|prepared/.test(ingredient)){
   voices='🩵 Rook: Put leftovers in shallow, covered containers and get them into the fridge within 2 hours—or within 1 hour above 90°F (32°C).\n📜 The Archivist: Label with the date; most cooked leftovers keep 3–4 days in a fridge at 40°F (4°C) or colder.\n🧡 Chef Saffron: Reheat leftovers to 165°F (74°C).\n🐹 Ham: I can help plan the next meal. I cannot approve leftovers by tasting them.';
  } else if(/berry|berries|apple|grape|peach|plum|avocado|carrot|celery|broccoli|cabbage|cucumber|pepper|tomato|lettuce|green|herb|fruit|banana|mango|tomatillo|okra|plantain|lime|lemon/.test(ingredient)){
   voices='💜 Juniper: Protect delicate produce from excess moisture and remove damaged pieces. Some fruits ripen on the counter before moving to the fridge.\n💚 Lil Dino: The right storage spot depends on the specific fruit or vegetable—check the guide above.\n🩵 Rook: If it is still sound but you cannot use it soon, see whether it can be frozen or cooked into a meal.\n🐹 Ham: Quality-control note: I can judge crunchiness in a recipe, not whether food is safe.';
  } else if(/freeze/.test(ingredient)){
   voices='📜 The Archivist: Seal freezer food well and label it with the name and date.\n🩵 Rook: Freeze ingredients while they are still in good condition, not after they spoil.\n💚 Lil Dino: Freezing preserves food; it does not make spoiled food safe.\n🐹 Ham: Frozen berries for smoothies? Finally, a plan I can support.';
  } else {
   voices='💚 Lil Dino: Use the ingredient-specific storage notes above rather than guessing.\n📜 The Archivist: Label opened packages and leftovers with the date and follow package directions.\n🧡 Chef Saffron: Keep the fridge at 40°F (4°C) or colder and prevent cross-contamination.\n🐹 Ham: I am the snack quality-control intern, not the food-safety inspector.';
  }
  tipText+='\n\n🍽️ THE FRIDGE CREW\n'+voices;
 }
 tipBox.textContent=tipText;
 tipBox.hidden=false;
 list.querySelectorAll('.tip-choice').forEach(choice=>{
  choice.setAttribute('aria-pressed',String(choice===button));
 });
 tipBox.scrollIntoView({behavior:'smooth',block:'nearest'});
});
const rookKnowledge=[
{names:['onion','onions','onion peel','onion peels','onion skins','shallot','shallots'],title:'🧅 Onions, shallots, and onion skins',tag:'COOK / COMPOST CHECK',text:'Use firm, sound onion pieces in soups, stir-fries, sauces, and stock. Clean dry onion skins can add color to some stocks, then be strained out. Compost skins only if your system accepts them; discard onions that are moldy, slimy, or badly decayed.'},
{names:['ginger','ginger peel','ginger scraps','ginger skin'],title:'🫚 Ginger scraps',tag:'REUSE / COMPOST CHECK',text:'Clean ginger peel and firm trimmings can flavor broth, tea, or stock; strain them out before serving. A firm piece with a viable bud may sprout when planted, but success varies. Compost only if your system accepts it, and discard moldy or soft rotten ginger.'},
{names:['shallot peel','shallot skins'],title:'🧅 Shallot skins',tag:'COMPOST CHECK',text:'Dry, clean shallot skins can go into many compost systems or be simmered with suitable stock ingredients and strained out. Check your compost rules and do not save scraps that are spoiled.'},
{names:['bok choy','pak choi','bok choy base','pak choi base'],title:'🥬 Bok choy and pak choi',tag:'REUSE / TRY REGROWING',text:'Slice tender stems and leaves into stir-fries, soups, dumplings, or noodle bowls. A healthy base may grow some leaves in shallow clean water with bright light; refresh the water often. It may not produce a full new plant.'},
{names:['napa cabbage','chinese cabbage','wong bok'],title:'🥬 Napa cabbage',tag:'REUSE / COMPOST CHECK',text:'Use crisp leaves and tender ribs in stir-fries, dumplings, kimchi-style preparations, or soups. Keep sound leftovers refrigerated and use promptly. Compost outer leaves if accepted by your system; discard slimy or moldy cabbage.'},
{names:['cabbage','cabbage core','cabbage leaves'],title:'🥬 Cabbage leaves and core',tag:'REUSE / COMPOST CHECK',text:'Thinly slice a sound core or outer leaves for soup, stir-fry, slaw, or fried rice. Compost trimmings if your system accepts them. Discard slimy, moldy, or foul-smelling cabbage.'},
{names:['lemongrass','lemongrass stalk','lemongrass ends'],title:'🌾 Lemongrass ends',tag:'REUSE / COMPOST CHECK',text:'Clean, firm lower stalks can infuse soup, curry, tea, and broth; bruise them to release aroma and remove before eating if fibrous. Some fresh stalk bases may root in water, but growth is not guaranteed. Compost unusable trimmings where accepted.'},
{names:['cilantro stems','coriander stems','cilantro roots','coriander roots'],title:'🌿 Cilantro stems and roots',tag:'USE THE WHOLE HERB',text:'Tender cilantro stems and well-cleaned roots are flavorful in sauces, marinades, curry pastes, soups, and stir-fries. Chop or pound them finely. Compost tough leftovers if your system accepts them; keep the herb refrigerated and discard slimy or spoiled parts.'},
{names:['scallion roots','spring onion roots','green onion roots'],title:'🌱 Scallion root ends',tag:'REGROW',text:'Place clean white root ends in a glass with the roots under water and the green tops above it. Keep in bright light and change water frequently. Harvest some green growth; for longer-term growth, try potting in soil. A full new onion is not guaranteed.'},
{names:['mushroom stems','shiitake stems','shiitake stem'],title:'🍄 Mushroom stems',tag:'REUSE / COMPOST CHECK',text:'Firm mushroom stems can flavor broth, sauces, dumpling fillings, or finely chopped stir-fries; some tougher stems are best strained from stock. Refrigerate promptly and discard slimy or spoiled mushrooms. Compost only if your system accepts them.'},
{names:['rice','cooked rice','leftover rice','rice scraps'],title:'🍚 Leftover rice',tag:'FOOD SAFETY FIRST',text:'Cooked rice is not a compost-style leftover to keep at room temperature: cool it quickly, refrigerate promptly, and use within a short safe window (commonly 3–4 days in a refrigerator at 40°F/4°C or below) or freeze it. Reheat thoroughly. If it sat out too long, discard it; reheating may not remove all hazards.'},
{names:['noodles','cooked noodles','leftover noodles','rice noodles'],title:'🍜 Leftover noodles',tag:'FOOD SAFETY FIRST',text:'Use plain, safely stored noodles in soup, stir-fries, or a chilled noodle bowl. Refrigerate promptly in a shallow container and use within 3–4 days; discard noodles left at room temperature too long or showing spoilage. Composting cooked foods depends on your system.'},
{names:['tofu','tofu scraps','leftover tofu'],title:'🧊 Tofu leftovers',tag:'FOOD SAFETY FIRST',text:'Keep tofu refrigerated and follow the package directions after opening. Use safely stored leftovers in soup, stir-fries, or rice bowls. Discard tofu that has been held too warm or shows signs of spoilage. Basic backyard compost may not accept it because it can attract pests.'},
{names:['soy sauce bottle','sauce bottle','glass sauce bottle'],title:'🫙 Empty sauce bottles',tag:'REUSE / RECYCLE CHECK',text:'Rinse a food-safe bottle and reuse it only if it is clean, undamaged, and easy to sanitize. Remove labels if needed and check local recycling rules for the material and lid. Never reuse containers that held non-food chemicals.'},
{names:['chili pepper','chili peppers','chili scraps','pepper seeds'],title:'🌶️ Chili and pepper scraps',tag:'COOK / COMPOST CHECK',text:'Sound pepper trimmings can go into cooked sauces, soups, or stock. Avoid touching eyes after handling hot peppers and wash hands and tools well. Compost scraps only if accepted by your system; discard moldy or spoiled peppers.'},
{names:['corn husk','corn husks','corn cob','corn cobs'],title:'🌽 Corn husks and cobs',tag:'COMPOST / STOCK CHECK',text:'Clean husks and cobs may be compostable where accepted; they break down more slowly when left whole. Cobs can also flavor stock, then should be removed. Do not compost husks with plastic, wax, or other non-compostable coatings.'},
{names:['sweet potato peel','sweet potato peels','sweet potato skins'],title:'🍠 Sweet potato peels',tag:'REUSE ONLY IF SOUND',text:'Peels from firm, sound sweet potatoes can be washed and cooked in suitable recipes. Store and cook promptly. Compost clean trimmings if your system accepts them; discard moldy, slimy, or rotten pieces.'},
{names:['edamame pods','soybean pods'],title:'🫛 Edamame pods',tag:'COMPOST CHECK',text:'Edamame pods are usually too fibrous to eat, but may be compostable in systems that accept food scraps. Chop them smaller to help breakdown. Follow your local compost program’s rules.'},
{names:['seaweed','nori','seaweed scraps'],title:'🌊 Seaweed and nori scraps',tag:'COMPOST RULES VARY',text:'Keep clean, unused seaweed scraps separate from wrappers and plastic. Compost acceptance varies, especially for salty or seasoned leftovers, so check your system. Do not reuse seaweed that has spoiled or been contaminated.'},
{names:['green onion','green onions','scallion','scallions','spring onion'],title:'🌱 Green onions',tag:'REGROW',text:'Place clean white root ends in a small glass with roots covered and tops above water. Keep in bright light and refresh water frequently. You can harvest some green growth, but a full new onion is not guaranteed; potting in soil may help longer-term growth.'},
{names:['romaine','lettuce','lettuce base'],title:'🥬 Romaine or lettuce base',tag:'TRY REGROWING',text:'A sound base may produce small leaves in shallow water with bright light. Change water regularly. Expect an experiment and some leaves, not necessarily a full new head.'},
{names:['celery','celery base'],title:'🥬 Celery base',tag:'TRY REGROWING',text:'A healthy celery base may produce leaves and small shoots in shallow water. Refresh water and provide light; move to soil if it develops roots. Results vary and may not produce a full celery bunch.'},
{names:['basil','mint','herb cutting','herb stems'],title:'🌿 Herb cuttings',tag:'REGROW',text:'Some herbs, including mint and basil, can root from healthy stems. Remove leaves from the part placed in clean water, refresh water often, and pot up after roots develop. Success depends on the herb and cutting.'},
{names:['carrot tops','carrot greens','carrot'],title:'🥕 Carrot tops',tag:'REGROW WITH LIMITS',text:'The crown may grow leafy greens, but it will not regrow a new carrot root. Only use the leaves in food if the carrot is sound and you can confidently identify the plant.'},
{names:['garlic','garlic clove'],title:'🧄 Sprouting garlic',tag:'PLANTING EXPERIMENT',text:'A sound sprouting clove can grow green shoots in soil. Growth varies; discard cloves that are moldy, mushy, or decaying.'},
{names:['coffee grounds','coffee filter','coffee filters'],title:'☕ Coffee grounds and paper filters',tag:'COMPOST CHECK',text:'Many compost systems accept used coffee grounds and plain paper filters. Add in moderation and follow your compost or municipal program’s rules. Grounds are not a complete fertilizer.'},
{names:['banana peel','banana peels','banana skin'],title:'🍌 Banana peels',tag:'COMPOST CHECK',text:'Often suitable for home compost where food scraps are accepted. Chopping helps them break down. Municipal programs differ, so check the local list.'},
{names:['lemon peel','lemon peels','citrus peel','orange peel','citrus'],title:'🍋 Citrus peel',tag:'REUSE / COMPOST CHECK',text:'Wash the fruit first; clean zest can flavor sugar, baking, dressings, and marinades. Avoid the bitter white pith when zesting. Compost peels only if your system accepts citrus.'},
{names:['eggshell','eggshells','egg shells'],title:'🥚 Eggshells',tag:'COMPOST CHECK',text:'Some compost systems accept eggshells; crushing helps them break down. They are not a quick cure for plant calcium problems. Wash hands and surfaces after handling raw eggs.'},
{names:['broccoli stems','broccoli stem','cauliflower stem','vegetable stems'],title:'🥦 Tender vegetable stems',tag:'REUSE IN COOKING',text:'Peel away tough outer parts if needed, then slice tender stems for stir-fries, soups, slaws, or roasting. Refrigerate and use promptly.'},
{names:['potato peel','potato peels','potato skins'],title:'🥔 Potato peels',tag:'REUSE ONLY IF SOUND',text:'Peels from sound potatoes can be cooked after washing and safe preparation. Do not use green, bitter, or heavily sprouted potatoes; discard them.'},
{names:['stale bread','dry bread','bread'],title:'🥖 Stale bread',tag:'CHECK CONDITION',text:'If it is merely dry and has no signs of spoilage, it may become croutons, breadcrumbs, or toast. If mold is present, discard it rather than trying to rescue it.'},
{names:['moldy bread','mouldy bread','mold','mould','moldy food','spoiled food','rotten food'],title:'⚠️ Moldy or spoiled food',tag:'DISCARD SAFELY',text:'Do not taste it to test safety. Bread and other porous foods can have mold beyond the visible spot; do not trim just the patch. Discard concerning spoiled food and clean the storage area.'},
{names:['glass jar','glass jars','jar','jars'],title:'🫙 Clean glass jars',tag:'REUSE / RECYCLE CHECK',text:'A clean, undamaged food jar may be reused for dry storage or crafts. Do not use ordinary jars for shelf-stable canning unless they are designed for that purpose and you follow tested instructions. Recycling acceptance varies locally.'},
{names:['egg carton','cardboard','paperboard','cardboard box'],title:'📦 Cardboard and egg cartons',tag:'RECYCLING CHECK',text:'Clean, dry cardboard is commonly recyclable where accepted. Food-soiled cardboard may be treated differently. Molded-pulp cartons may be compostable in some systems; foam and plastic cartons have different rules.'},
{names:['freezer scraps','freezer scrap bag','vegetable scraps','stock scraps','vegetable stock'],title:'🧊 Freezer scrap bag',tag:'REUSE IN COOKING',text:'Freeze sound vegetable trimmings promptly in a labeled, food-safe bag. Do not save spoiled or contaminated scraps. Simmer suitable scraps for stock, strain, and discard the spent solids.'},
{names:['meat scraps','meat','fish scraps','fish','dairy scraps','dairy','cheese','cooked leftovers'],title:'🍖 Meat, fish, dairy, and cooked scraps',tag:'COMPOST RULES VARY',text:'Basic backyard compost bins may exclude these items because they can attract pests or smell. Use only a system that explicitly accepts them, or follow local organics guidance.'},
{names:['cooking oil','oil','grease','fat'],title:'🛢️ Cooking oil and grease',tag:'SPECIAL DISPOSAL',text:'Never pour oil or grease down the drain. Let it cool and follow local disposal advice; larger amounts may have a collection option. Do not add oils to a basic compost bin unless its guidance allows it.'},
{names:['battery','batteries','electronics','phone','laptop'],title:'🔋 Batteries and electronics',tag:'SPECIAL DROP-OFF',text:'Do not put batteries or electronics in compost or ordinary recycling unless a local program specifically directs you there. Use an approved drop-off; lithium batteries can pose fire risks.'},
{names:['chemical container','cleaner bottle','pesticide','chemical','detergent bottle'],title:'🧴 Chemical containers',tag:'NEVER REUSE FOR FOOD',text:'Never reuse a container that held cleaners, pesticides, fuel, or other chemicals for food. Follow the product label and local hazardous-waste instructions.'},
{names:['compost','compost greens','browns','green scraps','brown leaves'],title:'♻️ Compost basics',tag:'SYSTEM DEPENDENT',text:'Many systems balance nitrogen-rich “greens” with carbon-rich “browns,” moisture, and air. Meat, dairy, oils, and compostable packaging may be excluded from some systems. Follow your bin or local program instructions.'},
{names:['food container','plastic container','container','leftovers','storage container'],title:'🧽 Clean food containers',tag:'REUSE SAFELY',text:'Wash food-safe containers with dish soap and water, check for cracks or lingering odors, and dry them. Do not use damaged containers or containers that held chemicals. Refrigerate perishable food promptly.'},
{names:['reuse','reduce waste','meal plan','planning','leftover planning'],title:'🗓️ Prevent waste before it starts',tag:'ROOK’S BEST TRICK',text:'Plan meals around the most perishable items first, label leftovers with dates, freeze extras promptly, and buy amounts you can realistically use. Do not rely on smell alone to judge food safety.'},
{names:['regrow','regrowing','what can regrow','regrow scraps'],title:'🌱 What can regrow?',tag:'REALISTIC EXPECTATIONS',text:'Green onion roots, some lettuce/celery bases, and some herb cuttings can produce new growth under the right conditions. Many scraps will not become a whole new vegetable. Treat it as an experiment, not a guarantee.'}
];
function rookSearch(query){
 const q=query.trim().toLowerCase();const results=document.getElementById('rookReuseResults');
 if(!q){results.innerHTML='<p>Rook needs a clue first. Try “onion peels,” “bok choy,” “lemongrass,” “rice,” or “moldy bread.”</p>';return;}
 const words=q.split(/\s+/).filter(Boolean);
 const ranked=rookKnowledge.map(item=>{let score=0;for(const name of item.names){const n=name.toLowerCase();if(n===q)score=Math.max(score,12);else if(n.includes(q)||q.includes(n))score=Math.max(score,7);else if(words.some(w=>w.length>2&&n.includes(w)))score=Math.max(score,3);}return {item,score};}).filter(x=>x.score>0).sort((a,b)=>b.score-a.score).slice(0,4);
 if(!ranked.length){results.innerHTML='<article class="rook-result-card"><h4>🕵️ No exact clue found</h4><p>Rook has no reliable entry for “'+q.replace(/[&<>"']/g,'')+'” yet. Try a broader item name or one of the example searches. For local recycling and compost rules, check your town or waste provider’s current list.</p></article>';return;}
 results.innerHTML=ranked.map(({item})=>'<article class="rook-result-card"><span class="rook-tag">'+item.tag+'</span><h4>'+item.title+'</h4><p>'+item.text+'</p><p><strong>Rook’s margin note:</strong> “Second chances are clever. Safe second chances are cleverer.”</p></article>').join('');
}
document.getElementById('rookReuseForm').addEventListener('submit',e=>{e.preventDefault();rookSearch(document.getElementById('rookReuseInput').value);});
document.querySelectorAll('[data-rook-query]').forEach(b=>b.addEventListener('click',()=>{const input=document.getElementById('rookReuseInput');input.value=b.dataset.rookQuery;rookSearch(input.value);}));
const rookSecrets=[
'Freeze small portions of sound vegetable trimmings in a labeled bag. When you have enough, simmer suitable scraps for stock. Spoiled scraps never belong in the save-for-later bag.',
'A lettuce base may grow a few leaves, but it is not a guaranteed replacement for a whole head. A small harvest still counts as a successful experiment.',
'Compost labels are not universal permission slips. A product accepted by one industrial composting program may not break down in a home bin.',
'Clean glass jars can be useful for dry pantry storage, but ordinary jars are not automatically safe for shelf-stable canning.',
'The most mysterious ingredient in the kitchen is “leftover.” Label it with its name and date so tomorrow-you does not have to solve a food-safety riddle.',
'Rook’s final clue: prevention beats rescue. Store ingredients well, plan portions, and freeze extras while they are still sound.'
];let rookSecretIndex=-1;
document.getElementById('rookRevealSecret').addEventListener('click',()=>{let next=Math.floor(Math.random()*rookSecrets.length);if(rookSecrets.length>1&&next===rookSecretIndex)next=(next+1)%rookSecrets.length;rookSecretIndex=next;document.getElementById('rookSecretResult').textContent='🔐 ROOK’S SECRET: '+rookSecrets[next];});
let rookClueTaps=0;
document.getElementById('rookClueButton').addEventListener('click',()=>{
 rookClueTaps++;
 const reveal=document.getElementById('rookClueReveal');
 const hint=document.getElementById('rookClueHint');
 if(rookClueTaps<3){hint.textContent=rookClueTaps===1?'It looks like a screw from a tiny hidden drawer…': 'There are three little scratches on its head. One more look?';return;}
 reveal.hidden=false;
 reveal.textContent='🗝️ ROOK’S HIDDEN DISCOVERY — Behind the loose board is a tiny jar labeled “For a rainy-day recipe.” Inside: a handwritten note from Ham: “I saved the last spoonful of strawberry syrup so we could turn tomorrow’s leftovers into something lovely.” Rook’s note underneath reads: “Even small things can have a second story. Just make sure they’re still safe to use.”';
 hint.textContent='Secret found!';
 document.getElementById('rookClueButton').textContent='🩵 Found it!';
 document.getElementById('rookClueButton').disabled=true;
});



// Secret Room prototype interactions: local to this HTML test file.
const secretPanels=['secretSearchPanel','secretDrawerPanel','secretFragmentPanel','secretMessagePanel'];
function resetSecretPanels(){secretPanels.forEach(id=>document.getElementById(id).hidden=true);['secretSearchResult','secretDrawerResult','secretFragmentResult','secretMessageResult','secretEasterResult'].forEach(id=>document.getElementById(id).textContent='');document.getElementById('secretSearchInput').value='';}
function showSecretPanel(id){secretPanels.forEach(pid=>document.getElementById(pid).hidden=pid!==id);}
document.getElementById('secretSearchTile').addEventListener('click',()=>showSecretPanel('secretSearchPanel'));
document.getElementById('secretDrawerTile').addEventListener('click',()=>showSecretPanel('secretDrawerPanel'));
document.getElementById('secretFragmentTile').addEventListener('click',()=>showSecretPanel('secretFragmentPanel'));
document.getElementById('secretMessageTile').addEventListener('click',()=>showSecretPanel('secretMessagePanel'));
const secretCharacterRecords=[
 {keys:['lil dino','dino'],title:'🦖 Character File: Lil Dino',hints:['Lil Dino is a curious, sarcastic green cook who notices details other people dismiss.','Pink appears in small accessories and details—a favorite color, not their main color.','A margin note warns: “Do not tell them what the open eye means yet.”','Their curiosity may lead them toward secrets the Archive would rather keep buried.']},
 {keys:['juniper','juniper vale'],title:'🌿 Character File: Juniper Vale',hints:['Juniper is a practical herbalist and a careful researcher of plants and ingredients.','She values independence and prefers useful truths over comforting guesses.','Her knowledge of herbs may help identify ingredients that do not appear in ordinary records.','A note says: “Juniper knows that what grows in a place can outlive the name of the place.”']},
 {keys:['rook'],title:'🩵 Character File: Rook',hints:['Rook is resourceful, direct, and associated with reuse, leftovers, and finding value in what others discard.','Turquoise is Rook’s signature color.','Rook may notice evidence hidden among things the Archive labels as waste.','A pencilled note reads: “Never throw away the scraps. Sometimes they are the only proof.”']},
 {keys:['ham','hammy'],title:'🐹 Character File: Ham',hints:['Ham runs the Cozy Café and takes quality control very seriously—especially tasting.','Ham’s café world includes drinks, treats, smoothies, and playful flavor combinations.','One character calls Ham “Hammy,” but the nickname is not used by everyone.','A café receipt has a strange note: “Someone ordered a drink from a town missing from every map.”']},
 {keys:['chef saffron','saffron'],title:'🍊 Character File: Chef Saffron',hints:['Chef Saffron brings confident dinner-station energy and loves flavorful meals.','Orange is Chef Saffron’s signature color.','Their cooking notes focus on practical technique as much as bold flavor.','A recipe margin reads: “The missing place had its own spice blend. No two surviving copies agree.”']},
 {keys:['archivist'],title:'✉️ Character File: The Archivist',hints:['The Archivist leaves messages in recipe margins and hidden records.','They believe an archive is defined as much by what is excluded as by what is preserved.','A warning says not to let the Archivist discover the page that should not exist.','The evidence raises a troubling question: is the Archivist protecting the truth—or controlling which truth survives?']}
];
let activeCharacterHints=null;let activeCharacterHintIndex=0;
const nextHintButton=document.getElementById('secretNextHint');
function showCharacterHint(){if(!activeCharacterHints)return;const out=document.getElementById('secretSearchResult');out.textContent=activeCharacterHints.title+' ('+(activeCharacterHintIndex+1)+' of '+activeCharacterHints.hints.length+') — '+activeCharacterHints.hints[activeCharacterHintIndex];nextHintButton.hidden=activeCharacterHintIndex>=activeCharacterHints.hints.length-1;nextHintButton.textContent='Reveal another hint';}
nextHintButton.addEventListener('click',()=>{if(activeCharacterHints&&activeCharacterHintIndex<activeCharacterHints.hints.length-1){activeCharacterHintIndex++;showCharacterHint();}});
document.getElementById('secretSearchForm').addEventListener('submit',event=>{event.preventDefault();const q=document.getElementById('secretSearchInput').value.trim().toLowerCase();const out=document.getElementById('secretSearchResult');activeCharacterHints=null;activeCharacterHintIndex=0;nextHintButton.hidden=true;if(!q){out.textContent='Enter a word or clue to search the records.';return;}const character=secretCharacterRecords.find(r=>r.keys.some(k=>q===k||q.includes(k)));if(character){activeCharacterHints=character;showCharacterHint();return;}const records=[{keys:['missing page','torn page','erased index','removed page'],title:'📄 Record: The Missing Page',text:'The tear is unusually clean. The index lists a page number, but no title. Someone removed the name, not the evidence.'},{keys:['forbidden recipe','guild','archive','erased recipe','shouldnt exist','shouldn’t exist'],title:'📜 Record: The Recipe That Shouldn’t Exist',text:'The official catalog denies this recipe ever existed. A margin note says it was hidden because it connected people and places the guilds wanted kept separate.'},{keys:['third bell','bell','three stars','third chime'],title:'🔔 Record: The Third Bell',text:'Three stars and a bell appear beside a cabinet entry. The note reads: “When the third bell is remembered, the drawer may open.”'},{keys:['ash flour','winter sugar','impossible ingredient','recipe fragment'],title:'🧩 Record: Fragmentary Ingredients',text:'Ash flour and winter sugar appear in incomplete notes. One ledger lists winter sugar beside a location field that has been scraped away. Its meaning is uncertain until the missing place is identified.'},{keys:['message','letter'],title:'✉️ Record: The Archivist',text:'“An archive is not only what it keeps. It is also what someone decided to leave out.”'}];const found=records.find(r=>r.keys.some(k=>q.includes(k)));out.textContent=found?found.title+' — '+found.text:'No clear record found for “'+q+'”. Try a character name, “missing page,” “winter sugar,” “third bell,” or “Archivist.”';});
document.getElementById('secretUnlockDrawer').addEventListener('click',()=>{const out=document.getElementById('secretDrawerResult');if(!window.secretDrawerUnlocked && window.secretFragmentCollected){window.secretDrawerUnlocked=true;out.textContent='🔓 DRAWER OPENED — Inside is a small card: “The name was removed from the first page. Search for the record that the guilds erased.” You have uncovered a clue, not the whole truth.';}else if(!window.secretDrawerUnlocked){out.textContent='The lock clicks once, then stops. It needs the Recipe With No Name fragment first. Inspect the fragment on the central desk.';}else{out.textContent='🔓 DRAWER OPENED — Inside is a small card: “The name was removed from the first page. Search for the record that the guilds erased.” You have uncovered a clue, not the whole truth.';}});
document.getElementById('secretCollectFragment').addEventListener('click',()=>{window.secretFragmentCollected=true;document.getElementById('secretFragmentResult').textContent='📜 FRAGMENT COLLECTED — Three symbols are recorded in your discoveries: a sprig, a bell, and an open eye. The bell may be connected to a locked drawer.';document.getElementById('secretUnlockDrawer').textContent='Use the collected fragment to inspect the lock';});
document.getElementById('secretRevealMessage').addEventListener('click',()=>{if(window.secretMessageTurned){document.getElementById('secretMessageResult').textContent='On the back: “If you found this, the first lock has already failed. Trust the recipe’s ingredients less than the spaces between its lines.”';return;}window.secretMessageTurned=true;document.getElementById('secretMessageResult').textContent='The paper is thinner than it should be. A faint impression shows three stars beside a bell—the same symbol on the cabinet drawer.';});
document.getElementById('secretEasterEgg').addEventListener('click',()=>{const out=document.getElementById('secretEasterResult');if(!window.secretStarTaps)window.secretStarTaps=0;window.secretStarTaps++;if(window.secretStarTaps<3){out.textContent=window.secretStarTaps===1?'The star feels slightly raised, as if it were pressed into the wood after the desk was made.':'A tiny line appears beneath it: “Listen between the bells.” One more careful look?';}else{out.textContent='👁️ SECRET DISCOVERED — Beneath the purple star is a tiny engraved open eye. The Archivist’s note appears: “Not every witness is a person. Some rooms remember what people try to forget.”';document.getElementById('secretEasterEgg').textContent='Secret discovered';document.getElementById('secretEasterEgg').disabled=true;}});

// v49: save Secret Room investigation progress across visits in the same browser.
const ARCHIVE_SAVE_KEY = 'lilDinoSecretArchiveProgress_v1';
function readArchiveProgress(){
 try { const raw=localStorage.getItem(ARCHIVE_SAVE_KEY); return raw?JSON.parse(raw):{}; }
 catch(error){ return {}; }
}
function writeArchiveProgress(progress){
 try { localStorage.setItem(ARCHIVE_SAVE_KEY,JSON.stringify(progress)); document.getElementById('archiveSaveStatus').textContent='💾 Archive progress saved in this browser.'; return true; }
 catch(error){ document.getElementById('archiveSaveStatus').textContent='⚠️ This browser did not allow local saving. Progress may reset when you leave.'; return false; }
}
let archiveProgress = readArchiveProgress();
if(!archiveProgress || typeof archiveProgress!=='object') archiveProgress={};
if(!Array.isArray(archiveProgress.evidenceSeen)) archiveProgress.evidenceSeen=[];
const caseEvidenceSeen = new Set(archiveProgress.evidenceSeen);
const caseEvidenceText = {
 fragment: 'Evidence A — The title was torn away cleanly. The sprig, bell, and open eye were drawn in ink, not printed as part of the recipe.',
 drawer: 'Evidence B — The three-star lock matches the bell mark in the fragment. The drawer was designed to be opened by someone who found the page.',
 letter: 'Evidence C — The letter says, “Do not mistake a missing name for a missing person.” It refers to deliberate removal, not age or damage.'
};
function renderSavedCaseProgress(){
 document.querySelectorAll('[data-case-evidence]').forEach(btn=>btn.classList.toggle('found',caseEvidenceSeen.has(btn.dataset.caseEvidence)));
 document.getElementById('caseEvidenceResult').textContent='Case status: '+caseEvidenceSeen.size+' of 3 evidence items examined.';
 document.getElementById('caseConclusion').hidden=caseEvidenceSeen.size!==3 && !archiveProgress.case001Solved;
 if(archiveProgress.case001Solved){
  const reward=document.getElementById('caseReward'); reward.hidden=false;
  reward.textContent='🔓 CASE SOLVED — The evidence supports deliberate removal. The Archive records your first finding: “A missing title is not proof that a recipe never existed.” Reward unlocked: Case File 001 — The Erased Name. The Archivist leaves one final note: “Good. Now ask who benefited from its disappearance.”';
  document.getElementById('cabinetLocked').hidden=true;
  document.getElementById('cabinetUnlocked').hidden=false;
  document.getElementById('cabinetIntro').textContent='The brass seal clicks open. One folder waits inside, its label written in the Archivist’s precise hand.';
 }
}
document.querySelectorAll('[data-case-evidence]').forEach(btn=>btn.addEventListener('click',()=>{
 const key=btn.dataset.caseEvidence; caseEvidenceSeen.add(key); archiveProgress.evidenceSeen=[...caseEvidenceSeen]; writeArchiveProgress(archiveProgress); btn.classList.add('found');
 document.getElementById('caseEvidenceResult').textContent=caseEvidenceText[key]+' Evidence examined: '+caseEvidenceSeen.size+' of 3.';
 if(caseEvidenceSeen.size===3) document.getElementById('caseConclusion').hidden=false;
}));
document.getElementById('openCaseFile001').addEventListener('click',()=>{const details=document.getElementById('caseFile001Details');details.hidden=!details.hidden;document.getElementById('openCaseFile001').textContent=details.hidden?'📁 Open Case File 001 — The Erased Name':'📂 Close Case File 001';});
document.querySelectorAll('[data-case-answer]').forEach(btn=>btn.addEventListener('click',()=>{
 const reward=document.getElementById('caseReward'); reward.hidden=false;
 if(btn.dataset.caseAnswer==='right'){
  archiveProgress.case001Solved=true; archiveProgress.evidenceSeen=[...caseEvidenceSeen]; writeArchiveProgress(archiveProgress);
  reward.textContent='🔓 CASE SOLVED — The evidence supports deliberate removal. The Archive records your first finding: “A missing title is not proof that a recipe never existed.” Reward unlocked: Case File 001 — The Erased Name. The Archivist leaves one final note: “Good. Now ask who benefited from its disappearance.”';
  document.getElementById('cabinetLocked').hidden=true;
  document.getElementById('cabinetUnlocked').hidden=false;
  document.getElementById('cabinetIntro').textContent='The brass seal clicks open. One folder waits inside, its label written in the Archivist’s precise hand.';
 } else {
  reward.textContent='Not quite. Compare the clean tear, the matching lock symbol, and the letter’s warning. The clues point toward a deliberate act. You can examine any evidence again before choosing.';
 }
}));

// v51: persistent Discovery Journal records the brass eye and Impossible Ingredient lead.
// v50: two clue-based drawers; their unlocks persist with Case File 001.
function renderDiscoveryJournal(){
 const eyeFound=!!archiveProgress.drawerOneUnlocked;
 const ingredientFound=!!archiveProgress.drawerTwoUnlocked;
 document.getElementById('journalEyeStatus').textContent=eyeFound?'✅ Recovered and saved — Drawer I is open.':'🔒 Not yet recovered. Open Drawer I to find the token.';
 document.getElementById('journalIngredientStatus').textContent=ingredientFound?'✅ Recovered and saved — Drawer II is open.':'🔒 Not yet recovered. Open Drawer II to uncover the hidden Archive slip.';
 document.getElementById('journalArtifactEye').classList.toggle('drawer-open',eyeFound);
 document.getElementById('journalLeadIngredient').classList.toggle('drawer-open',ingredientFound);
 const next=document.getElementById('journalNextCase');
 if(eyeFound && ingredientFound){next.textContent='🗝️ CASE FILE 002 LEAD RECORDED — The Impossible Ingredient. The journal has preserved both discoveries. This lead is ready to guide the next investigation.';next.classList.add('found');}
 else {next.textContent='📌 The next case remains sealed until both drawer discoveries are recorded.';next.classList.remove('found');}
}
function renderPuzzleDrawers(){
 const oneOpen=!!archiveProgress.drawerOneUnlocked;
 const twoOpen=!!archiveProgress.drawerTwoUnlocked;
 const one=document.getElementById('drawerOneResult');
 const two=document.getElementById('drawerTwoResult');
 if(oneOpen){one.textContent='🔓 DRAWER OPEN — Inside is a brass token stamped with a tiny open eye. A note reads: “The second lock remembers the recipe’s margin.”';document.getElementById('puzzleDrawerOne').classList.add('drawer-open');document.getElementById('drawerOneAnswer').disabled=true;document.querySelector('#drawerOneForm button').disabled=true;}
 if(twoOpen){two.textContent='🔓 DRAWER OPEN — Beneath the lining is a hidden Archive slip: “The first erased recipe was not the only one. Follow the ingredient that appears where no ingredient should be.” Keep this lead; it may matter in a later case.';document.getElementById('puzzleDrawerTwo').classList.add('drawer-open');document.getElementById('drawerTwoAnswer').disabled=true;document.getElementById('drawerTwoSubmit').disabled=true;}
 else if(oneOpen){two.textContent='The first drawer is open. Use the recipe’s three margin symbols to try this lock.';}
 renderDiscoveryJournal();
}
document.getElementById('drawerOneForm').addEventListener('submit',event=>{
 event.preventDefault(); const answer=document.getElementById('drawerOneAnswer').value.trim().toLowerCase().replace(/[^a-z ]/g,'').replace(/\s+/g,' '); const out=document.getElementById('drawerOneResult');
 if(!archiveProgress.case001Solved){out.textContent='The lock will not turn yet. Solve Case File 001 first; the cabinet must recognize your discovery.';return;}
 if(answer==='third bell'||answer==='third chime') {archiveProgress.drawerOneUnlocked=true;writeArchiveProgress(archiveProgress);renderPuzzleDrawers();}
 else {out.textContent='The lock gives a quiet click but stays shut. Search the Archive for “third bell” and read the catalog note.';}
});
document.getElementById('drawerTwoForm').addEventListener('submit',event=>{
 event.preventDefault(); const answer=document.getElementById('drawerTwoAnswer').value.trim().toLowerCase().replace(/[^a-z ]/g,'').replace(/\s+/g,' '); const out=document.getElementById('drawerTwoResult');
 if(!archiveProgress.drawerOneUnlocked){out.textContent='This lock is still sealed. Open Drawer I first.';return;}
 if(answer==='sprig bell open eye'||answer==='sprig bell eye') {archiveProgress.drawerTwoUnlocked=true;writeArchiveProgress(archiveProgress);renderPuzzleDrawers();}
 else {out.textContent='The symbols do not align. Revisit the recipe fragment: read the three symbols in order.';}
});

// v53: Case File 002 — The Impossible Ingredient, unlocked only by the two saved drawer discoveries.
const case002Seen = new Set(Array.isArray(archiveProgress.case002EvidenceSeen) ? archiveProgress.case002EvidenceSeen : []);
const case002EvidenceText = {
 ledger: 'Evidence A — The old ingredient ledger lists “winter sugar” on a line where the location field has been scraped away. The quantity is recorded, but the source is missing.',
 margin: 'Evidence B — A recipe margin says: “Use only when the road is absent.” The handwriting matches the note found beneath Drawer II.',
 map: 'Evidence C — The Archive map has a clean, empty patch between two named towns. A faint line continues beneath the blank space, as if a place was removed without erasing the route.'
};
function renderCase002(){
 const unlocked=!!archiveProgress.drawerOneUnlocked && !!archiveProgress.drawerTwoUnlocked;
 document.getElementById('case002Locked').hidden=unlocked;
 document.getElementById('case002Work').hidden=!unlocked;
 document.getElementById('case002Intro').textContent=unlocked?'The journal’s two discoveries fit together. The brass eye marks the witness; the hidden slip points to an ingredient where none should be. Examine all three records.':'The Discovery Journal has recorded both drawer discoveries. A new investigation can begin: find the ingredient that appears where no ingredient should be.';
 document.querySelectorAll('[data-case002-evidence]').forEach(btn=>btn.classList.toggle('found',case002Seen.has(btn.dataset.case002Evidence)));
 document.getElementById('case002EvidenceResult').textContent='Evidence examined: '+case002Seen.size+' of 3.';
 document.getElementById('case002Conclusion').hidden=case002Seen.size!==3 && !archiveProgress.case002Solved;
 const reward=document.getElementById('case002Reward');
 if(archiveProgress.case002Solved){reward.hidden=false;reward.textContent='🔓 CASE FILE 002 SOLVED — “Winter sugar” is a trace of a place removed from the Archive’s records. The journal records a new lead: the map was altered, not merely damaged.';document.getElementById('caseFile002Status').textContent='✅ Unlocked — The Impossible Ingredient';document.getElementById('caseFile002Details').hidden=false;}
}
document.querySelectorAll('[data-case002-evidence]').forEach(btn=>btn.addEventListener('click',()=>{
 if(!(archiveProgress.drawerOneUnlocked && archiveProgress.drawerTwoUnlocked))return;
 const key=btn.dataset.case002Evidence;case002Seen.add(key);archiveProgress.case002EvidenceSeen=[...case002Seen];writeArchiveProgress(archiveProgress);btn.classList.add('found');
 document.getElementById('case002EvidenceResult').textContent=case002EvidenceText[key]+' Evidence examined: '+case002Seen.size+' of 3.';
 if(case002Seen.size===3)document.getElementById('case002Conclusion').hidden=false;
}));
document.querySelectorAll('[data-case002-answer]').forEach(btn=>btn.addEventListener('click',()=>{
 const reward=document.getElementById('case002Reward');reward.hidden=false;
 if(btn.dataset.case002Answer==='right'){
  archiveProgress.case002Solved=true;archiveProgress.case002EvidenceSeen=[...case002Seen];writeArchiveProgress(archiveProgress);renderCase002();
 }else{reward.textContent='Not quite. Compare the blank location field, the note about an absent road, and the gap on the map. What do all three suggest was removed?';}
}));

// v54: Case File 003 follows Case File 002 and records its page fragment persistently.
function renderCase003(){
 const solved=!!archiveProgress.case002Solved;
 document.getElementById('case003Gate').hidden=solved;
 document.getElementById('case003Work').hidden=!solved;
 if(!solved) document.getElementById('case003Gate').textContent='🔒 This page remains sealed until Case File 002 has been solved.';
 if(archiveProgress.case003PageFound){
  document.getElementById('recordCase003Page').textContent='✅ Page recorded in the journal';
  document.getElementById('recordCase003Page').disabled=true;
  document.getElementById('case003Result').textContent='📖 PAGE RECORDED — The page hints that names, places, and people are being erased from history. The warning suggests the Archivist may know more than they have revealed.';
 }
}
document.getElementById('recordCase003Page').addEventListener('click',()=>{
 if(!archiveProgress.case002Solved)return;
 archiveProgress.case003PageFound=true;
 writeArchiveProgress(archiveProgress);
 renderCase003();
});

renderSavedCaseProgress();
renderPuzzleDrawers();
renderCase002();
renderCase003();

document.getElementById('close').addEventListener('click',()=>{
 panel.classList.remove('show');
 activeRoom='';
 tipBox.hidden=true;
});
})();
</script>
</body>
</html>
