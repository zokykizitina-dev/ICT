import { useState } from "react";

const TELEGRAM = "https://t.me/+9tBvHeWAvYdlZWQ0";
const YOUTUBE_BASE = "https://youtu.be/tmeCWULSTHc";

const C = {
  bg: "#090b10", panel: "#11141c", card: "#161a26",
  border: "#1c2133", gold: "#f0b429", text: "#cdd5e0",
  muted: "#4e5a72", bull: "#26a69a", bear: "#ef5350",
  purple: "#9c6fe4", blue: "#4fc3f7", orange: "#ff6b35", green: "#4caf50",
};

const modules = [
  {
    id: 1, icon: "🎯", title: "Introduction", subtitle: "Présentation du mentorship",
    timestamp: "00:00:13", seconds: 13, color: C.gold,
    lessons: [
      {
        title: "Qu'est-ce que ce mentorship ?", timestamp: "00:00:13", seconds: 13,
        mindmap: {
          center: "Mentorship\nICT",
          nodes: [
            { label: "NQ Futures", angle: 0 },
            { label: "Thinkorswim\nlive", angle: 60 },
            { label: "Paper\nTrading", angle: 120 },
            { label: "Indépend-\nance", angle: 180 },
            { label: "Pas de\nSignals", angle: 240 },
            { label: "Résultats\nRéels", angle: 300 },
          ],
        },
        points: [
          "Mentorship axé sur les Futures indices : NQ, ES, YM",
          "Les trades montrés sont RÉELS — compte live Thinkorswim (fond vert = live, orange = demo)",
          "Enseignement via TradingView paper trading pour les étudiants",
          "Objectif final : indépendance totale — tu n'as besoin que du chart",
          "Ne pas essayer de trader avec des fonds réels au départ",
        ],
      },
      {
        title: "Pourquoi viser l'indépendance ?", timestamp: "00:09:34", seconds: 574,
        mindmap: {
          center: "Liberté\ndu Trader",
          nodes: [
            { label: "Pas de\nBlackbox", angle: 0 },
            { label: "Pas de\nSignals", angle: 72 },
            { label: "Chart seul\nsuffit", angle: 144 },
            { label: "Pensée\npropre", angle: 216 },
            { label: "Pas\nesclave", angle: 288 },
          ],
        },
        points: [
          "Les signal services te rendent captif — tu ne comprends rien",
          "Un blackbox system ne t'apprend pas à lire le marché",
          "ICT enseigne la LOGIQUE derrière les mouvements",
          "Une fois les règles apprises : chart seul suffit, rien d'autre",
          "L'indépendance = le vrai edge à long terme",
        ],
      },
    ],
  },
  {
    id: 2, icon: "📐", title: "Les Bases", subtitle: "Handle, Micro, 3 marchés",
    timestamp: "00:04:40", seconds: 280, color: C.blue,
    lessons: [
      {
        title: "Qu'est-ce qu'un Handle ?", timestamp: "00:04:40", seconds: 280,
        mindmap: {
          center: "Handle\n= 4 Ticks",
          nodes: [
            { label: "ES: $50\npar handle", angle: 0 },
            { label: "NQ: $20\npar handle", angle: 90 },
            { label: "NQ plus\nrapide", angle: 180 },
            { label: "Micro: fraction\ndu full", angle: 270 },
          ],
        },
        points: [
          "1 Handle = 4 ticks (fluctuation minimale du contrat)",
          "E-mini S&P (ES) : 1 handle = 4 × $12.50 = $50",
          "E-mini NASDAQ (NQ) : 1 handle = $20 — plus rapide, plus agressif",
          "Sur le trade montré : 100+ handles capturés en une session",
          "Objectif ICT : des GROS moves, pas des micro-scalps 3-5 handles",
        ],
      },
      {
        title: "Micro vs Full Contract", timestamp: "00:05:30", seconds: 330,
        mindmap: {
          center: "Les 3\nMarchés",
          nodes: [
            { label: "NQ\n(NASDAQ)", angle: 0 },
            { label: "ES\n(S&P 500)", angle: 90 },
            { label: "YM\n(Dow)", angle: 180 },
            { label: "Micro\n= fraction", angle: 270 },
          ],
        },
        points: [
          "Full NQ = environ $17,000 de marge requise",
          "Full ES = environ $12,500 de marge requise",
          "Micro = fraction du full contract — idéal pour apprendre",
          "Micro : risque très réduit, multiplicateur de tick plus petit",
          "YM (Dow) : valable mais moins enseigné dans ce mentorship",
          "Discount broker = levier élevé mais risque de se faire brûler",
        ],
      },
    ],
  },
  {
    id: 3, icon: "📊", title: "Multi-Timeframe", subtitle: "Weekly → Daily → Hourly",
    timestamp: "00:12:21", seconds: 741, color: C.purple,
    lessons: [
      {
        title: "Weekly Chart : Bias Directionnel", timestamp: "00:13:17", seconds: 797,
        mindmap: {
          center: "Weekly\nBias",
          nodes: [
            { label: "Haussier\nou Baissier ?", angle: 0 },
            { label: "Saisonna-\nlité", angle: 72 },
            { label: "Fed &\nTaux", angle: 144 },
            { label: "Earnings\nSaison", angle: 216 },
            { label: "Draw on\nLiquidity", angle: 288 },
          ],
        },
        points: [
          "Chaque weekend : est-ce que la bougie weekly va monter ou descendre ?",
          "On ne prédit PAS la clôture exacte — juste la direction",
          "Prix = comme un trombone attiré par un aimant vers certains niveaux",
          "Facteurs : saisonnalité, Fed/taux, earnings, momentum global",
          "Le bias weekly = boussole de toute la semaine de trading",
          "Si un setup se présente le 1er jour → on prend et on est satisfait",
        ],
      },
      {
        title: "Daily Chart : Swing Highs & Lows", timestamp: "00:16:23", seconds: 983,
        mindmap: {
          center: "Daily\nChart",
          nodes: [
            { label: "Swing\nHighs", angle: 0 },
            { label: "Buy Stops\nau-dessus", angle: 72 },
            { label: "Swing\nLows", angle: 144 },
            { label: "Sell Stops\nen-dessous", angle: 216 },
            { label: "Draw on\nLiquidity", angle: 288 },
          ],
        },
        points: [
          "Majorité de ton analyse se fait sur ce timeframe",
          "Au-dessus des vieux highs → Buy Stops (BSL)",
          "En-dessous des vieux lows → Sell Stops (SSL)",
          "Le marché gravite vers ces niveaux de liquidité",
          "Large funds et institutions regardent ces mêmes niveaux",
          "Imbalances (FVG) visibles aussi sur le daily",
        ],
      },
      {
        title: "Hourly Chart : Framework Semaine", timestamp: "00:19:35", seconds: 1175,
        mindmap: {
          center: "1H\nFramework",
          nodes: [
            { label: "Lundi\nminuit NY", angle: 0 },
            { label: "Vendredi\nclôture", angle: 90 },
            { label: "Niveaux\nDaily transposés", angle: 180 },
            { label: "ST High\n& Low", angle: 270 },
          ],
        },
        points: [
          "Délimiter la semaine : lundi minuit NY → vendredi clôture",
          "Transposer les niveaux importants du daily sur l'hourly",
          "Identifier le short-term high et low de la consolidation",
          "Consolidation → puis soit SSL pris, soit BSL pris en premier",
          "Le niveau daily visé = 'Old Daily Low' → marché doit y aller",
        ],
      },
    ],
  },
  {
    id: 4, icon: "🔑", title: "Concepts ICT", subtitle: "Liquidité · FVG · BMS · Stop Hunt",
    timestamp: "00:17:13", seconds: 1033, color: C.orange,
    lessons: [
      {
        title: "Buy Stops & Sell Stops (Liquidité)", timestamp: "00:17:13", seconds: 1033,
        mindmap: {
          center: "Liquidité",
          nodes: [
            { label: "BSL\nBuy Stops", angle: 0 },
            { label: "Au-dessus\ndes highs", angle: 60 },
            { label: "SSL\nSell Stops", angle: 120 },
            { label: "En-dessous\ndes lows", angle: 180 },
            { label: "Imbalance\n(FVG)", angle: 240 },
            { label: "Draw on\nLiquidity", angle: 300 },
          ],
        },
        points: [
          "Au-dessus des vieux highs → Buy Stops (BSL) s'accumulent",
          "En-dessous des vieux lows → Sell Stops (SSL) s'accumulent",
          "Le marché se dirige vers 2 choses : Stops OU Imbalances",
          "Smart Money a BESOIN de cette liquidité pour trader de grosses positions",
          "Sans liquidité = impossible d'entrer/sortir de grosses positions",
        ],
      },
      {
        title: "Engineering Liquidity — Stop Hunt", timestamp: "00:20:57", seconds: 1257,
        mindmap: {
          center: "Stop\nHunt",
          nodes: [
            { label: "Piège les\nretail", angle: 0 },
            { label: "SSL pris\nd'abord", angle: 90 },
            { label: "Shorts\npiégés", angle: 180 },
            { label: "BSL run\nensuite", angle: 270 },
          ],
        },
        points: [
          "Bearish : le marché DESCEND d'abord pour piéger les breakout sellers",
          "Ces traders retail entrent short sur la cassure → piégés",
          "Ensuite le marché MONTE pour prendre les Buy Stops (BSL)",
          "Ces BSL = contrepartie parfaite pour Smart Money qui veut shorter",
          "Avant CHAQUE grand move → toujours anticiper un stop hunt opposé",
          "C'est mécanique, algorithmique — pas du hasard",
        ],
      },
      {
        title: "Fair Value Gap (FVG) — Imbalance", timestamp: "00:29:58", seconds: 1798,
        mindmap: {
          center: "Fair Value\nGap",
          nodes: [
            { label: "1 bougie\nsans overlap", angle: 0 },
            { label: "High N-1 /\nLow N+1", angle: 90 },
            { label: "Zone\nd'entrée", angle: 180 },
            { label: "Prix revient\ntoujours", angle: 270 },
          ],
        },
        points: [
          "1 seule bougie passe sans aucun overlap avec les voisines = FVG",
          "Zone délimitée : High de la bougie N-1 / Low de la bougie N+1",
          "Algorithme DOIT revenir combler cette zone pour équilibrer le prix",
          "C'est la ZONE D'ENTRÉE principale du setup ICT",
          "Concept introduit par ICT en 2016 — copié depuis par beaucoup",
          "FVG haussier = buy-side imbalance / FVG baissier = sell-side",
        ],
      },
      {
        title: "Break in Market Structure (BMS)", timestamp: "00:27:50", seconds: 1670,
        mindmap: {
          center: "BMS",
          nodes: [
            { label: "Swing low\ncassé = BMS↓", angle: 0 },
            { label: "Swing high\ncassé = BMS↑", angle: 90 },
            { label: "Timeframe\n1-2-3 min", angle: 180 },
            { label: "→ Chercher\nFVG ensuite", angle: 270 },
          ],
        },
        points: [
          "Un swing low récent est cassé → BMS baissier confirmé",
          "Un swing high récent est cassé → BMS haussier confirmé",
          "Sur indices : chercher sur timeframe 1, 2 ou 3 minutes",
          "Le BMS = signal que la direction du marché a changé",
          "Après le BMS → attendre le retracement dans le FVG pour entrer",
          "Ne pas entrer directement sur le BMS — attendre le FVG",
        ],
      },
    ],
  },
  {
    id: 5, icon: "⚡", title: "Le Setup Complet", subtitle: "Les 5 étapes de A à Z",
    timestamp: "00:23:57", seconds: 1437, color: C.green,
    lessons: [
      {
        title: "Étape 1 — Hauts Relatifs Égaux (15-min)", timestamp: "00:23:57", seconds: 1437,
        mindmap: {
          center: "Equal\nHighs\n(BSL)",
          nodes: [
            { label: "2+ highs\nmême niveau", angle: 0 },
            { label: "Retail = voit\nrésistance", angle: 120 },
            { label: "Buy Stops\nau-dessus", angle: 240 },
          ],
        },
        points: [
          "Identifier 2 ou + highs au même niveau sur 15-min",
          "Retail les voit comme résistance → placent stop loss juste au-dessus",
          "Ces stop loss = Buy Stops qui s'accumulent au-dessus",
          "Le marché DOIT venir les chercher avant de baisser vraiment",
          "C'est le pool de liquidité BSL qui sera la cible du stop hunt",
        ],
      },
      {
        title: "Étape 2 — Run sur BSL + BMS (2-min)", timestamp: "00:26:34", seconds: 1594,
        mindmap: {
          center: "BSL Run\n+ BMS",
          nodes: [
            { label: "Dépasse\nles hauts", angle: 0 },
            { label: "Grosse\nbougie bear", angle: 90 },
            { label: "Casse un\nswing low", angle: 180 },
            { label: "BMS\nconfirmé", angle: 270 },
          ],
        },
        points: [
          "Le marché dépasse les hauts égaux → BSL swept (stop hunt exécuté)",
          "Immédiatement après : grosse bougie baissière apparaît",
          "Cette bougie casse un swing low récent → BMS baissier confirmé",
          "Le gap créé par cette bougie = le FVG dans lequel on va entrer",
          "Passer sur 2-min pour voir ce setup avec précision",
        ],
      },
      {
        title: "Étape 3 — FVG = Zone d'Entrée Short", timestamp: "00:29:58", seconds: 1798,
        mindmap: {
          center: "Entrée\nFVG\nShort",
          nodes: [
            { label: "Prix remonte\ndans FVG", angle: 0 },
            { label: "SHORT dès\nentrée FVG", angle: 120 },
            { label: "Stop: dessus\ndu BMS high", angle: 240 },
          ],
        },
        points: [
          "Après le BMS, le prix remonte dans la zone FVG",
          "Dès que le prix entre dans le FVG → VENDRE SHORT",
          "Entrer quand ça monte = contre-intuitif mais correct",
          "Stop loss : au-dessus du high de la bougie BMS",
          "Sur Micro : risque très limité en dollar",
          "Si raté sur 2-min → descendre sur 1-min pour trouver un FVG plus petit",
        ],
      },
      {
        title: "Étape 4 — Liquidity Matrix 50%", timestamp: "00:35:05", seconds: 2105,
        mindmap: {
          center: "50%\nMatrix",
          nodes: [
            { label: "Range\ndu jour H-L", angle: 0 },
            { label: "Premium\n> 50% cher", angle: 90 },
            { label: "Discount\n< 50% bon", angle: 180 },
            { label: "Short en\npremium", angle: 270 },
          ],
        },
        points: [
          "Prendre le range du jour : Low du jour → High du jour",
          "Fibonacci 50% = séparation Premium / Discount",
          "Au-dessus du 50% = Premium (marché cher) → zone pour shorter",
          "En-dessous du 50% = Discount → zone pour acheter",
          "FVG en zone premium + bias baissier = setup idéal short",
          "L'algorithme va de premium vers discount automatiquement",
        ],
      },
      {
        title: "Étape 5 — Target : SSL + Imbalance", timestamp: "00:38:31", seconds: 2311,
        mindmap: {
          center: "Target\nObjectif",
          nodes: [
            { label: "Sell Stops\nen-dessous", angle: 0 },
            { label: "FVG non\ncomblé", angle: 120 },
            { label: "Target\nle + proche", angle: 240 },
          ],
        },
        points: [
          "Target = vieux lows avec sell stops en-dessous (SSL)",
          "OU une imbalance (FVG) non comblée en-dessous du prix",
          "Choisir TOUJOURS le target le plus proche d'abord",
          "Low hanging fruit : ne pas être trop ambitieux au départ",
          "Laisser le marché aller plus loin sans toi = OK",
          "100-130 handles sur NQ = excellent trade, largement suffisant",
        ],
      },
    ],
  },
  {
    id: 6, icon: "📝", title: "Pratique", subtitle: "Devoirs · Formule · Conseils",
    timestamp: "00:46:17", seconds: 2777, color: C.bear,
    lessons: [
      {
        title: "La Formule Complète ICT", timestamp: "00:47:47", seconds: 2867,
        mindmap: {
          center: "Formule\nICT",
          nodes: [
            { label: "1. Bias\nWeekly", angle: 0 },
            { label: "2. Pool\nLiquidité", angle: 60 },
            { label: "3. Run\nsur pool", angle: 120 },
            { label: "4. BMS\nconfirmé", angle: 180 },
            { label: "5. Entrée\nFVG", angle: 240 },
            { label: "6. Target\nSSL/FVG", angle: 300 },
          ],
        },
        points: [
          "① Bias Weekly : haussier ou baissier cette semaine ?",
          "② Identifier le pool de liquidité ciblé (BSL si bearish)",
          "③ Attendre que le marché run sur ce pool (stop hunt)",
          "④ Confirmer le BMS sur 2-min après le stop hunt",
          "⑤ Entrer sur le FVG créé par la bougie BMS",
          "⑥ Target = SSL ou FVG non comblé sous le 50% du range",
        ],
      },
      {
        title: "Homework — Comment Backtester", timestamp: "00:46:17", seconds: 2777,
        mindmap: {
          center: "Homework",
          nodes: [
            { label: "Tous les\ncharts NQ/ES", angle: 0 },
            { label: "Multi-TF\nWeekly→2min", angle: 72 },
            { label: "Chercher\nBMS + FVG", angle: 144 },
            { label: "Journal\nde trading", angle: 216 },
            { label: "Compter\nles handles", angle: 288 },
          ],
        },
        points: [
          "Aller sur TOUS les charts e-mini Futures (NQ, ES, YM)",
          "Analyser dans l'ordre : Weekly → Daily → 1H → 15min → 2min",
          "Chercher les BMS après pool de liquidité pris en opposition",
          "Logger dans un journal : combien de handles offerts ?",
          "Répéter des semaines/mois — pas d'échappatoire au backtesting",
          "TradingView Replay = outil pour simuler en temps réel",
        ],
      },
      {
        title: "Conseils de Développement", timestamp: "00:15:35", seconds: 935,
        mindmap: {
          center: "Développe-\nment",
          nodes: [
            { label: "Pas chaque\njour", angle: 0 },
            { label: "8h30-11h\nNY time", angle: 90 },
            { label: "Replay\nTradingView", angle: 180 },
            { label: "Micro\npour débuter", angle: 270 },
          ],
        },
        points: [
          "Ne pas essayer de trader CHAQUE session — créer de mauvaises attentes",
          "Focus sur la fenêtre 8h30 → 11h00 New York time (session principale)",
          "1 bon setup par semaine = début de consistance",
          "Après une perte : ne pas vouloir 'corriger' immédiatement",
          "Micro account pour les premières vraies opérations",
          "L'expérience donne le timing — ça ne se transfère pas, ça se vit",
        ],
      },
    ],
  },
];

