# Groundfloor Unified GA4 Analytics — Complete Setup Reference

> A single source of truth for the analytics infrastructure across groundfloor.com, groundfloor.us, iOS app, and Android app. Includes direct links to every property, report, tag container, and integration.

| | |
|---|---|
| **GA4 Property** | `523095876` |
| **Measurement ID** | `G-W822YJN0Q4` |
| **Google Ads** | `612-495-1271` |
| **Firebase Project** | `gf-investor-mobile-app` |
| **Last Updated** | February 12, 2026 |

---

## Table of Contents

1. [Quick Links — All Properties, Reports & Tools](#1-quick-links--all-properties-reports--tools)
2. [Architecture Overview](#2-architecture-overview)
3. [Data Streams & Platforms](#3-data-streams--platforms)
4. [Google Tag Manager Setup](#4-google-tag-manager-setup)
5. [Firebase & Mobile App Integration](#5-firebase--mobile-app-integration)
6. [Product Integrations (Google Ads, Search Console)](#6-product-integrations)
7. [Key Events & Conversion Tracking](#7-key-events--conversion-tracking)
8. [Onboarding Funnel Exploration](#8-onboarding-funnel-exploration)
9. [Direct GA4 Report Links](#9-direct-ga4-report-links)
10. [Changelog — All Actions Taken](#10-changelog--all-actions-taken)
11. [Legacy Properties Reference](#11-legacy-properties-reference)
12. [Pending Items & Next Steps](#12-pending-items--next-steps)

---

## 1. Quick Links — All Properties, Reports & Tools

Direct links to every Google account, property, and tool involved in the Groundfloor analytics setup. Bookmark this section for day-to-day access.

### GA4 Analytics

| Report | Description | Link |
|---|---|---|
| **Groundfloor Unified – All Platforms** | Property 523095876 · G-W822YJN0Q4 · All web + mobile data | [Open GA4 Property →](https://analytics.google.com/analytics/web/#/p523095876/reports/home) |
| **Traffic Acquisition Report** | Session-level traffic sources: Direct, Organic, Paid, Referral, etc. | [Open Report →](https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-acquisition-v2&ruid=lifecycle-acquisition-v2&collectionId=life-cycle) |
| **Events (All Events)** | Full list of events flowing into the unified property | [Open Report →](https://analytics.google.com/analytics/web/#/p523095876/reports/explorer?params=_u..nav%3Dmaui%26_r.explorerCard..selmet%3D%5B%22eventCount%22%5D%26_r.explorerCard..seldim%3D%5B%22eventName%22%5D&r=top-events&ruid=top-events&collectionId=life-cycle) |
| **Key Events (Conversions)** | 21 key events including investmentFinished, registered, payment_method_added | [Open Report →](https://analytics.google.com/analytics/web/#/p523095876/reports/conversions) |
| **Realtime Overview** | Live users across web + iOS + Android right now | [Open Realtime →](https://analytics.google.com/analytics/web/#/p523095876/realtime/overview) |
| **Onboarding Funnel by Traffic Source** | 5-step funnel: Registration → Registered → Bank Acct → Payment → Investment, by channel | [Open Exploration →](https://analytics.google.com/analytics/web/#/analysis/a40960181p523095876/edit/qU5-bf-qQiO4vd-8h80NzQ) |

### GA4 Admin

| Page | Description | Link |
|---|---|---|
| **Data Streams (5 total)** | Web (.com, .us), iOS app, Android app, Testing API | [Open →](https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/streams/table) |
| **Events & Key Events Config** | Mark/unmark key events, view event parameters | [Open →](https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/events) |
| **Firebase Integration** | Firebase project gf-investor-mobile-app linked Feb 12, 2026 | [Open →](https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/firebase) |
| **Google Ads Integration** | Account 612-495-1271 linked Feb 4, 2026 | [Open →](https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/googleads) |

### Google Tag Manager

| Container | Description | Link |
|---|---|---|
| **GTM-53NRNKD6 (Version 37)** | groundfloor.com — 36 tags: 5 Google Tags, 26 GA4 Events, 1 Conversion Linker, 6 HTML/Schema | [Open Container →](https://tagmanager.google.com/#/container/accounts/6299000195/containers/222186267/workspaces?apiLink=container) |
| **Version 37: Unified GA4 Event Tags Update** | Published Feb 12, 2026 — All 26 GA4 event tags updated to G-W822YJN0Q4 | [Open Version →](https://tagmanager.google.com/#/versions/accounts/6299000195/containers/222186267/versions/37) |
| **GTM-K8SQFHW (Version 226)** | groundfloor.us — Unified forward-events tag sends all custom events to G-W822YJN0Q4 | [Open Container →](https://tagmanager.google.com/#/container/accounts/6054498498/containers/95498538/workspaces?apiLink=container) |

### Google Ads & Firebase

| Service | Description | Link |
|---|---|---|
| **GROUNDFLOOR (612-495-1271)** | Linked to unified property. 7 conversions staged for import (needs admin save). | [Open Google Ads →](https://ads.google.com/aw/overview?ocid=107041362&ascid=107041362) |
| **Conversion Actions** | Import GA4 key events as conversion goals for campaign optimization | [Open Conversions →](https://ads.google.com/aw/conversions?ocid=107041362&ascid=107041362) |
| **Firebase Console** | Project #966198890720 · iOS + Android apps · Linked to unified GA4 property | [Open Firebase →](https://console.firebase.google.com/project/gf-investor-mobile-app/overview) |
| **Firebase Analytics Dashboard** | Mobile app analytics routed to unified GA4 property | [Open Analytics →](https://console.firebase.google.com/project/gf-investor-mobile-app/analytics) |

---

## 2. Architecture Overview

The unified GA4 property consolidates data from four platforms into a single analytics view. All traffic sources, conversions, and user journeys are tracked in one place for the first time.

> **Why unified?** Previously, Groundfloor had separate GA4 properties for the marketing site (.com), web application (.us), and mobile apps. This made it impossible to see a user's full journey from ad click → registration → first investment across platforms. The unified property solves this.

| Platform | Domain / App | Data Collection Method | Routing to GA4 |
|---|---|---|---|
| **Marketing Site** | groundfloor.com | GTM container GTM-53NRNKD6 (Version 37) | Google Tag G-W822YJN0Q4 + 26 GA4 Event tags |
| **Web Application** | groundfloor.us | GTM container GTM-K8SQFHW (Version 226) | Forward Events tag → G-W822YJN0Q4 + cross-domain linking |
| **iOS App** | us.groundfloor.merlin | Firebase SDK (GoogleService-Info.plist) | Firebase → GA4 link (server-side routing) |
| **Android App** | us.groundfloor.merlin | Firebase SDK (google-services.json) | Firebase → GA4 link (server-side routing) |

### Cross-Domain Tracking

Cross-domain linking is configured between `groundfloor.com` (contains match) and `groundfloor.us` (exact match). This preserves user sessions when visitors navigate from the marketing site to the web application, ensuring proper traffic source attribution.

### Referral Exclusions

Both `groundfloor.com` and `groundfloor.us` are set as referral exclusions to prevent self-referral attribution noise between the two domains.

---

## 3. Data Streams & Platforms

The unified property has 5 data streams. Three are actively receiving traffic; the .us stream routes through the .com stream via cross-domain tracking; and the Testing API stream was auto-created by Firebase.

| Stream Name | Type | Stream ID | Identifier | Status |
|---|---|---|---|---|
| **Groundfloor.com – Main Website** | Web | 13411990980 | G-W822YJN0Q4 | ✅ Receiving Traffic |
| **Groundfloor.us – Web Application** | Web | 13412016041 | G-W822YJN0Q4 | ℹ️ Routes via .com stream |
| **Groundfloor Investor App** | iOS | 13603838468 | us.groundfloor.merlin | ✅ Receiving Traffic |
| **Groundfloor Investor App** | Android | 13603583831 | us.groundfloor.merlin | ✅ Receiving Traffic |
| **Testing API** | Web | 13603766723 | — | ℹ️ Auto-created (Firebase) |

### Platform Breakdown (28-Day, Verified Feb 12)

| Platform | Active Users (Realtime) | OS Distribution (28d) | Device Split |
|---|---|---|---|
| Web | 73 | Windows 7K, Mac 2K, Linux 295, Chrome OS 116 | Desktop 55.1% |
| iOS | 31 | iOS 5.2K | Mobile 43.7%, Tablet 1.3% |
| Android | 19 | Android 2.6K | _(included above)_ |

---

## 4. Google Tag Manager Setup

### GTM-53NRNKD6 — groundfloor.com (Marketing Site)

This container manages all tracking on the Groundfloor marketing website. It was fully audited and updated on Feb 12, 2026.

| Tag Type | Count | Details | Measurement ID |
|---|---|---|---|
| **Google Tags** | 5 | Unified, Legacy .com, Legacy .us, Lending, Google Ads | G-W822YJN0Q4 (unified), G-73JBQSSWXH, G-DPQ1WQ71R9, G-8XBKNS31ZB, AW-968207878 |
| **GA4 Event Tags** | 26 | All CTA click events, form submissions, content engagement | G-W822YJN0Q4 ✅ Updated Feb 12 |
| **Conversion Linker** | 1 | Google Ads conversion tracking | — |
| **Custom HTML / Schema** | 6 | 5 FAQ Schema + 1 Software Application Schema | — |

> **Action Taken (Feb 12):** All 26 GA4 Event tags were updated from the legacy measurement ID (`G-73JBQSSWXH`) to the unified ID (`G-W822YJN0Q4`). The 5 Google Tags were intentionally left unchanged for dual-tagging during the 30–90 day transition period. Published as **Version 37**.

**Notable GA4 Event Tags (examples of the 26):**

| Tag Name | Event | Trigger |
|---|---|---|
| GA4 - Get Started Button Clicks | `get_started_click` | CTA button clicks |
| GA4 - Create Account Button | `create_account_click` | Create account CTA |
| GA4 - Contact Form Submission | `contact_form_submission` | Form submit |
| GA4 - View Properties | `view_properties_click` | Property listing clicks |
| GA4 - Scroll Depth | `scroll_depth` | Scroll milestones |
| _+ 21 more event tags_ | | _Content engagement, navigation, and conversion CTAs_ |

### GTM-K8SQFHW — groundfloor.us (Web Application)

The .us container uses a dynamic "Forward Events" pattern that catches all custom dataLayer events and sends them to GA4 with their parameters.

> **Action Taken (Feb 12):** The existing "Forward events" tag was routing to the old property (`G-DPQ1WQ71R9`). A new tag — **"GA4 Unified – Forward Events – G-W822YJN0Q4"** — was created as a duplicate with the correct measurement ID and published as **Version 226**. This tag forwards all custom events with parameters: `value`, `accountType`, `orderId`, `amountInvested`, `utmCampaign`, `utmTerm`, and the `userId` user property.

---

## 5. Firebase & Mobile App Integration

The iOS and Android apps use the Firebase Analytics SDK. On Feb 12, 2026, the Firebase project was linked to the unified GA4 property, routing all mobile analytics data to the single view. **No app code changes were required.**

| Field | Value |
|---|---|
| Firebase Project ID | `gf-investor-mobile-app` |
| Firebase Project Number | 966198890720 |
| iOS Firebase App ID | `1:966198890720:ios:8f22229b579556e6124085` |
| Android Firebase App ID | `1:966198890720:android:4e9dd7ae06907309124085` |
| Bundle / Package Name | `us.groundfloor.merlin` |
| Enhanced Audience Integration | ✅ Enabled |
| Firebase Link Date (unified) | February 12, 2026 |
| App Versions Verified | iOS v2.0.34, Android v2.0.34 |

> ⚠️ **Orphaned project resolved:** An accidental GCP project (`groundfloor-unified--all-plat`, #972930606463) had been auto-created and was blocking the real Firebase link. It was identified via the GA4 Admin API (`properties.firebaseLinks.list`), deleted via `properties.firebaseLinks.delete`, and the GCP project was shut down. The real project then linked successfully.

---

## 6. Product Integrations

### Google Ads — 612-495-1271 (AW-968207878)

| Setting | Value |
|---|---|
| Account Name | GROUNDFLOOR |
| Account ID | 612-495-1271 / AW-968207878 |
| Linked to Unified Property | Feb 4, 2026 (by greg.cordell@groundfloor.us) |
| Personalized Advertising | ✅ Enabled |
| Conversion Import | ⏳ 7 events staged — needs admin save |

**Staged conversion imports (pending admin with edit access):**

| GA4 Event | Google Ads Category | Status |
|---|---|---|
| `investmentFinished` | Purchase | ⏳ Staged |
| `payment_method_added` | Add to cart | ⏳ Staged |
| `Bank Account Created` | Signup | ⏳ Staged |
| `registered` | Signup | ⏳ Staged |
| `begin_registration` | Signup | ⏳ Staged |
| `accreditation_verified` | Signup | ⏳ Staged |
| `onboardingLinkBankAccountComplete` | Signup | ⏳ Staged |

### Google Search Console

| Setting | Value |
|---|---|
| Property | https://groundfloor.com/ (URL-prefix) |
| Linked Stream | Groundfloor.com – Main Website (13411990980) |
| Note | Domain-level properties were unavailable (already linked to legacy GA4 properties) |

---

## 7. Key Events & Conversion Tracking

21 key events are configured in the unified property. These track the full investor lifecycle from first visit through investment completion.

| Key Event | Category | Streams Active | Notes |
|---|---|---|---|
| **`investmentFinished`** | Investment | Web + iOS + Android | Primary conversion — investment completed |
| **`payment_method_added`** | Onboarding | Web + iOS + Android | Payment method linked |
| **`session_start`** | Engagement | Web + iOS + Android | New session initiated |
| **`begin_registration`** | Registration | 2 streams | User starts signup flow |
| **`complete_registration`** | Registration | 2 streams | User completes signup |
| **`registered`** | Registration | 2 streams | Registration confirmed |
| **`first_open`** | App | 2 streams | First app open |
| **`accreditation_verified`** | Onboarding | Web | Accredited investor verification |
| **`Bank Account Created`** | Onboarding | Web | Bank account linked |
| **`onboardingLinkBankAccountComplete`** | Onboarding | Web | Plaid bank linking completed |
| **`form_submit`** | Engagement | Web | Contact/signup form submitted |
| **`view_search_results`** | Engagement | Web | Property search executed |
| _+ 9 additional e-commerce events_ | | | _add_to_cart, purchase, view_item, etc. — awaiting data_ |

---

## 8. Onboarding Funnel Exploration

The primary reporting deliverable for this project: a 5-step investor onboarding funnel broken down by traffic source. This answers the core question — _"Which traffic sources drive the most completed investors?"_

**[Open Onboarding Funnel by Traffic Source →](https://analytics.google.com/analytics/web/#/analysis/a40960181p523095876/edit/qU5-bf-qQiO4vd-8h80NzQ)**

### Funnel Steps

| Step | Name | GA4 Event | What It Tracks |
|---|---|---|---|
| **1** | Begin Registration | `begin_registration` | User starts the signup process |
| **2** | Registered | `registered` | User account created |
| **3** | Bank Account Created | `Bank Account Created` | Bank account linked via Plaid |
| **4** | Payment Method Added | `payment_method_added` | Payment method configured |
| **5** | Investment Completed | `investmentFinished` | First (or subsequent) investment made |

### Exploration Configuration

| Setting | Value |
|---|---|
| Technique | Funnel exploration — Standard funnel |
| Open Funnel | Enabled (users can enter at any step) |
| Breakdown Dimension | **First user default channel group** |
| Additional Dimensions | Session default channel group, Device category, Country, First user medium, Event name, Gender |
| Segments | Direct traffic, Paid traffic, Mobile traffic, Tablet traffic |
| Metrics | Active users, Event count, Transactions |

> ℹ️ **How to use:** Open the funnel exploration link above. Toggle between "Open" and "Closed" funnel views. Change the Breakdown dimension to _Session default channel group_ for session-level attribution, or _Device category_ for device breakdown. Adjust the date range as the property accumulates more data.

---

## 9. Direct GA4 Report Links

Click any link below to open the report directly in GA4 for the unified property (523095876).

### Reports — Life Cycle

| Category | Report | Link |
|---|---|---|
| Acquisition | **User Acquisition** — How users were first acquired, by default channel group | [Open →](https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-acquisition-v2&ruid=lifecycle-acquisition-v2) |
| Acquisition | **Traffic Acquisition** — Session-level traffic sources: Direct, Paid, Organic, etc. | [Open →](https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-traffic-acquisition-v2&ruid=lifecycle-traffic-acquisition-v2) |
| Engagement | **Engagement Overview** — Avg engagement time, engaged sessions, events per session | [Open →](https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-engagement-overview&ruid=lifecycle-engagement-overview) |
| Engagement | **Events** — All events with counts, filter by event name | [Open →](https://analytics.google.com/analytics/web/#/p523095876/reports/explorer?params=_u..nav%3Dmaui%26_r.explorerCard..selmet%3D%5B%22eventCount%22%5D%26_r.explorerCard..seldim%3D%5B%22eventName%22%5D&r=top-events&ruid=top-events) |
| Engagement | **Key Events (Conversions)** — 21 key events: investmentFinished, registered, etc. | [Open →](https://analytics.google.com/analytics/web/#/p523095876/reports/conversions) |
| Retention | **Retention Overview** — New vs returning users, cohort retention, engagement over time | [Open →](https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=lifecycle-retention-overview&ruid=lifecycle-retention-overview) |

### Reports — User

| Category | Report | Link |
|---|---|---|
| User | **Demographics Overview** — Country, age, gender, interests breakdown | [Open →](https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=user-demographics-overview&ruid=user-demographics-overview) |
| User | **Tech Overview** — Platform, OS, device, browser, screen resolution | [Open →](https://analytics.google.com/analytics/web/#/p523095876/reports/dashboard?params=_u..nav%3Dmaui&r=user-technology-overview&ruid=user-technology-overview) |

### Explorations & Custom Reports

| Report | Description | Link |
|---|---|---|
| **Onboarding Funnel by Traffic Source** | 5-step funnel with First user default channel group breakdown | [Open →](https://analytics.google.com/analytics/web/#/analysis/a40960181p523095876/edit/qU5-bf-qQiO4vd-8h80NzQ) |
| **Create New Exploration** | Build custom freeform, funnel, path, or cohort explorations | [Open →](https://analytics.google.com/analytics/web/#/analysis/a40960181p523095876/new) |

### Admin Pages

| Page | Description | Link |
|---|---|---|
| **Property Settings** | Property-level configuration, data retention, Google Signals | [Open →](https://analytics.google.com/analytics/web/#/a40960181p523095876/admin) |
| **Data Streams** | Manage all 5 data streams (web, iOS, Android) | [Open →](https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/streams/table) |
| **Events Configuration** | View, create, and mark events as key events | [Open →](https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/events) |
| **Audiences** | Create and manage remarketing audiences | [Open →](https://analytics.google.com/analytics/web/#/a40960181p523095876/admin/audiences/table) |

---

## 10. Changelog — All Actions Taken

A complete chronological record of every change made across all Google accounts during the unified GA4 setup.

### Feb 4, 2026

- **Unified GA4 property created** — Property 523095876 (G-W822YJN0Q4) created under GA4 account a40960181. Two web data streams added: Groundfloor.com – Main Website (13411990980) and Groundfloor.us – Web Application (13412016041).

- **Cross-domain tracking configured** — Linker configuration set between groundfloor.com (contains match) and groundfloor.us (exact match). Referral exclusions added for both domains.

- **Google Ads account linked** — Account 612-495-1271 (GROUNDFLOOR) linked to unified property by greg.cordell@groundfloor.us. Personalized Advertising enabled.

- **GTM-53NRNKD6 — Unified Google Tag deployed** — Published Version 36 of the groundfloor.com GTM container with the unified Google Tag (G-W822YJN0Q4) firing on Initialization – All Pages.

- **Google Search Console linked** — https://groundfloor.com/ (URL-prefix) linked to the Groundfloor.com – Main Website data stream.

### Feb 12, 2026 — Morning

- **GTM-K8SQFHW — Unified Forward Events tag created** — A new tag "GA4 Unified – Forward Events – G-W822YJN0Q4" was created in the groundfloor.us container, duplicating the existing forward-events tag but pointing to the unified measurement ID. Published as Version 226. This routes all custom dataLayer events (`value`, `accountType`, `orderId`, `amountInvested`, `utmCampaign`, `utmTerm`) and `userId` to the unified property.

### Feb 12, 2026 — Afternoon

- **Firebase integration — Orphaned link removed** — Discovered accidental GCP project "groundfloor-unified--all-plat" (#972930606463) blocking the real Firebase link. Orphaned Firebase link deleted via GA4 Admin API (`properties.firebaseLinks.delete`). Accidental GCP project shut down via GCP Console.

- **Firebase project linked to unified property** — Firebase project `gf-investor-mobile-app` (966198890720) linked to unified property 523095876. iOS stream 13603838468 and Android stream 13603583831 created. Enhanced Audience Integration enabled. No app code changes required.

### Feb 12, 2026 — Evening

- **GTM-53NRNKD6 — All 26 GA4 Event tags updated** — Full audit of 36 tags completed. All 26 GA4 Event tags updated from legacy `G-73JBQSSWXH` to unified `G-W822YJN0Q4`. Published as Version 37 ("Unified GA4 Property - Event Tags Update") at 5:46 PM. Legacy Google Tags intentionally preserved for dual-tagging transition.

- **21 key events marked** — 6 new key events marked: registered, payment_method_added, investmentFinished, begin_registration, accreditation_verified, Bank Account Created. These join 15 previously configured key events for a total of 21.

- **Google Ads conversion import staged** — 7 key events selected and categorized for import into Google Ads from the unified property: investmentFinished (Purchase), payment_method_added (Add to cart), and 5 Signup events. Final save requires admin with edit access on Google Ads account.

### Feb 12, 2026 — Late Evening

- **Full cross-platform verification completed** — End-to-end verification: all 5 data streams confirmed healthy, 123 concurrent users across Web (73), iOS (31), Android (19). All 21 key events verified. 12 traffic acquisition channels confirmed. Cross-domain tracking confirmed. `investmentFinished` appearing from 3 streams.

- **Onboarding Funnel Exploration created** — "Onboarding Funnel by Traffic Source" exploration created in GA4 with 5 funnel steps (`begin_registration` → `registered` → `Bank Account Created` → `payment_method_added` → `investmentFinished`), breakdown by First user default channel group. Open funnel enabled. Date range: Feb 4–11, 2026. Initial data showing users from Direct, Organic Search, and Referral channels.

---

## 11. Legacy Properties Reference

These properties are being maintained during the 30–90 day transition period. Do not delete or archive until the validation period is complete.

| Property | ID | Measurement ID | Purpose | Status |
|---|---|---|---|---|
| **Groundfloor.com (legacy)** | 434315098 | G-73JBQSSWXH | Original marketing site tracking | ℹ️ Dual-tagging active |
| **Investor Web App (legacy)** | 280645774 | G-DPQ1WQ71R9 | Original .us web app tracking | ℹ️ Dual-tagging active |
| **Investor Mobile App Platform** | 304327914 | N/A (Firebase) | Original mobile app tracking (iOS + Android) | ⏳ To be deprecated |
| **Lending Property** | — | G-8XBKNS31ZB | Lending-specific tracking | ℹ️ Separate property |

> ⚠️ **Important:** Legacy Google Tags in both GTM containers were intentionally left unchanged. Others in the company use GA4 events on these legacy properties. After the validation period (60–90 days), a separate cleanup project will remove the legacy tags.

---

## 12. Pending Items & Next Steps

| Item | Priority | Owner | Status | Notes |
|---|---|---|---|---|
| **Complete Google Ads conversion import** | High | Admin with Google Ads edit access | ⏳ Needs Admin | Navigate to Google Ads > Conversions > Import > GA4. Re-select the 7 staged events and click "Save and continue." |
| **Remove legacy Ads conversion imports** | Medium | Marketing | ⏳ After above | Remove old conversion actions from Mobile App property (304327914) to avoid double-counting. |
| **Notify mobile dev, marketing, analytics teams** | Medium | GA4 Admin | ⏳ Pending | Inform all teams that mobile analytics now routes to the unified property. |
| **Validate cross-platform data (2+ weeks)** | Medium | Analytics Team | ⏳ Ongoing | Compare daily metrics between unified and legacy properties to ensure no data loss. |
| **Archive legacy properties** | Low | GA4 Admin | ℹ️ 60–90 days | After validation: archive properties 434315098, 280645774, 304327914 and remove legacy GTM tags. |

---

<sub>Groundfloor Analytics Setup Guide — GA4 Property 523095876 (G-W822YJN0Q4) · Generated Feb 12, 2026</sub>
