<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Groundfloor Analytics — Complete Setup Guide & Reference</title>
    <style>
        :root {
            --gf-dark: #1B2A4A;
            --gf-green: #00C389;
            --gf-light: #f0f4f8;
            --gf-border: #d0d7de;
            --text: #1f2937;
            --text-sec: #6b7280;
            --blue: #2563eb;
            --red: #dc2626;
            --amber: #d97706;
            --green: #16a34a;
            --purple: #7c3aed;
            --radius: 8px;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
            background: #fff;
            color: var(--text);
            line-height: 1.65;
            font-size: 15px;
        }

        /* ─── NAV ─── */
        .top-bar {
            background: var(--gf-dark);
            color: #fff;
            padding: 14px 32px;
            display: flex;
            align-items: center;
            gap: 14px;
            position: sticky;
            top: 0;
            z-index: 100;
            box-shadow: 0 2px 8px rgba(0,0,0,.18);
        }
        .top-bar .logo {
            width: 32px; height: 32px;
            background: var(--gf-green);
            border-radius: 6px;
            display: flex; align-items: center; justify-content: center;
            font-weight: 800; font-size: 16px;
        }
        .top-bar h1 { font-size: 16px; font-weight: 600; }
        .top-bar .tag {
            font-size: 11px; background: rgba(255,255,255,.15);
            padding: 2px 8px; border-radius: 4px; margin-left: auto;
        }

        .wrapper { max-width: 1100px; margin: 0 auto; padding: 0 28px; }

        /* ─── HERO ─── */
        .hero {
            background: linear-gradient(135deg, var(--gf-dark) 0%, #2d4a7a 100%);
            color: #fff;
            padding: 48px 0 40px;
        }
        .hero h2 { font-size: 28px; font-weight: 700; margin-bottom: 8px; }
        .hero p { font-size: 15px; opacity: .8; max-width: 700px; }
        .hero .meta { margin-top: 20px; display: flex; flex-wrap: wrap; gap: 24px; font-size: 13px; }
        .hero .meta span { display: flex; align-items: center; gap: 6px; }
        .hero .meta .dot { width: 8px; height: 8px; border-radius: 50%; }

        /* ─── SECTION ─── */
        section { padding: 36px 0; border-bottom: 1px solid var(--gf-border); }
        section:last-child { border-bottom: none; }
        .section-num {
            font-size: 11px; font-weight: 700; color: var(--gf-green);
            text-transform: uppercase; letter-spacing: 1.2px; margin-bottom: 4px;
        }
        section h3 { font-size: 22px; font-weight: 700; margin-bottom: 16px; }
        section h4 { font-size: 16px; font-weight: 600; margin: 24px 0 10px; color: var(--gf-dark); }
        section p { margin-bottom: 12px; }

        /* ─── TABLES ─── */
        table {
            width: 100%; border-collapse: collapse; font-size: 13px;
            margin: 12px 0 20px; background: #fff;
            border: 1px solid var(--gf-border); border-radius: var(--radius);
            overflow: hidden;
        }
        thead th {
            text-align: left; padding: 10px 14px; background: var(--gf-light);
            font-weight: 600; font-size: 11px; text-transform: uppercase;
            letter-spacing: .5px; color: var(--text-sec); border-bottom: 2px solid var(--gf-border);
        }
        tbody td {
            padding: 9px 14px; border-bottom: 1px solid #f0f0f0;
            vertical-align: top;
        }
        tbody tr:last-child td { border-bottom: none; }
        tbody tr:hover { background: #f9fafb; }

        /* ─── LINK CARDS ─── */
        .link-grid {
            display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 14px; margin: 16px 0;
        }
        .link-card {
            border: 1px solid var(--gf-border); border-radius: var(--radius);
            padding: 16px 18px; background: #fff;
            transition: box-shadow .15s, border-color .15s;
            text-decoration: none; color: var(--text);
            display: block;
        }
        .link-card:hover {
            box-shadow: 0 2px 8px rgba(0,0,0,.08);
            border-color: var(--blue);
        }
        .link-card .lc-label {
            font-size: 11px; font-weight: 600; text-transform: uppercase;
            letter-spacing: .5px; margin-bottom: 4px;
        }
        .link-card .lc-label.ga4 { color: #e37400; }
        .link-card .lc-label.gtm { color: var(--blue); }
        .link-card .lc-label.ads { color: var(--green); }
        .link-card .lc-label.firebase { color: var(--amber); }
        .link-card .lc-label.report { color: var(--purple); }
        .link-card .lc-title { font-size: 15px; font-weight: 600; margin-bottom: 2px; }
        .link-card .lc-desc { font-size: 12px; color: var(--text-sec); }
        .link-card .lc-url {
            font-size: 11px; color: var(--blue); margin-top: 6px;
            word-break: break-all; opacity: .7;
        }

        /* ─── STATUS BADGES ─── */
        .badge {
            display: inline-block; font-size: 11px; font-weight: 600;
            padding: 2px 8px; border-radius: 4px; vertical-align: middle;
        }
        .badge.done { background: #dcfce7; color: #166534; }
        .badge.pending { background: #fef9c3; color: #854d0e; }
        .badge.blocked { background: #fee2e2; color: #991b1b; }
        .badge.info { background: #dbeafe; color: #1e40af; }

        /* ─── TIMELINE ─── */
        .timeline { margin: 16px 0; }
        .tl-item {
            display: flex; gap: 16px; padding: 14px 0;
            border-bottom: 1px solid #f0f0f0;
        }
        .tl-item:last-child { border-bottom: none; }
        .tl-date {
            min-width: 100px; font-size: 12px; font-weight: 600;
            color: var(--text-sec); padding-top: 2px;
        }
        .tl-dot {
            width: 10px; height: 10px; border-radius: 50%;
            background: var(--gf-green); margin-top: 6px; flex-shrink: 0;
        }
        .tl-content { flex: 1; }
        .tl-content strong { font-weight: 600; }
        .tl-content .tl-detail { font-size: 13px; color: var(--text-sec); margin-top: 2px; }

        /* ─── CODE ─── */
        code {
            background: var(--gf-light); padding: 2px 6px; border-radius: 3px;
            font-size: 13px; font-family: 'SF Mono', 'Fira Code', monospace;
        }

        /* ─── CALLOUT ─── */
        .callout {
            border-left: 4px solid var(--gf-green); background: #f0fdf4;
            padding: 14px 18px; border-radius: 0 var(--radius) var(--radius) 0;
            margin: 16px 0; font-size: 14px;
        }
        .callout.warn { border-color: var(--amber); background: #fffbeb; }
        .callout.info { border-color: var(--blue); background: #eff6ff; }
        .callout strong { font-weight: 600; }

        /* ─── TOC ─── */
        .toc {
            background: var(--gf-light); border-radius: var(--radius);
            padding: 20px 24px; margin: 24px 0;
        }
        .toc h4 { margin: 0 0 12px; font-size: 14px; }
        .toc ol { padding-left: 20px; }
        .toc li { margin: 4px 0; font-size: 14px; }
        .toc a { color: var(--blue); text-decoration: none; }
        .toc a:hover { text-decoration: underline; }

        /* ─── PRINT ─── */
        @media print {
            .top-bar { position: static; }
            .link-card { break-inside: avoid; border: 1px solid #ccc; }
            section { break-inside: avoid; }
            a { color: var(--text) !important; }
        }

        @media (max-width: 700px) {
            .wrapper { padding: 0 16px; }
            .link-grid { grid-template-columns: 1fr; }
            .hero h2 { font-size: 22px; }
        }
    </style>
</head>
<body>

<div class="top-bar">
    <div class="logo">G</div>
    <h1>Groundfloor Analytics — Setup Guide</h1>
    <span class="tag">Updated Feb 12, 2026</span>
</div>

<div class="hero">
    <div class="wrapper">
        <h2>Groundfloor Unified GA4 Analytics — Complete Setup Reference</h2>
        <p>A single source of truth for the analytics infrastructure across groundfloor.com, groundfloor.us, iOS app, and Android app. Includes direct links to every property, report, tag container, and integration.</p>
        <div class="meta">
            <span><span class="dot" style="background:#00C389"></span> GA4 Property: 523095876</span>
            <span><span class="dot" style="background:#2563eb"></span> Measurement ID: G-W822YJN0Q4</span>
            <span><span class="dot" style="background:#e37400"></span> Google Ads: 612-495-1271</span>
            <span><span class="dot" style="background:#d97706"></span> Firebase: gf-investor-mobile-app</span>
        </div>
    </div>
</div>

<div class="wrapper">

<!-- TABLE OF CONTENTS -->
<div class="toc">
    <h4>Table of Contents</h4>
    <ol>
        <li><a href="#quicklinks">Quick Links — All Properties, Reports & Tools</a></li>
        <li><a href="#architecture">Architecture Overview</a></li>
        <li><a href="#data-streams">Data Streams & Platforms</a></li>
        <li><a href="#gtm">Google Tag Manager Setup</a></li>
        <li><a href="#firebase">Firebase & Mobile App Integration</a></li>
        <li><a href="#integrations">Product Integrations (Google Ads, Search Console)</a></li>
        <li><a href="#events">Key Events & Conversion Tracking</a></li>
        <li><a href="#funnel">Onboarding Funnel Exploration</a></li>
        <li><a href="#ga4-reports">Direct GA4 Report Links</a></li>
        <li><a href="#changelog">Changelog — All Actions Taken</a></li>
        <li><a href="#legacy">Legacy Properties Reference</a></li>
        <li><a href="#pending">Pending Items & Next Steps</a></li>
    </ol>
</div>


<!-- ============================================================ -->
<!-- 1. QUICK LINKS -->
<!-- ============================================================ -->
<section id="quicklinks">
    <div class="section-num">Section 1</div>
    <h3>Quick Links — All Properties, Reports &amp; Tools</h3>
    <p>Direct links to every Google account, property, and tool involved in the Groundfloor analytics setup. Bookmark this section for day-to-day access.</p>

    <h4>GA4 Analytics</h4>
    <div class="link-grid">
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/home" target="_blank" rel="noopener">
            <div class="lc-label ga4">GA4 — Unified Property</div>
            <div class="lc-title">Groundfloor Unified – All Platforms</div>
            <div class="lc-desc">Property 523095876 &middot; G-W822YJN0Q4 &middot; All web + mobile data</div>
            <div class="lc-url">analytics.google.com &rarr; Property 523095876</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-acquisition-v2&ruid=lifecycle-acquisition-v2&collectionId=life-cycle" target="_blank" rel="noopener">
            <div class="lc-label ga4">GA4 — Acquisition Report</div>
            <div class="lc-title">Traffic Acquisition Report</div>
            <div class="lc-desc">See session-level traffic sources: Direct, Organic, Paid, Referral, etc.</div>
            <div class="lc-url">Reports &rarr; Life cycle &rarr; Acquisition &rarr; Traffic acquisition</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/explorer?params=_u..nav%3Dmaui%26_r.explorerCard..selmet%3D%5B%22eventCount%22%5D%26_r.explorerCard..seldim%3D%5B%22eventName%22%5D&r=top-events&ruid=top-events&collectionId=life-cycle" target="_blank" rel="noopener">
            <div class="lc-label ga4">GA4 — Events Report</div>
            <div class="lc-title">Events (All Events)</div>
            <div class="lc-desc">Full list of events flowing into the unified property</div>
            <div class="lc-url">Reports &rarr; Life cycle &rarr; Engagement &rarr; Events</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/conversions" target="_blank" rel="noopener">
            <div class="lc-label ga4">GA4 — Key Events</div>
            <div class="lc-title">Key Events (Conversions)</div>
            <div class="lc-desc">21 key events tracked including investmentFinished, registered, payment_method_added</div>
            <div class="lc-url">Reports &rarr; Life cycle &rarr; Engagement &rarr; Key events</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/realtime/overview" target="_blank" rel="noopener">
            <div class="lc-label ga4">GA4 — Realtime</div>
            <div class="lc-title">Realtime Overview</div>
            <div class="lc-desc">Live users across web + iOS + Android right now</div>
            <div class="lc-url">Reports &rarr; Realtime</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/analysis/a40960181p523095876/edit/qU5-bf-qQiO4vd-8h80NzQ" target="_blank" rel="noopener">
            <div class="lc-label report">Exploration — Funnel</div>
            <div class="lc-title">Onboarding Funnel by Traffic Source</div>
            <div class="lc-desc">5-step funnel: Registration → Registered → Bank Acct → Payment → Investment, by channel</div>
            <div class="lc-url">Explore &rarr; Funnel exploration</div>
        </a>
    </div>

    <h4>GA4 Admin</h4>
    <div class="link-grid">
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/streams/table" target="_blank" rel="noopener">
            <div class="lc-label ga4">Admin — Data Streams</div>
            <div class="lc-title">Data Streams (5 total)</div>
            <div class="lc-desc">Web (.com, .us), iOS app, Android app, Testing API</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/events" target="_blank" rel="noopener">
            <div class="lc-label ga4">Admin — Events</div>
            <div class="lc-title">Events &amp; Key Events Config</div>
            <div class="lc-desc">Mark/unmark key events, view event parameters</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/firebase" target="_blank" rel="noopener">
            <div class="lc-label ga4">Admin — Firebase Links</div>
            <div class="lc-title">Firebase Integration</div>
            <div class="lc-desc">Firebase project gf-investor-mobile-app linked Feb 12, 2026</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/googleads" target="_blank" rel="noopener">
            <div class="lc-label ga4">Admin — Google Ads Links</div>
            <div class="lc-title">Google Ads Integration</div>
            <div class="lc-desc">Account 612-495-1271 linked Feb 4, 2026</div>
        </a>
    </div>

    <h4>Google Tag Manager</h4>
    <div class="link-grid">
        <a class="link-card" href="https://tagmanager.google.com/#/container/accounts/6299000195/containers/222186267/workspaces?apiLink=container" target="_blank" rel="noopener">
            <div class="lc-label gtm">GTM — groundfloor.com</div>
            <div class="lc-title">GTM-53NRNKD6 (Version 37)</div>
            <div class="lc-desc">36 tags: 5 Google Tags, 26 GA4 Events, 1 Conversion Linker, 6 HTML/Schema</div>
        </a>
        <a class="link-card" href="https://tagmanager.google.com/#/versions/accounts/6299000195/containers/222186267/versions/37" target="_blank" rel="noopener">
            <div class="lc-label gtm">GTM — Version 37 (Latest)</div>
            <div class="lc-title">Version 37: Unified GA4 Event Tags Update</div>
            <div class="lc-desc">Published Feb 12, 2026 — All 26 GA4 event tags updated to G-W822YJN0Q4</div>
        </a>
        <a class="link-card" href="https://tagmanager.google.com/#/container/accounts/6054498498/containers/95498538/workspaces?apiLink=container" target="_blank" rel="noopener">
            <div class="lc-label gtm">GTM — groundfloor.us</div>
            <div class="lc-title">GTM-K8SQFHW (Version 226)</div>
            <div class="lc-desc">Unified forward-events tag sends all custom events to G-W822YJN0Q4</div>
        </a>
    </div>

    <h4>Google Ads &amp; Firebase</h4>
    <div class="link-grid">
        <a class="link-card" href="https://ads.google.com/aw/overview?ocid=107041362&ascid=107041362" target="_blank" rel="noopener">
            <div class="lc-label ads">Google Ads</div>
            <div class="lc-title">GROUNDFLOOR (612-495-1271)</div>
            <div class="lc-desc">Linked to unified property. 7 conversions staged for import (needs admin save).</div>
        </a>
        <a class="link-card" href="https://ads.google.com/aw/conversions?ocid=107041362&ascid=107041362" target="_blank" rel="noopener">
            <div class="lc-label ads">Google Ads — Conversions</div>
            <div class="lc-title">Conversion Actions</div>
            <div class="lc-desc">Import GA4 key events as conversion goals for campaign optimization</div>
        </a>
        <a class="link-card" href="https://console.firebase.google.com/project/gf-investor-mobile-app/overview" target="_blank" rel="noopener">
            <div class="lc-label firebase">Firebase Console</div>
            <div class="lc-title">gf-investor-mobile-app</div>
            <div class="lc-desc">Project #966198890720 &middot; iOS + Android apps &middot; Linked to unified GA4 property</div>
        </a>
        <a class="link-card" href="https://console.firebase.google.com/project/gf-investor-mobile-app/analytics" target="_blank" rel="noopener">
            <div class="lc-label firebase">Firebase Analytics</div>
            <div class="lc-title">Firebase Analytics Dashboard</div>
            <div class="lc-desc">Mobile app analytics routed to unified GA4 property</div>
        </a>
    </div>
</section>


<!-- ============================================================ -->
<!-- 2. ARCHITECTURE -->
<!-- ============================================================ -->
<section id="architecture">
    <div class="section-num">Section 2</div>
    <h3>Architecture Overview</h3>
    <p>The unified GA4 property consolidates data from four platforms into a single analytics view. All traffic sources, conversions, and user journeys are tracked in one place for the first time.</p>

    <div class="callout">
        <strong>Why unified?</strong> Previously, Groundfloor had separate GA4 properties for the marketing site (.com), web application (.us), and mobile apps. This made it impossible to see a user's full journey from ad click → registration → first investment across platforms. The unified property solves this.
    </div>

    <table>
        <thead><tr><th>Platform</th><th>Domain / App</th><th>Data Collection Method</th><th>Routing to GA4</th></tr></thead>
        <tbody>
            <tr><td><strong>Marketing Site</strong></td><td>groundfloor.com</td><td>GTM container GTM-53NRNKD6 (Version 37)</td><td>Google Tag G-W822YJN0Q4 + 26 GA4 Event tags</td></tr>
            <tr><td><strong>Web Application</strong></td><td>groundfloor.us</td><td>GTM container GTM-K8SQFHW (Version 226)</td><td>Forward Events tag → G-W822YJN0Q4 + cross-domain linking</td></tr>
            <tr><td><strong>iOS App</strong></td><td>us.groundfloor.merlin</td><td>Firebase SDK (GoogleService-Info.plist)</td><td>Firebase → GA4 link (server-side routing)</td></tr>
            <tr><td><strong>Android App</strong></td><td>us.groundfloor.merlin</td><td>Firebase SDK (google-services.json)</td><td>Firebase → GA4 link (server-side routing)</td></tr>
        </tbody>
    </table>

    <h4>Cross-Domain Tracking</h4>
    <p>Cross-domain linking is configured between <code>groundfloor.com</code> (contains match) and <code>groundfloor.us</code> (exact match). This preserves user sessions when visitors navigate from the marketing site to the web application, ensuring proper traffic source attribution.</p>

    <h4>Referral Exclusions</h4>
    <p>Both <code>groundfloor.com</code> and <code>groundfloor.us</code> are set as referral exclusions to prevent self-referral attribution noise between the two domains.</p>
</section>


<!-- ============================================================ -->
<!-- 3. DATA STREAMS -->
<!-- ============================================================ -->
<section id="data-streams">
    <div class="section-num">Section 3</div>
    <h3>Data Streams &amp; Platforms</h3>
    <p>The unified property has 5 data streams. Three are actively receiving traffic; the .us stream routes through the .com stream via cross-domain tracking; and the Testing API stream was auto-created by Firebase.</p>

    <table>
        <thead><tr><th>Stream Name</th><th>Type</th><th>Stream ID</th><th>Identifier</th><th>Status</th></tr></thead>
        <tbody>
            <tr>
                <td><strong>Groundfloor.com – Main Website</strong></td>
                <td>Web</td>
                <td>13411990980</td>
                <td>G-W822YJN0Q4</td>
                <td><span class="badge done">Receiving Traffic</span></td>
            </tr>
            <tr>
                <td><strong>Groundfloor.us – Web Application</strong></td>
                <td>Web</td>
                <td>13412016041</td>
                <td>G-W822YJN0Q4</td>
                <td><span class="badge info">Routes via .com stream</span></td>
            </tr>
            <tr>
                <td><strong>Groundfloor Investor App</strong></td>
                <td>iOS</td>
                <td>13603838468</td>
                <td>us.groundfloor.merlin</td>
                <td><span class="badge done">Receiving Traffic</span></td>
            </tr>
            <tr>
                <td><strong>Groundfloor Investor App</strong></td>
                <td>Android</td>
                <td>13603583831</td>
                <td>us.groundfloor.merlin</td>
                <td><span class="badge done">Receiving Traffic</span></td>
            </tr>
            <tr>
                <td><strong>Testing API</strong></td>
                <td>Web</td>
                <td>13603766723</td>
                <td>—</td>
                <td><span class="badge info">Auto-created (Firebase)</span></td>
            </tr>
        </tbody>
    </table>

    <h4>Platform Breakdown (28-Day, Verified Feb 12)</h4>
    <table>
        <thead><tr><th>Platform</th><th>Active Users (Realtime)</th><th>OS Distribution (28d)</th><th>Device Split</th></tr></thead>
        <tbody>
            <tr><td>Web</td><td>73</td><td>Windows 7K, Mac 2K, Linux 295, Chrome OS 116</td><td>Desktop 55.1%</td></tr>
            <tr><td>iOS</td><td>31</td><td>iOS 5.2K</td><td rowspan="2">Mobile 43.7%, Tablet 1.3%</td></tr>
            <tr><td>Android</td><td>19</td><td>Android 2.6K</td></tr>
        </tbody>
    </table>
</section>


<!-- ============================================================ -->
<!-- 4. GTM SETUP -->
<!-- ============================================================ -->
<section id="gtm">
    <div class="section-num">Section 4</div>
    <h3>Google Tag Manager Setup</h3>

    <h4>GTM-53NRNKD6 — groundfloor.com (Marketing Site)</h4>
    <p>This container manages all tracking on the Groundfloor marketing website. It was fully audited and updated on Feb 12, 2026.</p>

    <table>
        <thead><tr><th>Tag Type</th><th>Count</th><th>Details</th><th>Measurement ID</th></tr></thead>
        <tbody>
            <tr><td><strong>Google Tags</strong></td><td>5</td><td>Unified, Legacy .com, Legacy .us, Lending, Google Ads</td><td>G-W822YJN0Q4 (unified), G-73JBQSSWXH, G-DPQ1WQ71R9, G-8XBKNS31ZB, AW-968207878</td></tr>
            <tr><td><strong>GA4 Event Tags</strong></td><td>26</td><td>All CTA click events, form submissions, content engagement</td><td>G-W822YJN0Q4 <span class="badge done">Updated Feb 12</span></td></tr>
            <tr><td><strong>Conversion Linker</strong></td><td>1</td><td>Google Ads conversion tracking</td><td>—</td></tr>
            <tr><td><strong>Custom HTML / Schema</strong></td><td>6</td><td>5 FAQ Schema + 1 Software Application Schema</td><td>—</td></tr>
        </tbody>
    </table>

    <div class="callout">
        <strong>Action Taken (Feb 12):</strong> All 26 GA4 Event tags were updated from the legacy measurement ID (<code>G-73JBQSSWXH</code>) to the unified ID (<code>G-W822YJN0Q4</code>). The 5 Google Tags were intentionally left unchanged for dual-tagging during the 30–90 day transition period. Published as <strong>Version 37</strong>.
    </div>

    <p><strong>Notable GA4 Event Tags (examples of the 26):</strong></p>
    <table>
        <thead><tr><th>Tag Name</th><th>Event</th><th>Trigger</th></tr></thead>
        <tbody>
            <tr><td>GA4 - Get Started Button Clicks</td><td>get_started_click</td><td>CTA button clicks</td></tr>
            <tr><td>GA4 - Create Account Button</td><td>create_account_click</td><td>Create account CTA</td></tr>
            <tr><td>GA4 - Contact Form Submission</td><td>contact_form_submission</td><td>Form submit</td></tr>
            <tr><td>GA4 - View Properties</td><td>view_properties_click</td><td>Property listing clicks</td></tr>
            <tr><td>GA4 - Scroll Depth</td><td>scroll_depth</td><td>Scroll milestones</td></tr>
            <tr><td colspan="3" style="color:var(--text-sec);font-style:italic;">+ 21 more event tags covering content engagement, navigation, and conversion CTAs</td></tr>
        </tbody>
    </table>

    <h4>GTM-K8SQFHW — groundfloor.us (Web Application)</h4>
    <p>The .us container uses a dynamic "Forward Events" pattern that catches all custom dataLayer events and sends them to GA4 with their parameters.</p>

    <div class="callout">
        <strong>Action Taken (Feb 12):</strong> The existing "Forward events" tag was routing to the old property (<code>G-DPQ1WQ71R9</code>). A new tag — <strong>"GA4 Unified – Forward Events – G-W822YJN0Q4"</strong> — was created as a duplicate with the correct measurement ID and published as <strong>Version 226</strong>. This tag forwards all custom events with parameters: <code>value</code>, <code>accountType</code>, <code>orderId</code>, <code>amountInvested</code>, <code>utmCampaign</code>, <code>utmTerm</code>, and the <code>userId</code> user property.
    </div>
</section>


<!-- ============================================================ -->
<!-- 5. FIREBASE -->
<!-- ============================================================ -->
<section id="firebase">
    <div class="section-num">Section 5</div>
    <h3>Firebase &amp; Mobile App Integration</h3>
    <p>The iOS and Android apps use the Firebase Analytics SDK. On Feb 12, 2026, the Firebase project was linked to the unified GA4 property, routing all mobile analytics data to the single view. <strong>No app code changes were required.</strong></p>

    <table>
        <thead><tr><th>Field</th><th>Value</th></tr></thead>
        <tbody>
            <tr><td>Firebase Project ID</td><td><code>gf-investor-mobile-app</code></td></tr>
            <tr><td>Firebase Project Number</td><td>966198890720</td></tr>
            <tr><td>iOS Firebase App ID</td><td><code>1:966198890720:ios:8f22229b579556e6124085</code></td></tr>
            <tr><td>Android Firebase App ID</td><td><code>1:966198890720:android:4e9dd7ae06907309124085</code></td></tr>
            <tr><td>Bundle / Package Name</td><td><code>us.groundfloor.merlin</code></td></tr>
            <tr><td>Enhanced Audience Integration</td><td><span class="badge done">Enabled</span></td></tr>
            <tr><td>Firebase Link Date (unified)</td><td>February 12, 2026</td></tr>
            <tr><td>App Versions Verified</td><td>iOS v2.0.34, Android v2.0.34</td></tr>
        </tbody>
    </table>

    <div class="callout warn">
        <strong>Orphaned project resolved:</strong> An accidental GCP project (<code>groundfloor-unified--all-plat</code>, #972930606463) had been auto-created and was blocking the real Firebase link. It was identified via the GA4 Admin API (<code>properties.firebaseLinks.list</code>), deleted via <code>properties.firebaseLinks.delete</code>, and the GCP project was shut down. The real project then linked successfully.
    </div>
</section>


<!-- ============================================================ -->
<!-- 6. INTEGRATIONS -->
<!-- ============================================================ -->
<section id="integrations">
    <div class="section-num">Section 6</div>
    <h3>Product Integrations</h3>

    <h4>Google Ads — 612-495-1271 (AW-968207878)</h4>
    <table>
        <thead><tr><th>Setting</th><th>Value</th></tr></thead>
        <tbody>
            <tr><td>Account Name</td><td>GROUNDFLOOR</td></tr>
            <tr><td>Account ID</td><td>612-495-1271 / AW-968207878</td></tr>
            <tr><td>Linked to Unified Property</td><td>Feb 4, 2026 (by greg.cordell@groundfloor.us)</td></tr>
            <tr><td>Personalized Advertising</td><td><span class="badge done">Enabled</span></td></tr>
            <tr><td>Conversion Import</td><td><span class="badge pending">7 events staged — needs admin save</span></td></tr>
        </tbody>
    </table>

    <p><strong>Staged conversion imports (pending admin with edit access):</strong></p>
    <table>
        <thead><tr><th>GA4 Event</th><th>Google Ads Category</th><th>Status</th></tr></thead>
        <tbody>
            <tr><td>investmentFinished</td><td>Purchase</td><td><span class="badge pending">Staged</span></td></tr>
            <tr><td>payment_method_added</td><td>Add to cart</td><td><span class="badge pending">Staged</span></td></tr>
            <tr><td>Bank Account Created</td><td>Signup</td><td><span class="badge pending">Staged</span></td></tr>
            <tr><td>registered</td><td>Signup</td><td><span class="badge pending">Staged</span></td></tr>
            <tr><td>begin_registration</td><td>Signup</td><td><span class="badge pending">Staged</span></td></tr>
            <tr><td>accreditation_verified</td><td>Signup</td><td><span class="badge pending">Staged</span></td></tr>
            <tr><td>onboardingLinkBankAccountComplete</td><td>Signup</td><td><span class="badge pending">Staged</span></td></tr>
        </tbody>
    </table>

    <h4>Google Search Console</h4>
    <table>
        <thead><tr><th>Setting</th><th>Value</th></tr></thead>
        <tbody>
            <tr><td>Property</td><td>https://groundfloor.com/ (URL-prefix)</td></tr>
            <tr><td>Linked Stream</td><td>Groundfloor.com – Main Website (13411990980)</td></tr>
            <tr><td>Note</td><td>Domain-level properties were unavailable (already linked to legacy GA4 properties)</td></tr>
        </tbody>
    </table>
</section>


<!-- ============================================================ -->
<!-- 7. KEY EVENTS -->
<!-- ============================================================ -->
<section id="events">
    <div class="section-num">Section 7</div>
    <h3>Key Events &amp; Conversion Tracking</h3>
    <p>21 key events are configured in the unified property. These track the full investor lifecycle from first visit through investment completion.</p>

    <table>
        <thead><tr><th>Key Event</th><th>Category</th><th>Streams Active</th><th>Notes</th></tr></thead>
        <tbody>
            <tr><td><strong>investmentFinished</strong></td><td>Investment</td><td>Web + iOS + Android</td><td>Primary conversion — investment completed</td></tr>
            <tr><td><strong>payment_method_added</strong></td><td>Onboarding</td><td>Web + iOS + Android</td><td>Payment method linked</td></tr>
            <tr><td><strong>session_start</strong></td><td>Engagement</td><td>Web + iOS + Android</td><td>New session initiated</td></tr>
            <tr><td><strong>begin_registration</strong></td><td>Registration</td><td>2 streams</td><td>User starts signup flow</td></tr>
            <tr><td><strong>complete_registration</strong></td><td>Registration</td><td>2 streams</td><td>User completes signup</td></tr>
            <tr><td><strong>registered</strong></td><td>Registration</td><td>2 streams</td><td>Registration confirmed</td></tr>
            <tr><td><strong>first_open</strong></td><td>App</td><td>2 streams</td><td>First app open</td></tr>
            <tr><td><strong>accreditation_verified</strong></td><td>Onboarding</td><td>Web</td><td>Accredited investor verification</td></tr>
            <tr><td><strong>Bank Account Created</strong></td><td>Onboarding</td><td>Web</td><td>Bank account linked</td></tr>
            <tr><td><strong>onboardingLinkBankAccountComplete</strong></td><td>Onboarding</td><td>Web</td><td>Plaid bank linking completed</td></tr>
            <tr><td><strong>form_submit</strong></td><td>Engagement</td><td>Web</td><td>Contact/signup form submitted</td></tr>
            <tr><td><strong>view_search_results</strong></td><td>Engagement</td><td>Web</td><td>Property search executed</td></tr>
            <tr><td colspan="4" style="color:var(--text-sec);font-style:italic;">+ 9 additional e-commerce events preconfigured (add_to_cart, purchase, view_item, etc.) — awaiting data</td></tr>
        </tbody>
    </table>
</section>


<!-- ============================================================ -->
<!-- 8. FUNNEL -->
<!-- ============================================================ -->
<section id="funnel">
    <div class="section-num">Section 8</div>
    <h3>Onboarding Funnel Exploration</h3>
    <p>The primary reporting deliverable for this project: a 5-step investor onboarding funnel broken down by traffic source. This answers the core question — <em>"Which traffic sources drive the most completed investors?"</em></p>

    <div class="link-grid">
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/analysis/a40960181p523095876/edit/qU5-bf-qQiO4vd-8h80NzQ" target="_blank" rel="noopener">
            <div class="lc-label report">GA4 Exploration</div>
            <div class="lc-title">Onboarding Funnel by Traffic Source</div>
            <div class="lc-desc">Open this exploration directly in GA4 to see the live funnel data</div>
            <div class="lc-url">Explore &rarr; Funnel exploration &rarr; "Onboarding Funnel by Traffic Source"</div>
        </a>
    </div>

    <h4>Funnel Steps</h4>
    <table>
        <thead><tr><th>Step</th><th>Name</th><th>GA4 Event</th><th>What It Tracks</th></tr></thead>
        <tbody>
            <tr><td><strong>1</strong></td><td>Begin Registration</td><td><code>begin_registration</code></td><td>User starts the signup process</td></tr>
            <tr><td><strong>2</strong></td><td>Registered</td><td><code>registered</code></td><td>User account created</td></tr>
            <tr><td><strong>3</strong></td><td>Bank Account Created</td><td><code>Bank Account Created</code></td><td>Bank account linked via Plaid</td></tr>
            <tr><td><strong>4</strong></td><td>Payment Method Added</td><td><code>payment_method_added</code></td><td>Payment method configured</td></tr>
            <tr><td><strong>5</strong></td><td>Investment Completed</td><td><code>investmentFinished</code></td><td>First (or subsequent) investment made</td></tr>
        </tbody>
    </table>

    <h4>Exploration Configuration</h4>
    <table>
        <thead><tr><th>Setting</th><th>Value</th></tr></thead>
        <tbody>
            <tr><td>Technique</td><td>Funnel exploration — Standard funnel</td></tr>
            <tr><td>Open Funnel</td><td>Enabled (users can enter at any step)</td></tr>
            <tr><td>Breakdown Dimension</td><td><strong>First user default channel group</strong></td></tr>
            <tr><td>Additional Dimensions</td><td>Session default channel group, Device category, Country, First user medium, Event name, Gender</td></tr>
            <tr><td>Segments</td><td>Direct traffic, Paid traffic, Mobile traffic, Tablet traffic</td></tr>
            <tr><td>Metrics</td><td>Active users, Event count, Transactions</td></tr>
        </tbody>
    </table>

    <div class="callout info">
        <strong>How to use:</strong> Open the funnel exploration link above. Toggle between "Open" and "Closed" funnel views. Change the Breakdown dimension to <em>Session default channel group</em> for session-level attribution, or <em>Device category</em> for device breakdown. Adjust the date range as the property accumulates more data.
    </div>
</section>


<!-- ============================================================ -->
<!-- 9. GA4 REPORT LINKS -->
<!-- ============================================================ -->
<section id="ga4-reports">
    <div class="section-num">Section 9</div>
    <h3>Direct GA4 Report Links</h3>
    <p>Click any link below to open the report directly in GA4 for the unified property (523095876).</p>

    <h4>Reports — Life Cycle</h4>
    <div class="link-grid">
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-acquisition-v2&ruid=lifecycle-acquisition-v2" target="_blank" rel="noopener">
            <div class="lc-label ga4">Acquisition</div>
            <div class="lc-title">User Acquisition</div>
            <div class="lc-desc">How users were first acquired — by default channel group</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-traffic-acquisition-v2&ruid=lifecycle-traffic-acquisition-v2" target="_blank" rel="noopener">
            <div class="lc-label ga4">Acquisition</div>
            <div class="lc-title">Traffic Acquisition</div>
            <div class="lc-desc">Session-level traffic sources — Direct, Paid, Organic, etc.</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-engagement-overview&ruid=lifecycle-engagement-overview" target="_blank" rel="noopener">
            <div class="lc-label ga4">Engagement</div>
            <div class="lc-title">Engagement Overview</div>
            <div class="lc-desc">Avg engagement time, engaged sessions, events per session</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/explorer?params=_u..nav%3Dmaui%26_r.explorerCard..selmet%3D%5B%22eventCount%22%5D%26_r.explorerCard..seldim%3D%5B%22eventName%22%5D&r=top-events&ruid=top-events" target="_blank" rel="noopener">
            <div class="lc-label ga4">Engagement</div>
            <div class="lc-title">Events</div>
            <div class="lc-desc">All events with counts — filter by event name</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/conversions" target="_blank" rel="noopener">
            <div class="lc-label ga4">Engagement</div>
            <div class="lc-title">Key Events (Conversions)</div>
            <div class="lc-desc">21 key events — investmentFinished, registered, payment_method_added, etc.</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-retention-overview&ruid=lifecycle-retention-overview" target="_blank" rel="noopener">
            <div class="lc-label ga4">Retention</div>
            <div class="lc-title">Retention Overview</div>
            <div class="lc-desc">New vs returning users, cohort retention, engagement over time</div>
        </a>
    </div>

    <h4>Reports — User</h4>
    <div class="link-grid">
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=user-demographics-overview&ruid=user-demographics-overview" target="_blank" rel="noopener">
            <div class="lc-label ga4">User</div>
            <div class="lc-title">Demographics Overview</div>
            <div class="lc-desc">Country, age, gender, interests breakdown</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=user-technology-overview&ruid=user-technology-overview" target="_blank" rel="noopener">
            <div class="lc-label ga4">User</div>
            <div class="lc-title">Tech Overview</div>
            <div class="lc-desc">Platform, OS, device, browser, screen resolution</div>
        </a>
    </div>

    <h4>Explorations &amp; Custom Reports</h4>
    <div class="link-grid">
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/analysis/a40960181p523095876/edit/qU5-bf-qQiO4vd-8h80NzQ" target="_blank" rel="noopener">
            <div class="lc-label report">Exploration</div>
            <div class="lc-title">Onboarding Funnel by Traffic Source</div>
            <div class="lc-desc">5-step funnel with First user default channel group breakdown</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/analysis/a40960181p523095876/new" target="_blank" rel="noopener">
            <div class="lc-label report">Exploration</div>
            <div class="lc-title">Create New Exploration</div>
            <div class="lc-desc">Build custom freeform, funnel, path, or cohort explorations</div>
        </a>
    </div>

    <h4>Admin Pages</h4>
    <div class="link-grid">
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/a40960181p523095876/admin" target="_blank" rel="noopener">
            <div class="lc-label ga4">Admin</div>
            <div class="lc-title">Property Settings</div>
            <div class="lc-desc">Property-level configuration, data retention, Google Signals</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/streams/table" target="_blank" rel="noopener">
            <div class="lc-label ga4">Admin</div>
            <div class="lc-title">Data Streams</div>
            <div class="lc-desc">Manage all 5 data streams (web, iOS, Android)</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/events" target="_blank" rel="noopener">
            <div class="lc-label ga4">Admin</div>
            <div class="lc-title">Events Configuration</div>
            <div class="lc-desc">View, create, and mark events as key events</div>
        </a>
        <a class="link-card" href="https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/audiences/table" target="_blank" rel="noopener">
            <div class="lc-label ga4">Admin</div>
            <div class="lc-title">Audiences</div>
            <div class="lc-desc">Create and manage remarketing audiences</div>
        </a>
    </div>
</section>


<!-- ============================================================ -->
<!-- 10. CHANGELOG -->
<!-- ============================================================ -->
<section id="changelog">
    <div class="section-num">Section 10</div>
    <h3>Changelog — All Actions Taken</h3>
    <p>A complete chronological record of every change made across all Google accounts during the unified GA4 setup.</p>

    <div class="timeline">
        <div class="tl-item">
            <div class="tl-date">Feb 4, 2026</div>
            <div class="tl-dot"></div>
            <div class="tl-content">
                <strong>Unified GA4 property created</strong>
                <div class="tl-detail">Property 523095876 (G-W822YJN0Q4) created under GA4 account a40960181. Two web data streams added: Groundfloor.com – Main Website (13411990980) and Groundfloor.us – Web Application (13412016041).</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 4, 2026</div>
            <div class="tl-dot"></div>
            <div class="tl-content">
                <strong>Cross-domain tracking configured</strong>
                <div class="tl-detail">Linker configuration set between groundfloor.com (contains match) and groundfloor.us (exact match). Referral exclusions added for both domains.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 4, 2026</div>
            <div class="tl-dot"></div>
            <div class="tl-content">
                <strong>Google Ads account linked</strong>
                <div class="tl-detail">Account 612-495-1271 (GROUNDFLOOR) linked to unified property by greg.cordell@groundfloor.us. Personalized Advertising enabled.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 4, 2026</div>
            <div class="tl-dot"></div>
            <div class="tl-content">
                <strong>GTM-53NRNKD6 — Unified Google Tag deployed</strong>
                <div class="tl-detail">Published Version 36 of the groundfloor.com GTM container with the unified Google Tag (G-W822YJN0Q4) firing on Initialization – All Pages.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 4, 2026</div>
            <div class="tl-dot"></div>
            <div class="tl-content">
                <strong>Google Search Console linked</strong>
                <div class="tl-detail">https://groundfloor.com/ (URL-prefix) linked to the Groundfloor.com – Main Website data stream.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 12, 2026<br><span style="font-size:10px;color:#999;">Morning</span></div>
            <div class="tl-dot" style="background:var(--blue)"></div>
            <div class="tl-content">
                <strong>GTM-K8SQFHW — Unified Forward Events tag created</strong>
                <div class="tl-detail">A new tag "GA4 Unified – Forward Events – G-W822YJN0Q4" was created in the groundfloor.us container, duplicating the existing forward-events tag but pointing to the unified measurement ID. Published as Version 226. This routes all custom dataLayer events (value, accountType, orderId, amountInvested, utmCampaign, utmTerm) and userId to the unified property.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 12, 2026<br><span style="font-size:10px;color:#999;">Afternoon</span></div>
            <div class="tl-dot" style="background:var(--blue)"></div>
            <div class="tl-content">
                <strong>Firebase integration — Orphaned link removed</strong>
                <div class="tl-detail">Discovered accidental GCP project "groundfloor-unified--all-plat" (#972930606463) blocking the real Firebase link. Orphaned Firebase link deleted via GA4 Admin API (<code>properties.firebaseLinks.delete</code>). Accidental GCP project shut down via GCP Console.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 12, 2026<br><span style="font-size:10px;color:#999;">Afternoon</span></div>
            <div class="tl-dot" style="background:var(--blue)"></div>
            <div class="tl-content">
                <strong>Firebase project linked to unified property</strong>
                <div class="tl-detail">Firebase project <code>gf-investor-mobile-app</code> (966198890720) linked to unified property 523095876. iOS stream 13603838468 and Android stream 13603583831 created. Enhanced Audience Integration enabled. No app code changes required.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 12, 2026<br><span style="font-size:10px;color:#999;">Evening</span></div>
            <div class="tl-dot" style="background:var(--purple)"></div>
            <div class="tl-content">
                <strong>GTM-53NRNKD6 — All 26 GA4 Event tags updated</strong>
                <div class="tl-detail">Full audit of 36 tags completed. All 26 GA4 Event tags updated from legacy <code>G-73JBQSSWXH</code> to unified <code>G-W822YJN0Q4</code>. Published as Version 37 ("Unified GA4 Property - Event Tags Update") at 5:46 PM. Legacy Google Tags intentionally preserved for dual-tagging transition.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 12, 2026<br><span style="font-size:10px;color:#999;">Evening</span></div>
            <div class="tl-dot" style="background:var(--purple)"></div>
            <div class="tl-content">
                <strong>21 key events marked</strong>
                <div class="tl-detail">6 new key events marked: registered, payment_method_added, investmentFinished, begin_registration, accreditation_verified, Bank Account Created. These join 15 previously configured key events for a total of 21.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 12, 2026<br><span style="font-size:10px;color:#999;">Evening</span></div>
            <div class="tl-dot" style="background:var(--purple)"></div>
            <div class="tl-content">
                <strong>Google Ads conversion import staged</strong>
                <div class="tl-detail">7 key events selected and categorized for import into Google Ads from the unified property: investmentFinished (Purchase), payment_method_added (Add to cart), and 5 Signup events. Final save requires admin with edit access on Google Ads account.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 12, 2026<br><span style="font-size:10px;color:#999;">Late evening</span></div>
            <div class="tl-dot" style="background:#e37400"></div>
            <div class="tl-content">
                <strong>Full cross-platform verification completed</strong>
                <div class="tl-detail">End-to-end verification: all 5 data streams confirmed healthy, 123 concurrent users across Web (73), iOS (31), Android (19). All 21 key events verified. 12 traffic acquisition channels confirmed. Cross-domain tracking confirmed. investmentFinished appearing from 3 streams.</div>
            </div>
        </div>
        <div class="tl-item">
            <div class="tl-date">Feb 12, 2026<br><span style="font-size:10px;color:#999;">Late evening</span></div>
            <div class="tl-dot" style="background:#e37400"></div>
            <div class="tl-content">
                <strong>Onboarding Funnel Exploration created</strong>
                <div class="tl-detail">"Onboarding Funnel by Traffic Source" exploration created in GA4 with 5 funnel steps (begin_registration → registered → Bank Account Created → payment_method_added → investmentFinished), breakdown by First user default channel group. Open funnel enabled. Date range: Feb 4–11, 2026. Initial data showing users from Direct, Organic Search, and Referral channels.</div>
            </div>
        </div>
    </div>
</section>


<!-- ============================================================ -->
<!-- 11. LEGACY -->
<!-- ============================================================ -->
<section id="legacy">
    <div class="section-num">Section 11</div>
    <h3>Legacy Properties Reference</h3>
    <p>These properties are being maintained during the 30–90 day transition period. Do not delete or archive until the validation period is complete.</p>

    <table>
        <thead><tr><th>Property</th><th>ID</th><th>Measurement ID</th><th>Purpose</th><th>Status</th></tr></thead>
        <tbody>
            <tr>
                <td><strong>Groundfloor.com (legacy)</strong></td>
                <td>434315098</td>
                <td>G-73JBQSSWXH</td>
                <td>Original marketing site tracking</td>
                <td><span class="badge info">Dual-tagging active</span></td>
            </tr>
            <tr>
                <td><strong>Investor Web App (legacy)</strong></td>
                <td>280645774</td>
                <td>G-DPQ1WQ71R9</td>
                <td>Original .us web app tracking</td>
                <td><span class="badge info">Dual-tagging active</span></td>
            </tr>
            <tr>
                <td><strong>Investor Mobile App Platform</strong></td>
                <td>304327914</td>
                <td>N/A (Firebase)</td>
                <td>Original mobile app tracking (iOS + Android)</td>
                <td><span class="badge pending">To be deprecated</span></td>
            </tr>
            <tr>
                <td><strong>Lending Property</strong></td>
                <td>—</td>
                <td>G-8XBKNS31ZB</td>
                <td>Lending-specific tracking</td>
                <td><span class="badge info">Separate property</span></td>
            </tr>
        </tbody>
    </table>

    <div class="callout warn">
        <strong>Important:</strong> Legacy Google Tags in both GTM containers were intentionally left unchanged. Others in the company use GA4 events on these legacy properties. After the validation period (60–90 days), a separate cleanup project will remove the legacy tags.
    </div>
</section>


<!-- ============================================================ -->
<!-- 12. PENDING -->
<!-- ============================================================ -->
<section id="pending">
    <div class="section-num">Section 12</div>
    <h3>Pending Items &amp; Next Steps</h3>

    <table>
        <thead><tr><th>Item</th><th>Priority</th><th>Owner</th><th>Status</th><th>Notes</th></tr></thead>
        <tbody>
            <tr>
                <td><strong>Complete Google Ads conversion import</strong></td>
                <td>High</td>
                <td>Admin with Google Ads edit access</td>
                <td><span class="badge pending">Needs Admin</span></td>
                <td>Navigate to Google Ads &gt; Conversions &gt; Import &gt; GA4. Re-select the 7 staged events and click "Save and continue."</td>
            </tr>
            <tr>
                <td><strong>Remove legacy Ads conversion imports</strong></td>
                <td>Medium</td>
                <td>Marketing</td>
                <td><span class="badge pending">After above</span></td>
                <td>Remove old conversion actions from Mobile App property (304327914) to avoid double-counting.</td>
            </tr>
            <tr>
                <td><strong>Notify mobile dev, marketing, analytics teams</strong></td>
                <td>Medium</td>
                <td>GA4 Admin</td>
                <td><span class="badge pending">Pending</span></td>
                <td>Inform all teams that mobile analytics now routes to the unified property.</td>
            </tr>
            <tr>
                <td><strong>Validate cross-platform data (2+ weeks)</strong></td>
                <td>Medium</td>
                <td>Analytics Team</td>
                <td><span class="badge pending">Ongoing</span></td>
                <td>Compare daily metrics between unified and legacy properties to ensure no data loss.</td>
            </tr>
            <tr>
                <td><strong>Archive legacy properties</strong></td>
                <td>Low</td>
                <td>GA4 Admin</td>
                <td><span class="badge info">60–90 days</span></td>
                <td>After validation: archive properties 434315098, 280645774, 304327914 and remove legacy GTM tags.</td>
            </tr>
        </tbody>
    </table>
</section>

</div><!-- /wrapper -->

<div style="background:var(--gf-dark);color:#fff;padding:20px;text-align:center;font-size:12px;margin-top:32px;">
    <p>Groundfloor Analytics Setup Guide — GA4 Property 523095876 (G-W822YJN0Q4)</p>
    <p style="opacity:.6;margin-top:4px;">Generated Feb 12, 2026 &middot; Groundfloor Analytics &middot; All links verified at time of creation</p>
</div>

</body>
</html>