function MindMap({ map, color }) {
  const cx = 160, cy = 125, dist = 108;
  return (
    <svg width={320} height={250} style={{ maxWidth: "100%", overflow: "visible" }}>
      {map.nodes.map((n, i) => {
        const rad = (n.angle * Math.PI) / 180;
        const nx = cx + Math.cos(rad) * dist;
        const ny = cy + Math.sin(rad) * dist;
        const lines = n.label.split("\n");
        return (
          <g key={i}>
            <line x1={cx} y1={cy} x2={nx} y2={ny} stroke={color + "55"} strokeWidth={1.5} />
            <ellipse cx={nx} cy={ny} rx={36} ry={20} fill={color + "18"} stroke={color + "70"} strokeWidth={1} />
            {lines.map((l, li) => (
              <text key={li} x={nx} y={ny + (li - (lines.length - 1) / 2) * 11}
                textAnchor="middle" dominantBaseline="middle"
                fontSize={8.5} fill={color} fontFamily="Courier New" fontWeight="700">{l}</text>
            ))}
          </g>
        );
      })}
      <ellipse cx={cx} cy={cy} rx={50} ry={30} fill={color + "28"} stroke={color} strokeWidth={2} />
      {map.center.split("\n").map((l, i) => (
        <text key={i} x={cx} y={cy + (i - (map.center.split("\n").length - 1) / 2) * 13}
          textAnchor="middle" dominantBaseline="middle"
          fontSize={10} fill={color} fontFamily="Courier New" fontWeight="700">{l}</text>
      ))}
    </svg>
  );
}

function TGBanner() {
  return (
    <a href={TELEGRAM} target="_blank" rel="noreferrer" style={{
      display: "flex", alignItems: "center", gap: 12,
      background: "linear-gradient(135deg,#0088cc18,#0088cc30)",
      border: "1px solid #0088cc66", borderRadius: 10,
      padding: "11px 16px", textDecoration: "none", width: "100%", boxSizing: "border-box",
    }}>
      <span style={{ fontSize: 24 }}>✈️</span>
      <div style={{ flex: 1 }}>
        <div style={{ color: "#4fc3f7", fontWeight: 700, fontSize: 13, fontFamily: "Courier New" }}>
          Rejoindre DailyWakeUp — Telegram
        </div>
        <div style={{ color: C.muted, fontSize: 11, fontFamily: "Courier New" }}>
          Signaux XAUUSD · VIP · Mentoring · BTC
        </div>
      </div>
      <div style={{
        background: "#0088cc", color: "#fff", borderRadius: 6,
        padding: "5px 12px", fontSize: 12, fontWeight: 700, whiteSpace: "nowrap",
      }}>Rejoindre →</div>
    </a>
  );
}

export default function App() {
  const [modIdx, setModIdx] = useState(0);
  const [lesIdx, setLesIdx] = useState(0);

  const totalLessons = modules.reduce((a, m) => a + m.lessons.length, 0);
  let lessonNum = 0;
  for (let mi = 0; mi < modIdx; mi++) lessonNum += modules[mi].lessons.length;
  lessonNum += lesIdx + 1;

  const mod = modules[modIdx];
  const lesson = mod.lessons[lesIdx];

  function next() {
    if (lesIdx < mod.lessons.length - 1) setLesIdx(lesIdx + 1);
    else if (modIdx < modules.length - 1) { setModIdx(modIdx + 1); setLesIdx(0); }
  }
  function prev() {
    if (lesIdx > 0) setLesIdx(lesIdx - 1);
    else if (modIdx > 0) { const pm = modules[modIdx - 1]; setModIdx(modIdx - 1); setLesIdx(pm.lessons.length - 1); }
  }

  return (
    <div style={{ background: C.bg, minHeight: "100vh", fontFamily: "'Courier New', monospace", color: C.text }}>
      {/* HEADER */}
      <div style={{
        background: C.panel, borderBottom: `1px solid ${C.border}`,
        display: "flex", alignItems: "center", justifyContent: "space-between",
        padding: "12px 18px", flexWrap: "wrap", gap: 10,
      }}>
        <div>
          <div style={{ fontSize: 9, letterSpacing: 4, color: C.gold }}>ICT MENTORSHIP · LESSON 1</div>
          <div style={{ fontSize: 17, fontWeight: 700, color: "#fff", marginTop: 2 }}>DailyWakeUp Trading 📈</div>
        </div>
        <div style={{ display: "flex", gap: 8, flexWrap: "wrap" }}>
          <a href={`${YOUTUBE_BASE}?si=8wyTvjtdOClZURPR`} target="_blank" rel="noreferrer"
            style={{ background: "#cc000033", border: "1px solid #cc000066", color: "#ff7070", borderRadius: 7, padding: "6px 12px", textDecoration: "none", fontSize: 11, fontWeight: 700 }}>
            ▶ YouTube
          </a>
          <a href={TELEGRAM} target="_blank" rel="noreferrer"
            style={{ background: "#0088cc", color: "#fff", borderRadius: 7, padding: "6px 14px", textDecoration: "none", fontSize: 11, fontWeight: 700 }}>
            ✈️ Telegram
          </a>
        </div>
      </div>

      <div style={{ maxWidth: 920, margin: "0 auto", padding: "14px 12px" }}>
        {/* TOP Telegram */}
        <TGBanner />

        {/* YouTube card */}
        <a href={`${YOUTUBE_BASE}?si=8wyTvjtdOClZURPR`} target="_blank" rel="noreferrer"
          style={{ display: "flex", alignItems: "center", gap: 10, marginTop: 10, background: "#cc000018", border: "1px solid #cc000044", borderRadius: 10, padding: "10px 14px", textDecoration: "none" }}>
          <span style={{ fontSize: 22 }}>▶️</span>
          <div>
            <div style={{ color: "#ff5555", fontWeight: 700, fontSize: 12 }}>ICT Free Mentorship — Lesson 1 (48 min)</div>
            <div style={{ color: C.muted, fontSize: 10 }}>Elements of a Trade Setup · NQ Futures · Cliquer pour regarder</div>
          </div>
        </a>

        {/* Module tabs */}
        <div style={{ display: "flex", gap: 6, marginTop: 14, overflowX: "auto", paddingBottom: 4 }}>
          {modules.map((m, i) => (
            <button key={m.id} onClick={() => { setModIdx(i); setLesIdx(0); }}
              style={{
                background: modIdx === i ? m.color : C.panel,
                border: `1px solid ${modIdx === i ? m.color : C.border}`,
                color: modIdx === i ? "#000" : C.muted,
                borderRadius: 8, padding: "6px 14px", fontSize: 11, fontWeight: 700,
                cursor: "pointer", fontFamily: "inherit", whiteSpace: "nowrap", flexShrink: 0,
              }}>
              {m.icon} {m.title}
            </button>
          ))}
        </div>

        {/* Module bar */}
        <div style={{
          background: C.panel, border: `1px solid ${mod.color}44`,
          borderLeft: `4px solid ${mod.color}`, borderRadius: 10,
          padding: "12px 16px", marginTop: 10,
          display: "flex", alignItems: "center", justifyContent: "space-between", flexWrap: "wrap", gap: 8,
        }}>
          <div>
            <div style={{ fontSize: 15, fontWeight: 700, color: mod.color }}>{mod.icon} Module {mod.id} — {mod.title}</div>
            <div style={{ fontSize: 11, color: C.muted, marginTop: 2 }}>{mod.subtitle}</div>
          </div>
          <a href={`${YOUTUBE_BASE}?t=${mod.seconds}`} target="_blank" rel="noreferrer"
            style={{ background: "#cc000022", border: "1px solid #cc000055", color: "#ff7070", borderRadius: 7, padding: "5px 11px", textDecoration: "none", fontSize: 11, fontWeight: 700 }}>
            ▶ {mod.timestamp}
          </a>
        </div>

        {/* Lesson tabs */}
        <div style={{ display: "flex", gap: 6, marginTop: 10, flexWrap: "wrap" }}>
          {mod.lessons.map((l, i) => (
            <button key={i} onClick={() => setLesIdx(i)}
              style={{
                background: lesIdx === i ? mod.color + "22" : C.card,
                border: `1px solid ${lesIdx === i ? mod.color : C.border}`,
                color: lesIdx === i ? mod.color : C.muted,
                borderRadius: 7, padding: "5px 12px", fontSize: 11, cursor: "pointer", fontFamily: "inherit",
              }}>
              {l.title.length > 35 ? l.title.slice(0, 35) + "…" : l.title}
            </button>
          ))}
        </div>

        {/* LESSON CARD */}
        <div style={{ background: C.card, border: `1px solid ${C.border}`, borderRadius: 12, marginTop: 10, overflow: "hidden" }}>
          {/* Lesson header */}
          <div style={{
            background: mod.color + "15", borderBottom: `1px solid ${mod.color}30`,
            padding: "14px 18px", display: "flex", justifyContent: "space-between", alignItems: "flex-start", flexWrap: "wrap", gap: 8,
          }}>
            <div>
              <div style={{ fontSize: 15, fontWeight: 700, color: "#fff" }}>{lesson.title}</div>
              <div style={{ fontSize: 10, color: C.muted, marginTop: 3 }}>
                Leçon {lessonNum} / {totalLessons} · Module {mod.id}
              </div>
            </div>
            <a href={`${YOUTUBE_BASE}?t=${lesson.seconds}`} target="_blank" rel="noreferrer"
              style={{
                background: "#cc000033", border: "1px solid #cc000066",
                color: "#ff8888", borderRadius: 8, padding: "7px 14px",
                textDecoration: "none", fontSize: 13, fontWeight: 700,
                display: "flex", alignItems: "center", gap: 6,
              }}>
              ▶ {lesson.timestamp}
              <span style={{ fontSize: 9, color: C.muted }}>sur YouTube</span>
            </a>
          </div>

          {/* Body */}
          <div style={{ display: "flex", flexWrap: "wrap" }}>
            {/* Points */}
            <div style={{ flex: "1 1 300px", padding: "18px" }}>
              <div style={{ fontSize: 9, letterSpacing: 3, color: C.muted, marginBottom: 12 }}>POINTS CLÉS</div>
              {lesson.points.map((p, i) => (
                <div key={i} style={{ display: "flex", gap: 10, marginBottom: 12, alignItems: "flex-start" }}>
                  <div style={{
                    width: 22, height: 22, borderRadius: "50%", flexShrink: 0, marginTop: 1,
                    background: mod.color + "25", border: `1.5px solid ${mod.color}`,
                    color: mod.color, fontSize: 10, fontWeight: 700,
                    display: "flex", alignItems: "center", justifyContent: "center",
                  }}>{i + 1}</div>
                  <span style={{ fontSize: 13, lineHeight: 1.6, color: C.text }}>{p}</span>
                </div>
              ))}
            </div>

            {/* Mind map */}
            <div style={{
              flex: "1 1 280px", padding: "18px",
              borderLeft: `1px solid ${C.border}`,
              display: "flex", flexDirection: "column", alignItems: "center",
            }}>
              <div style={{ fontSize: 9, letterSpacing: 3, color: C.muted, marginBottom: 8 }}>MIND MAP</div>
              <MindMap map={lesson.mindmap} color={mod.color} />
            </div>
          </div>

          {/* TELEGRAM bottom of lesson */}
          <div style={{ padding: "12px 16px", borderTop: `1px solid ${C.border}` }}>
            <TGBanner />
          </div>
        </div>

        {/* Navigation */}
        <div style={{ display: "flex", alignItems: "center", justifyContent: "space-between", marginTop: 12, gap: 10 }}>
          <button onClick={prev} disabled={modIdx === 0 && lesIdx === 0}
            style={{
              background: C.panel, border: `1px solid ${C.border}`, color: C.muted,
              borderRadius: 8, padding: "9px 18px", cursor: "pointer", fontFamily: "inherit", fontSize: 12,
              opacity: modIdx === 0 && lesIdx === 0 ? 0.3 : 1,
            }}>← Précédent</button>

          <div style={{ color: C.muted, fontSize: 11, textAlign: "center" }}>
            <div>{lessonNum} / {totalLessons} leçons</div>
            <div style={{ marginTop: 4, background: C.border, borderRadius: 4, height: 4, width: 120 }}>
              <div style={{ background: mod.color, height: 4, borderRadius: 4, width: `${(lessonNum / totalLessons) * 100}%`, transition: "width 0.3s" }} />
            </div>
          </div>

          <button onClick={next} disabled={modIdx === modules.length - 1 && lesIdx === mod.lessons.length - 1}
            style={{
              background: mod.color, border: "none", color: "#000",
              borderRadius: 8, padding: "9px 18px", cursor: "pointer", fontFamily: "inherit", fontSize: 12, fontWeight: 700,
              opacity: modIdx === modules.length - 1 && lesIdx === mod.lessons.length - 1 ? 0.3 : 1,
            }}>Suivant →</button>
        </div>

        {/* BOTTOM Telegram */}
        <div style={{ marginTop: 22 }}>
          <TGBanner />
        </div>

        <div style={{ textAlign: "center", marginTop: 16, color: C.muted, fontSize: 10 }}>
          DailyWakeUp Trading · ICT Lesson 1 · Madagascar 🇲🇬 · t.me/DailyWakeUp
        </div>
      </div>
    </div>
  );
}
