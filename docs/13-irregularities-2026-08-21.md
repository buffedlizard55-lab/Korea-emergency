# 13. Irregularities Flagged for Review — line-by-line pass, 21 Aug 2026

This is the review log for the line-by-line verification you asked for. Items are ordered by
severity. **Nothing here was silently "fixed" in a way that hides the original problem** — each
entry states what the repo said, what the official source says, and what I changed.

Severity key: 🔴 blocking / factually wrong · 🟠 wrong for *your* trip · 🟡 accuracy or link issue ·
🔵 unverifiable in this environment (needs your eyes)

---

## 🔴 IRR-1 — The whole repo is built around the wrong itinerary

**This is the biggest problem in the repository.**

You stated: **Seoul 1–9 Nov · Busan 9–15 Nov · Seoul 15–22 Nov 2026.**

The repo is built around a completely different trip:

| Repo says | You said |
|---|---|
| Seoul 1–8 Nov (7 nights) | Seoul 1–9 Nov |
| **Daejeon / Cheonan 8–13 Nov (5 nights)** | **Not in your trip at all** |
| Busan 13–20 Nov (7 nights) | Busan 9–15 Nov |
| Seoul 20–22 Nov (2 nights) | Seoul 15–22 Nov (7 nights) |

Consequences that are wrong for you throughout `README.md`, `docs/01`, `docs/10` and `docs/index.md`:

1. **Daejeon / Cheonan** appears as a whole trip phase with KTX bookings, consular notes and hotel
   advice. You are never going there.
2. **KTX booking checklist is wrong.** The repo tells you to book 8 Nov Seoul→Daejeon, 13 Nov
   →Busan, 20 Nov Busan→Seoul. Your actual moves are **9 Nov Seoul→Busan** and **15 Nov
   Busan→Seoul**.
3. **🔴 CSAT day is mis-located.** The repo repeatedly says CSAT (Thu 19 Nov) falls "inside your
   Busan stay" and gives you a Busan-specific CSAT protocol. On your real itinerary you leave Busan
   on **15 Nov** — on **19 Nov you are in Seoul**. Any CSAT planning must be Seoul-based.
4. Night counts, the "21 nights" table and the "Seoul exceeds 5–7 days" note all describe the old plan.

**✅ RESOLVED — 2nd pass, 21 Aug 2026.** The itinerary was restated identically a second time, so it is
treated as confirmed. A corrected plan now exists at
**[`docs/15-itinerary-corrected-seoul-busan-seoul.md`](15-itinerary-corrected-seoul-busan-seoul.md)** —
Seoul 8 nights + Busan 6 + Seoul 7 = 21 nights (arithmetic recomputed), KTX legs corrected to
**9 Nov** and **15 Nov**, Daejeon/Cheonan removed, and **CSAT relocated to Seoul** with the full
verified exam timetable.

`docs/10-itinerary-day-plan.md` is **left in place but superseded** and now carries a banner at the
top. It was not deleted so the original record remains auditable.

---

## 🔴 IRR-2 — 1339 is described in a way that could cost time in an emergency

`docs/03-emergency-contacts.md` and several other files treat the emergency-number set as
112 / 119 / 1366 / 1330 and never mention 1339. Separately, older Korean material widely circulating
online still calls **1339 an "emergency medical information centre."**

**What the official sources say (verified 21 Aug 2026):**

- **KDCA** states 1339 is the **KDCA Call Center** for infectious-disease information and reporting,
  available 24/7/365 — [kdca.go.kr/eng](https://www.kdca.go.kr/eng/4276/subview.do).
- VISITKOREA lists it as **"Infectious Disease Emergencies: +82-1339"** —
  [VISITKOREA Emergency Situations](https://english.visitkorea.or.kr/svc/contents/contentsView.do?vcontsId=140042).
- The old 1339 emergency-medical-information role was **merged into 119** (Korean press coverage of
  the 119 구조·구급 법 revision).

**Why it matters:** if either of you calls 1339 expecting an ambulance, you lose time.
**Ambulance is 119.** This is now stated explicitly in `docs/12` (N6).

---

## 🟠 IRR-3 — 122 (maritime emergency) is obsolete — relevant to your Busan coast days

Not stated in the repo, but worth locking down before Busan: the maritime emergency number **122 was
abolished and folded into 119**. Korea's official 긴급신고 통합 policy consolidated ~20 reporting
numbers into **112 (crime) / 119 (disaster, rescue, fire, maritime) / 110 (non-urgent civil)**, and
MOIS's own page lists `122(해양사고)` among the numbers merged into 119/112.

Source: [MOIS — 긴급신고 통합서비스](https://www.mois.go.kr/frt/sub/a06/b10/emergencycall/screen.do)

**For Haeundae / Gwangalli / Songdo:** if someone is in the water, call **119**. Do not look for 122.

---

## 🟠 IRR-4 — Busan Consulate "no consular services" — confirmed correct, and it matters more now

The repo's claim is **correct and now re-verified verbatim** against the State Department advisory:

> "Please note that consular services, including passport services, are not available at the U.S.
> Consulate in Busan; they are only available at the U.S. Embassy in Seoul."
> — [travel.state.gov South Korea](https://travel.state.gov/en/international-travel/travel-advisories/south-korea.html)

Emergency number re-verified on both State and Embassy sites: **+82-2-397-4114**, listed as both
main telephone and emergency after-hours, with the Embassy site showing **(02)-397-4114** in-country.
Address confirmed: **188 Sejong-daero, Jongno-gu, Seoul 03141**.
[kr.usembassy.gov](https://kr.usembassy.gov/)

**Trip-specific note:** you are in Busan **9–15 Nov**, six days with no local consular fallback. A
lost passport in Busan means a trip back to Seoul. Keep passport photocopies separated between the
two of you.

---

## 🟡 IRR-5 — Passport-validity advice contradicts the official rule

`docs/02-entry-documents.md` says a passport valid "≥6 months is best practice."

State Department's South Korea page states plainly:

> **Valid passport requirements — Must be valid at the time of entry. There is no minimum expiration
> validity requirement.**

The repo's version isn't dangerous, but it is presented next to official rules and reads like one.
It should stay clearly labelled as personal caution, not a Korean requirement.

---

## 🔴 IRR-2b — NEW: official-vs-official conflict on 1339 (found in 2nd pass)

Two Korean government sources describe **1339 differently**:

| Source | What it says |
|---|---|
| **KDCA** (the agency that operates it) | 1339 is the **KDCA Call Center** for infectious-disease information and reporting, 24/7/365 — [kdca.go.kr/eng](https://www.kdca.go.kr/eng/4276/subview.do) |
| **VISITKOREA** (KTO) | "**Infectious Disease Emergencies: +82-1339**" — [VISITKOREA](https://english.visitkorea.or.kr/svc/contents/contentsView.do?vcontsId=140042) |
| **Visit Seoul** (Seoul Tourism Organization) — ⚠️ | "**Emergency Medical Information Center: 1339 (medical assistance for international visitors)**" — [english.visitseoul.net/safety](https://english.visitseoul.net/safety) |

**Assessment:** Visit Seoul's description appears to be **stale**. The operating agency (KDCA) and the
national tourism body both describe 1339 as infectious-disease. The old "emergency medical
information center" role was merged into 119.

**Practical rule — do not depend on 1339 for an ambulance. Call 119.** Flagged because an official
Seoul tourism page still says otherwise, and a traveler following it could lose time.

---

## ✅ IRR-6 — RESOLVED: currency declaration confirmed by Korea Customs Service

Previously flagged as a State-Dept-vs-MOFA conflict. Now settled at the **authoritative source**.

Korea Customs Service, official English page:

> "If you bring in means of payment **not exceeding USD 10,000** to Korea, you do not need any
> permission or declaration… However, if you enter the country with foreign currency, KRW notes, or
> checks **above USD 10,000 or the equivalent in total, you must report it to the Customs.**"

Procedure: tick **item 3** on the Traveler Declaration Form and obtain the Certificate of Foreign
Currency Declaration — it **cannot be issued once you have left the immigration area**. Penalty for
non-declaration: up to 1 year imprisonment or a fine up to **KRW 100 million**.
[customs.go.kr — Declaration of Foreign Currency](https://www.customs.go.kr/english/cm/cntnts/cntntsView.do?mi=10800&cntntsId=5500)

**Conclusion:** the repo's USD 10,000 rule is **correct**. The State Department's "No declaration
needed on entry or exit" line is a simplification that applies below the threshold and should not be
relied on. Airport desks: **T1 032-722-4422 · T2 032-723-5119**.

---

## Superseded original wording of IRR-6

`docs/09-money-communication.md` states that currency over **USD 10,000** must be declared to
Customs, sourced to a ROK MOFA consular page (S16).

The State Department country page for South Korea now says under **Currency on entry and exit**:
**"No declaration needed on entry or exit."**

These two official sources do not read the same way. This is a genuine conflict between two
government sources, not a repo invention. **Flagged, not resolved** — Korea Customs Service is the
authority and should be checked directly before you fly. Do not treat either statement as settled.

---

## 🟡 IRR-7 — Broken / redirecting official links in the existing source register

Checked every URL in `docs/sources.md` on 21 Aug 2026:

| Source | Problem | Correct URL |
|---|---|---|
| S12 KMA | `weather.go.kr/w/index.do` serves a Korean service-error/notice page in this environment | **English portal: [kma.go.kr/neng](https://www.kma.go.kr/neng/index.do)** — confirmed live, English severe-weather alerts incl. Typhoon / Heavy Rain / Heavy Snowfall / Strong Wind / Asian Dust |
| S12 (in `docs/10`) | `kma.go.kr/eng/` cited repeatedly | Redirects to `/neng/` — update to avoid a dead-looking link on the road |
| S10 KICE | `kice.re.kr` did not resolve from this sandbox | Timetable independently confirmed via the KICE guideline PDF (see IRR-8) and a provincial-education PDF |
| S2 (in `docs/verification-audit.md`) | `kr.usembassy.gov/busan/` is cited as the Busan source | That path 404s; the Busan no-services fact is on the **State Dept advisory** instead |
| S9 VISITKOREA holidays | `contentsView.do?vcontsId=140038` returned a 400 error page during this pass | Re-check; the holiday claim itself is unverified this round — see IRR-9 |

**Also:** `docs/index.md` and `README.md` describe `docs/10-itinerary-day-plan.md` as "375 lines";
it is **380 lines**. Cosmetic, but it is exactly the kind of unchecked number this project is
supposed to eliminate.

---

## ✅ IRR-8 — CSAT date and English timetable: CONFIRMED (upgraded from single-source)

The repo's CSAT claims were previously leaning on a KICE page I could not reach. Both are now
confirmed from independent official sources:

- **Date — Thursday 19 November 2026.** Korean government policy briefing (korea.kr), Ministry of
  Education announcement: the 2027학년도 수능 is held **2026. 11. 19.(목)**, results 11 Dec 2026 —
  [korea.kr](https://www.korea.kr/news/policyNewsView.do?newsId=148932726). KICE announced the
  detailed implementation plan on 30 June 2026 reaffirming 19 Nov.
- **English session — 13:10–14:20 (70 min), listening 17 questions within 25 minutes from 13:10.**
  Confirmed in the **KICE guideline PDF** ([csatcdn.kice.re.kr/resources/pdf/guideline.pdf](https://csatcdn.kice.re.kr/resources/pdf/guideline.pdf))
  and in the KICE public notice 제2026-85호 republished by Gyeonggi-do Office of Education
  ([PDF](https://www.goe.go.kr/resource/goe/na/bbs_2675/2026/06/76ed0d83-c6ac-4462-b855-8d4ce310c480.pdf)).

**Correct for your trip:** 19 Nov is a **Seoul** day for you, not Busan. Also note the full exam day
runs roughly **08:10 entry → 17:45**, so disruption is not limited to the English hour.

⚠️ **Still unverified — do not restore:** the widely repeated claim of a nationwide **13:05–13:40
flight/takeoff-and-landing hold** during the listening test appears only in unofficial wikis. The
repo was right to remove it. Verify with the airline/airport if you fly on 19 Nov.

---

## 🔵 IRR-9 — Claims I could NOT verify this pass (do not treat as confirmed)

| Claim in repo | Status |
|---|---|
| "No Korean national public holidays 1–22 Nov 2026" (S9) | ✅ **RESOLVED 2nd pass** — the VISITKOREA page loaded this time. It lists **14 public holidays for 2026** and **none is in November**. Claim confirmed. See N36 in `docs/14`. |
| AREX timetable / fares (S15) | Not reachable this pass. Repo already correctly refuses to state fixed times. |
| ICN late-night bus routes N6000/N6001 (S14) | Not reachable this pass; airport.kr redirected to the Korean intro page. Treat route numbers as needing confirmation at the airport. |
| K-ETA portal notice (S8, `bbsSn=299707`) | Not opened directly. **However the exemption itself is verified** on the State Dept page: K-ETA exemption for U.S. passport holders **extended through 31 December 2026**, required from 1 Jan 2027. |
| Lost112 national lost-property portal | Site would not load (`lost112.go.kr`, HTTP 500 / TLS failure). It is genuinely the Korean National Police portal, but because I could not read it, it is **excluded** from the 20 verified entries. |
| ICN official emergency contact table (medical centre 032-743-3119 etc.) | Appeared via the official `airport.kr` domain in search index, but the live page redirected to a Korean intro page. **Excluded** from the verified 20. |
| Seoul Metro lost & found 1577-1234 | Only found on district/third-party pages this pass, not on an official Seoul Metro page I could open. **Excluded** from the verified 20. |
| Seoul 120 Dasan foreign-language hours | Official `english.seoul.go.kr` policy page 404s; available hours differ between sources (weekday 09:00–18:00 vs. extended). **Excluded** from the verified 20 as a standalone entry. |

---

## ✅ Re-verified as correct (no change needed)

- **Travel Advisory Level 1 — Exercise normal precautions**, issued **28 May 2025**; advisory flags
  large-scale demonstrations, Korean Peninsula tensions, and civil emergency drills. ✔
- **Visa-free ≤ 90 days** for tourism/business. ✔
- **U.S. Embassy Seoul +82-2-397-4114**, 24/7, 188 Sejong-daero. ✔
- **K-ETA exemption through 31 Dec 2026**; required from 1 Jan 2027. ✔
- **e-Arrival Card** — official portal live; homepage states **"No fee required"** and **"Complete and
  submit within 3 days before arrival in Korea,"** and displays a rolling 3-day submission window.
  Portal also carries an official warning that **fake e-Arrival Card websites exist** and that
  **www.e-arrivalcard.go.kr is the only official site — any site requesting payment is not official.**
  (Worth adding to your scam awareness.) ✔
- **Weekday/date arithmetic** — recomputed with Python: 31 Oct Sat · 1 Nov Sun · **9 Nov Mon** ·
  **15 Nov Sun** · 19 Nov Thu · 22 Nov Sun. All correct. ✔
- **Medication rules** — the repo's cannabis/CBD prohibition and MFDS pre-approval requirement for
  amphetamines/narcotics/opioids matches the State Department tip: "Some prescription drugs are
  illegal in South Korea and others require pre-approval from the South Korean Ministry of Food and
  Drug Safety (K-MFDS)." ✔

---

## Status summary after the 2nd verification pass (21 Aug 2026)

| ID | Issue | Status |
|---|---|---|
| IRR-1 | Wrong itinerary (Daejeon leg; CSAT in Busan) | ✅ **Resolved** — corrected plan in `docs/15` |
| IRR-2 | 1339 not an ambulance line | ✅ Documented (N6) |
| IRR-2b | Visit Seoul still calls 1339 "Emergency Medical Information Center" | 🔴 **Open — official page appears stale; use 119** |
| IRR-3 | 122 maritime number obsolete | ✅ Documented (N24, `docs/15`) |
| IRR-4 | Busan no consular services | ✅ Re-verified correct |
| IRR-5 | Passport-validity wording | 🟡 Open — label as advice, not a Korean rule |
| IRR-6 | Currency declaration conflict | ✅ **Resolved** — Korea Customs confirms USD 10,000 (N35) |
| IRR-7 | Broken/redirecting source links | ✅ Corrected — KMA English is `/neng`, independently confirmed by Busan city (N28) |
| IRR-8 | CSAT date/time | ✅ Confirmed from two official sources; full timetable in `docs/15` |
| IRR-9 | Unverified claims | ✅ Holiday claim resolved (N36); AREX / ICN buses / Lost112 / Seoul Metro 1577-1234 **still unverified — excluded from all verified lists** |

## Remaining open items

1. **IRR-2b** — treat Visit Seoul's 1339 line as stale. Ambulance = **119**.
2. **IRR-5** — passport validity: State says no minimum; keep "6 months" labelled as caution only.
3. **Still unreachable from this environment** (do not cite as verified): `lost112.go.kr`,
   AREX timetable, ICN night-bus routes N6000/N6001, Seoul Metro lost & found 1577-1234,
   Seoul Dasan 120 foreign-language hours, Busan beach lifeguard season dates.
4. `docs/10-itinerary-day-plan.md` remains superseded-but-present by design.

*Reviewed twice, 21 Aug 2026. No claim in this file is asserted without a link that was opened, or an
explicit "unverified" label.*

---

# 3rd pass — 20 new entries (N41–N60), 21–22 Aug 2026

Set 3 is [`docs/16-seoul-busan-emergency-resources-set3.md`](16-seoul-busan-emergency-resources-set3.md).
Same rule: only official sources; failures stay here. New irregularities are numbered IRR-10+.
("21–22 Aug": the pass ran 21 Aug UTC; Korean pages showed 22 Aug KST clocks during fetches — this
also retroactively explains the "22 Aug 2026" stamp in N38.)

## 🔴 IRR-10 — LOST112 is dead; merged into 경찰민원24 (Police Minwon 24) on 26 Jan 2026 — RESOLVES the IRR-9 mystery

- `lost112.go.kr` again returned **HTTP 500** this pass. **That is not an outage — the service was
  migrated.** AREX's official lost-property page states: "'26.1.26.일부터 LOST112가 **경찴민원24**로
  통합 운영됩니다" ([airportrailroad.com/customer/lost](https://www.airportrailroad.com/customer/lost)).
- The old portal itself carries the closing notice (read via the official `lost112.go.kr` domain in
  the search index): "2026년 1월 26일부터 LOST112 서비스가 **경찴민원24**로 통합됩니다 … 도메인:
  **minwon24.police.go.kr** … 오픈일: 2026년 1월 26일 오전 9시."
- `minwon24.police.go.kr` is **live** and carries 분실물신고 / 습득물검색 (report lost / search found
  items). Korean-language interface.
- ⚠️ **Stale official pages still point to LOST112:** Seoul Metro's English FAQ (N47 source) and
  Korail's English/Japanese/Korean guides (N48 source) all still print `www.lost112.go.kr`. They are
  official but outdated on this one point. **Use minwon24.police.go.kr.**

## 🟠 IRR-11 — AREX's customer-facing site moved to airportrailroad.com (S15 outdated)

- `arex.or.kr/main.do` still loads, but it is now the **corporate** site and posts a
  service-migration notice ("공항철도 회원통합 및 서비스 이전 안내") linking the customer portal to
  **`airportrailroad.com`** — where timetables, fares, tickets, real-time trains, delay certificates
  and lost & found now live.
- `docs/sources.md` S15 describes arex.or.kr as the "official timetable and fare portal" — **update
  done in the source register this pass** (S58 added); anyone using the old deep links
  (`content.do?menuNo=MN2015…&clientLocale=en_US` in `docs/verification-audit.md`) may hit dead
  pages. The AREX notices also show a **2026 을지연습 (Ulchi civil-defense exercise) notice for
  18–21 Aug 2026** — before your trip; context only.
- AREX site is Korean-first with a language switcher (EN/CN/JP present in the selector).

## 🟡 IRR-12 — ICN late-night bus page: still unreachable live; fare numbers conflict by direction

- The official English URL (S14) **still redirects to a Korean intro page** when fetched live, as in
  the 1st pass. The route/stop/fare table was recovered via the official `airport.kr` domain in the
  search index and is now entry **N51** — but treat it as "re-open before use."
- **Fare conflict:** the current page lists **₩17,000–18,000 adult for airport→Seoul** N-buses,
  while 2024–25 airport notices list **₩10,000 adult for Seoul→airport**. Both can be true
  (direction-dependent pricing), but it means **no fare should be memorized** — confirm at the
  airport desk.

## 🟡 IRR-13 — KMA English `/eng/` pages serve an error notice (extends IRR-7)

- `kma.go.kr/eng/weather/kma_service/introduction.jsp` (Earthquake/Tsunami/Volcano service page)
  returned KMA's generic "service disruption" notice, which states KMA only operates
  `weather.go.kr/w/`-prefix pages since 2021.
- Consequence: **S54** (`kma.go.kr/eng/biz/public_04.jsp`, the 131 Weather Call Center page used by
  N39) sits on an unmanaged path pattern — **re-verify before relying on it**. The 131 number itself
  is independently confirmed by the notice page's own footer ("기상 관련 문의: 기상콜센터(131)").
  English KMA content remains at **`kma.go.kr/neng`** (IRR-7 / N28).
- No KMA earthquake/tsunami entry was added to set 3 for this reason — the Korean database (N38)
  and Busan's English guides (N19/N25) remain the cited tools.

## 🟡 IRR-14 — Seoul Metro lines 6–7 lost & found: official says Wangsimni, blogs say Taereung

- Seoul Metro's official English FAQ lists the **Lines 6·7 center at Wangsimni (02-6311-6766/6767)**.
  Several third-party guides put it at Taereung station. **The official page wins** (N47 quotes it).
  Recorded so nobody "fixes" the entry using a blog.

## 🟡 IRR-15 — Busan's own English pages disagree on the 2026 beach season (irrelevant to November, but flagged)

- Haeundae's official page: season **26 Jun – 15 Sep 2026**, 09:00–18:00 (N54).
- A Busan English news item: season extension, beaches open **1 Jun – 30 Sep**.
- **Every version ends before October**, and the city's closure notice describes the post-season
  posture as patrols + discouraging swimming. For 9–15 Nov: **no lifeguards, treat the sea as
  dangerous** (see water-safety guide N26).

## 🟡 IRR-16 — Seoul's night-pharmacy page disagrees with itself (40 vs 38)

- The official page (updated 19 Aug 2026) headline says **40 locations in 25 districts**, while the
  operating-list line says **38 pharmacies in 24 districts**. Internal inconsistency on an official
  page. Practical rule the page itself prints: **전화확인 후에 방문 — call before visiting** (N53).

## 🟢 IRR-17 — RESOLVED: kr.usembassy.gov/busan/ now loads (IRR-7's 404 finding no longer reproduces)

- The Consulate Busan page is live with current detail: Lotte Gold Rose Building 6F, #993
  Jungang-daero, Busanjin-gu; Mon–Fri 08:30–12:30 / 13:00–17:00; **"The Consulate does not conduct
  consular services"**; after-hours = Embassy duty officer (02) 397-4114 (entry **N57**). State Dept
  advisory adds phone +82-51-863-0731, email BusanConsulate@state.gov.

## 🔴 IRR-18 — README.md still carried the superseded itinerary after IRR-1 was "resolved" — FIXED THIS PASS

- IRR-1 was closed by adding `docs/15`, but **`README.md` was never edited**: its TOP-5 still said
  CSAT "inside your Busan stay", the trip-timeline table still showed the Daejeon/Cheonan phase and
  Busan 13–20 Nov, and the final checklist still listed KTX bookings for 8/13/20 Nov — all wrong
  for the stated trip (Seoul 1–9 · Busan 9–15 · Seoul 15–22; KTX 9 & 15 Nov; CSAT 19 Nov = Seoul day).
- **Fixed 21–22 Aug 2026:** README TOP-5 item, timeline table, and KTX checklist lines now match
  `docs/15`. The fix is noted here rather than silently overwritten, per the audit convention.
- `docs/10` remains superseded-by-design (audit record). `docs/01-trip-overview.md` was checked and
  already describes the corrected city split.

## Status summary after the 3rd pass

| ID | Issue | Status |
|---|---|---|
| IRR-9 (update) | Lost112 unreachable | ✅ **Explained & superseded** — merged into 경찴민원24 on 26 Jan 2026 (IRR-10); Seoul Metro 1577-1234 **verified** (N47); Seoul Dasan 120 hours **verified** (N52); Busan beach lifeguard season **verified closed in Nov** (N54); AREX **verified** via new customer site (N49); ICN night buses **verified with live-page caveat** (N51) |
| IRR-10 | LOST112 → 경찴민원24 migration | ✅ Documented (N46); stale links on official operator pages flagged |
| IRR-11 | AREX site migration | ✅ Documented (N49/N50); source register updated (S58/S59) |
| IRR-12 | ICN English page + fare direction conflict | 🟡 Open — use N51 with "confirm at airport" rule |
| IRR-13 | KMA `/eng/` link rot incl. S54 | 🟡 Open — use `/neng`; re-verify 131 page before departure |
| IRR-14 | Metro 6·7 lost&found location | ✅ Settled per official page (N47) |
| IRR-15 | Busan beach season discrepancy | ✅ Immaterial for November (N54) — flagged for the record |
| IRR-16 | Seoul night-pharmacy 40-vs-38 count | 🟡 Open — follow the page's "call first" rule (N53) |
| IRR-17 | Busan consulate page 404 | ✅ Resolved — page live (N57) |
| IRR-18 | README retained superseded itinerary | ✅ Fixed this pass |

## Remaining open items (cumulative)

1. **IRR-2b** — Visit Seoul still labels 1339 "Emergency Medical Information Center"; ambulance = **119**.
2. **IRR-5** — passport validity: keep "6 months" labelled as caution, not a Korean rule.
3. **IRR-12** — ICN English late-night bus page not renderable in this environment; fares are
   direction-dependent — confirm at the airport.
4. **IRR-13** — KMA `/eng/…` pages (incl. S54/131 page) sit on unmanaged paths; use `/neng` and
   re-verify before departure.
5. **IRR-16** — Seoul night-pharmacy count discrepancy on the official page; call before visiting.

---

# 4th pass — 20 new entries (N61–N80), 21–22 Aug 2026

Set 4 is [`docs/17-seoul-busan-emergency-resources-set4.md`](17-seoul-busan-emergency-resources-set4.md).
Same rule: only official sources; failures stay here. New irregularities are numbered IRR-19+.

## ✅ IRR-19 — ICN English Emergency Contacts page now loads (resolves part of IRR-9)

- IRR-9 excluded the ICN official emergency-contact table because the English page redirected to a
  Korean intro. On this pass **`airport.kr/ap_en/1544/subview.do` loaded in English** with the full
  table (help desk **1577-2600**, hours **07:00–22:00**, Inha medical T1/T2, lost & found, fire,
  crime). Added as **N61**.
- ⚠️ The live HTML has a markup glitch on the T2 explosives row (`Terminal 2/td>`). The printed T2
  number in that row is still **032-741-0202**.
- The dedicated Lost-and-Found hours page (`ap_en/1549/subview.do`) returned **HTTP 500** this pass,
  so **hours/locations for the L&F desks are not in set 4** — only the phone numbers from the
  Emergency Contacts table. Re-open before relying on a visit window.
- Separate ICN late-night **bus** English page (IRR-12) still did not render.

## 🟡 IRR-20 — Embassy Emergency Preparedness page still cites the unmanaged KMA `/eng` URL

- `kr.usembassy.gov/services-emergency-preparedness/` (dated **20 May 2026**) tells travelers to
  monitor KMA at **`http://web.kma.go.kr/eng/index.jsp`**. That is the same unmanaged `/eng` pattern
  flagged in IRR-7 / IRR-13. The Embassy's **131 then 9 then 1, 09:00–18:00** instruction matches
  N39. **Use `kma.go.kr/neng`** for English forecasts. Flagged so nobody "corrects" N72 toward the
  Embassy's stale KMA link.

## 🟡 IRR-21 — NHRCK English guide prints two different English email addresses

- The live 2026 English complaint guide
  ([humanrights.go.kr](https://www.humanrights.go.kr/eng/contents/view?contentsNo=143&menuLevel=3&menuNo=140))
  says English consultation is by email **`hoso@nhrc.go.kr`** on one panel and prints
  **`hoso@humanrights.go.kr`** on a later panel. Both appear on the same official page. **N68 quotes
  both and does not pick a winner.** Phone **1331** (weekdays 09:00–18:00) and the fax numbers
  (+82-2-2125-9811/9812) are unambiguous. Re-check the email before writing.

## 🟡 IRR-22 — `index.html` had a typo 경찴민원24 (wrong character) for 경찰민원24

- The GitHub Pages front page printed **경찴민원24** in the lost-property table and source line.
  The official name is **경찰민원24** (N46 / IRR-10). Fixed in this pass on `index.html`. The
  underlying URL `minwon24.police.go.kr` was already correct.

## 🟡 IRR-23 — `index.html` Seoul Metro lost-and-found phones disagree with N47

- Set 3 **N47** (Seoul Metro official English FAQ, page read) lists Line 5·8 Wangsimni
  **02-6311-6765/6768** and Line 6·7 Wangsimni **02-6311-6766/6767**.
- `index.html` had **02-6310-6765** and **02-6310-6766** (631**0**, and only one extension each).
- **The official FAQ wins.** `index.html` is aligned to N47 in this pass. Do not "fix" it back from
  a blog (see also IRR-14 on Wangsimni vs Taereung).

## 🔵 IRR-24 — Visit Busan TIC / 120-hours page would not load; not added

- `visitbusan.net` tourist-information URLs returned **HTTP 500** this pass. A search-index snippet
  from the official domain listed a Seomyeon Medical Tourism Information Center (051-818-1320,
  09:00–18:00) and a footer **051-120 Mon–Fri 08:30–18:30**. That footer **disagrees** with N18's
  Busan-city page (**weekdays 09:00–18:00**). **Not added to the verified 20.** Re-open
  [visitbusan.net TIC](https://www.visitbusan.net/en/index.do?menuCd=DOM_000000303014001000) and
  [busan.go.kr/eng/call-center](https://www.busan.go.kr/eng/call-center) closer to the trip.

## 🟡 IRR-25 — 1366 centre *addresses* differ across official-family pages; phones agree

- MOGEF (S77, page read) and one stop.or.kr listing agree on **Seoul 02-1366** and **Busan 051-1366**
  and on the MOGEF street addresses used in N62.
- Other official-family listings (older stop.or.kr captures) have shown different Seoul (Guro) and
  Busan (Geumjeong) street addresses. **Phones are consistent. Use 1366 / 02-1366 / 051-1366**, not
  a memorized street address, if you need the centre.

## 🟡 IRR-27 — State Dept from-abroad hours: repo said 24/7; Embassy preparedness page prints weekday hours

- `index.html` and `docs/03` have long described **+1-202-501-4444** as 24/7 (from S1).
- The Embassy Emergency Preparedness page (S86, dated 20 May 2026) says callers can obtain security
  information at that number **08:00–20:00 Eastern, Monday–Friday except U.S. federal holidays**.
- These can both be true (24/7 emergency vs weekday information line) or one can be stale. **Not
  changed in the existing number table this pass.** For a U.S. citizen emergency *in Korea*, the
  unambiguous 24/7 number remains **+82-2-397-4114**. Re-read S1 before treating 202-501-4444 as
  overnight.

## 🟡 IRR-26 — Safe Korea English portal is AI-translated (the site says so)

- `eng.safekorea.go.kr` displays: "This Translation is generated by AI and may contain errors or
  inaccuracies." The **maps and the existence of an English alert feed** are still official MOIS
  services (and the U.S. Embassy names this portal). Treat English alert wording as a pointer, not
  a certified translation; confirm with 119 / 1330 / Emergency Ready if you must act.

## Status summary after the 4th pass

| ID | Issue | Status |
|---|---|---|
| IRR-9 (ICN contacts) | ICN emergency table unreachable | ✅ **Resolved this pass** — English page live (N61); L&F *hours* page still 500 |
| IRR-19 | ICN Emergency Contacts now loads | ✅ Documented (N61) |
| IRR-20 | Embassy preparedness uses stale KMA `/eng` URL | 🟡 Open — use `kma.go.kr/neng` |
| IRR-21 | NHRCK two English emails on one page | 🟡 Open — use 1331; do not pick an email |
| IRR-22 | index.html 경찴민원24 typo | ✅ Fixed this pass |
| IRR-23 | index.html Metro 6310 vs official 6311 | ✅ Aligned to N47 this pass |
| IRR-24 | Visit Busan TIC / 120-hours conflict | 🔵 Unverified — excluded from N61–N80 |
| IRR-25 | 1366 street-address drift | 🟡 Phones verified; do not memorise addresses |
| IRR-26 | Safe Korea English is AI-translated | 🟡 Documented on N70 |
| IRR-27 | 202-501-4444 hours: 24/7 vs weekday 08:00–20:00 ET | 🟡 Open — use Embassy Seoul 24/7 for in-country emergencies |

## Remaining open items (cumulative, after 4th pass)

1. **IRR-2b** — Visit Seoul still labels 1339 "Emergency Medical Information Center"; ambulance = **119**.
2. **IRR-5** — passport validity: keep "6 months" labelled as caution, not a Korean rule.
3. **IRR-12** — ICN English late-night bus page not renderable; fares direction-dependent.
4. **IRR-13 / IRR-20** — KMA `/eng/…` (and the Embassy's `web.kma.go.kr/eng` link) unmanaged; use `/neng`.
5. **IRR-16** — Seoul night-pharmacy 40-vs-38 count; call before visiting.
6. **IRR-21** — NHRCK English email conflict; use 1331.
7. **IRR-24** — Visit Busan TIC page and 120-hours conflict unverified this pass.
8. **IRR-25** — 1366 street addresses drift; use the phone number.
9. **IRR-26** — Safe Korea English is AI-translated; confirm before acting.
10. **IRR-27** — State Dept +1-202-501-4444 hours conflict; in Korea use **+82-2-397-4114**.

---

# 5th pass — 20 new entries (N81–N100), 21–22 Aug 2026

Set 5 is [`docs/18-seoul-busan-emergency-resources-set5.md`](18-seoul-busan-emergency-resources-set5.md).
Same rule: only official sources; failures stay here. New irregularities are numbered IRR-28+.

## 🔴 IRR-28 — kstay lodging report stopped 2 Nov 2025; Hi Korea still links it

- Live official portal `kstay.hikorea.go.kr` banner: **“외국인 숙박신고가 2025.11.2.부로 중단되었습니다.”**
- Infectious-disease and terror tiles both show **없음 / 숙박신고가 불필요한 단계**.
- N76 (set 4) correctly reported that Hi Korea *displays* a kstay shortcut. That shortcut is now
  **stale**. **N98** records the stop. Hotels may still photocopy a passport under other rules —
  that is not this system.

## 🟡 IRR-29 — Climate Card 30-day product dies 31 Aug 2026 (before this trip)

- SMG official Climate Card page: 30-day prepaid card **rechargeable only until 31 August 2026**.
  **Climate Pass (1 Sep 2026)** requires a **foreigner registration number** and is for **Seoul
  residents**. Short-term 1–7 day passes remain. Do not buy a 30-day Climate Card for Nov 2026.

## 🟡 IRR-30 — Embassy holiday-calendar URL 404s

- ACS page (N73) links a holiday calendar. `kr.usembassy.gov/holiday-calendar/` returned **404**
  this pass. ACS is still closed on U.S. and Korean holidays (N73); the dedicated calendar URL is
  not usable. Re-open the ACS page closer to the trip.

## 🟡 IRR-31 — Seoul English air-quality deep links 404

- The Seoul English site header shows a live **fine dust warning** and links
  `…/7-citizen-safety-tips/` and `…/air-quality-information/`. Both returned **Page Not Found**
  this pass. Keep using **AirKorea English (N55)** and **KMA `/neng`**. Do not cite the broken
  Seoul deep links as verified how-to pages.

## 🔵 IRR-32 — ICN Lost & Found hours page still HTTP 500

- `airport.kr/ap_en/1549/subview.do` failed again (same as IRR-19). Phones remain on N61 only.

## Status summary after the 5th pass

| ID | Issue | Status |
|---|---|---|
| IRR-28 | kstay stopped 2 Nov 2025; Hi Korea link stale | ✅ Documented (N98) |
| IRR-29 | Climate Card 30-day ends 31 Aug 2026 | ✅ Documented (N94) |
| IRR-30 | Embassy holiday-calendar URL 404 | 🟡 Open — use ACS page, not that URL |
| IRR-31 | Seoul English air-quality how-to pages 404 | 🟡 Open — use AirKorea / KMA |
| IRR-32 | ICN L&F hours page still 500 | 🔵 Still unverified |

## Remaining open items (cumulative, after 5th pass)

1. **IRR-2b** — Visit Seoul still labels 1339 “Emergency Medical Information Center”; ambulance = **119**.
2. **IRR-5** — passport “6 months” is caution, not a Korean rule.
3. **IRR-12** — ICN English late-night bus page; fares direction-dependent.
4. **IRR-13 / IRR-20** — KMA `/eng` unmanaged; use `/neng`.
5. **IRR-16** — Seoul night-pharmacy 40-vs-38; call first.
6. **IRR-21** — NHRCK two English emails; use 1331.
7. **IRR-24** — Visit Busan TIC / 120-hours conflict unverified.
8. **IRR-25** — 1366 street addresses drift; use the phone.
9. **IRR-26** — Safe Korea English is AI-translated.
10. **IRR-27** — +1-202-501-4444 hours; in Korea use **+82-2-397-4114**.
11. **IRR-30** — Embassy holiday-calendar URL 404.
12. **IRR-31** — Seoul English air-quality how-to pages 404.
13. **IRR-32** — ICN L&F hours page still 500.

---

# 6th pass — 20 new entries (N101–N120), 21–22 Aug 2026

Set 6 is [`docs/19-seoul-busan-emergency-resources-set6.md`](19-seoul-busan-emergency-resources-set6.md).

## 🟡 IRR-33 — Seoul Fire HQ site `fire.seoul.go.kr` HTTP 500

- Linked from the official 119.go.kr HQ directory. Fetch returned **HTTP 500**. Busan HQ
  `119.busan.go.kr` loaded (N112). Do not treat the Seoul HQ site as verified this pass.

## 🟡 IRR-34 — bikeseoul.com blocked by WAF; Ttareungi hours conflict

- Official operator site `bikeseoul.com` returned a **web-firewall block** from this environment.
- Visit Seoul page edited **13 Jul 2026** prints **+82-1599-0120 (00:00–24:00)**. An older Seoul
  official-knowledge page (seoulsolution.kr) printed **07:00–22:00**. **N115 quotes the 2026 STO
  figure** and flags the conflict. Re-open before treating the line as 24-hour staffed.

## 🟡 IRR-35 — Embassy arrest page links an older lawyers PDF than the Legal Assistance page

- Arrest page (14 Apr 2026) links `…/2025/12/List-of-Lawyers.pdf`.
- Legal Assistance page (20 Jul 2026) links `…/2026/07/List-of-Lawyers.pdf`.
- **Use the July 2026 PDF (N105).** Do not mix the two.

## Status summary after the 6th pass

| ID | Issue | Status |
|---|---|---|
| IRR-33 | Seoul Fire HQ site 500 | 🟡 Open — use 119 / 119.go.kr |
| IRR-34 | bikeseoul.com WAF; 24h vs 07:00–22:00 | 🟡 Open — N115 quotes 2026 Visit Seoul |
| IRR-35 | Two Embassy lawyer PDFs | 🟡 Use July 2026 |

## Remaining open items (cumulative, after 6th pass)

Previous 1–13 still open, plus:

14. **IRR-33** — Seoul Fire HQ website 500.
15. **IRR-34** — Ttareungi hours; confirm 1599-0120 coverage.
16. **IRR-35** — use the July 2026 lawyers PDF.

---

# 7th pass — 20 new entries (N121–N140), 21–22 Aug 2026

Set 7 is [`docs/20-seoul-busan-emergency-resources-set7.md`](20-seoul-busan-emergency-resources-set7.md).

## 🟡 IRR-36 — Visit Seoul complaints page last-edited 12 Feb 2019

- Live page still lists **02-1800-9008 Tue–Sat 09:00–18:00**. The HTML **Edited Date is 12 Feb 2019**.
- Hours may be stale. **N124 quotes the live text and flags the date.** Sunday/Monday use **1330**.
  Re-open before treating Tue–Sat as current.

## 🟡 IRR-37 — Hangang Bus times are a 1 Mar 2026 “until further notice” table

- Last-arrival figures **20:27 / 19:32** are from the March 2026 restart notice, not a November
  2026 timetable. Confirm on **hgbus.co.kr** before boarding. Water emergency remains **119**.

## 🟡 IRR-38 — FSS 1332 homepage path 404s again

- `fss.or.kr/fss/kr/main.jsp` and `fine.fss.or.kr` error pages this pass (same as set 5).
  **1332 is still not a standalone verified-hours entry.** KLAC’s referral table (N63) remains
  the only page-read mention.

## Status after the 7th pass

| ID | Issue | Status |
|---|---|---|
| IRR-36 | 1800-9008 page dated 2019 | 🟡 Quote live text; re-open |
| IRR-37 | Hangang Bus times not a Nov 2026 table | 🟡 Confirm live |
| IRR-38 | FSS 1332 site still erroring | 🔵 Still no hours |

## Remaining open items (cumulative, after 7th pass)

Previous 1–16 still open, plus IRR-36–38.

---

# 8th pass — 20 new entries (N141–N160), 21–22 Aug 2026

Set 8 is [`docs/21-seoul-busan-emergency-resources-set8.md`](21-seoul-busan-emergency-resources-set8.md).
Same rule: only official sources; failures stay here. New irregularities are numbered IRR-39+.

## 🟡 IRR-39 — tiac.or.kr hours disagree with the Visit Seoul complaints page (N124)

- Visit Seoul complaints page (N124 / IRR-36, HTML edited **12 Feb 2019**): **02-1800-9008 Tuesday–Saturday 09:00–18:00**.
- Operator site **tiac.or.kr** (opened this pass, N158): **09:00–18:00**, **closed Seollal and Chuseok**, and **phone counselling is difficult 12:00–13:00**. It does **not** print Tuesday–Saturday.
- **N158 quotes the operator site.** Sunday/Monday coverage is therefore **unsettled** between two official-family pages. Re-open both closer to the trip; **1330** remains the 24/7 fallback.

## 🟡 IRR-40 — Gimhae English contact table: displayed number ≠ `tel:` link on two rows

On the official KAC page (N141–N143):

| Row | Text on the page | `tel:` href |
|---|---|---|
| Gimhae National Quarantine Station | **+82-51-973-6525** | `051-973-1922` |
| Airport Police, International Terminal | **+82-51-974-2432** | `051-974-2403` (same as the Domestic row) |

**N142 quotes the printed numbers** and flags the links. Confirm at the desk; do not “fix” the printed figure from the href.

## 🟡 IRR-41 — ICN power-bank poster prints a nonsense mAh conversion

- Live ICN notice dated **18 May 2026**, effective **20 Apr 2026** (N156): cabin only; **≤160 Wh, max 2**; over **100 Wh** ask the airline; no charge / use / overhead bin.
- The same poster’s alt-text says **“100Wh(270,000mAh)”**. 100 Wh is about **20,000 mAh at 5 V** (or ~27,000 mAh at 3.7 V), **not 270,000 mAh**. Treat the **Wh figures and the 제한물품 table** as the rule; ignore the mAh gloss.
- A March 2025 ICN campaign (still in the search index) allowed **up to five ≤100 Wh packs**. **The 2026 notice + the live 제한물품 page win.** Confirm with the **22 Nov airline**.

## 🔵 IRR-42 — ECRM (`ecrm.police.go.kr`) still JS-thin

- Opened `https://ecrm.police.go.kr/minwon/main`. The fetch returned only the language switcher (한국어 / English / 日本語 / 中文) and a login link. **No English body, hours, or cyber-crime form was readable.** Not added.

## 🔵 IRR-43 — ICN English departure-checklist URL still redirects to the Korean intro

- `airport.kr/ap_cnt/en/dep/depche/depche.do` (search-index snippet had 02-3210-0404) **redirected to the Korean intro page** again. **Not added.** 02-3210-0404 remains on the State Dept advisory (existing number table), not as a new ICN-desk entry.

## 🟡 IRR-44 — tiac Dongdaemun desk printed “10:00–1:00”

- tiac.or.kr (N159) lists **동대문 안내소 운영시간 : 10:00~1:00**. That can be read as 13:00 or 01:00. **Not used as a verified hour.** Itaewon **10:00–19:00 / 02-3785-0942** and Gwanghwamun **10:00–19:00 / 02-735-8688** are unambiguous and are the cited desks.

## 🔵 IRR-45 — MFDS “1342 용기한걸음센터” is a menu label, not a hours page

- Several MFDS pages list **1342 용기한걸음센터(24시 마약류 전화상담)** in the nav. The URL that label pointed to this pass (`mfds.go.kr/wpge/m_1078/de010807l001.do`) is the **마약류대책협의회** greeting — **no 1342 hours, languages, or what-to-say script**. **Not added.** Medicine import remains **Narcotics@korea.kr** (N154) and the existing MFDS notice (S11).

## 🔵 IRR-46 — MOIS 긴급신고 통합 page body did not extract this pass

- `mois.go.kr/frt/sub/a06/b10/emergencycall/screen.do` opened but the fetch returned **navigation only** (no 121 / 123 / 1544-4500 merge table in the extracted text). Those utility numbers are **still not a standalone verified entry**. The 122→119 merge already on N24 / N79 is unchanged. Do not list 121 / 123 / 1544-4500 as live emergency lines.

## Status after the 8th pass

| ID | Issue | Status |
|---|---|---|
| IRR-39 | tiac 09:00–18:00 vs Visit Seoul Tue–Sat | 🟡 Quote tiac; 1330 on Sun/Mon |
| IRR-40 | Gimhae displayed vs `tel:` mismatch | 🟡 Quote printed numbers |
| IRR-41 | ICN power-bank mAh gloss + 2025 vs 2026 count | 🟡 Use 2026 Wh table; ask the airline |
| IRR-42 | ECRM JS-thin | 🔵 Still no English body |
| IRR-43 | ICN English departure page redirect | 🔵 Not added |
| IRR-44 | tiac Dongdaemun “10:00–1:00” | 🟡 Not used |
| IRR-45 | 1342 menu has no hours page | 🔵 Not added |
| IRR-46 | MOIS merge-table body not extractable | 🔵 121/123/1544-4500 still out |

## Remaining open items (cumulative, after 8th pass)

Previous 1–16 and IRR-36–38 still open, plus IRR-39–46.

---

# 9th pass — 20 new entries (N161–N180), 21–22 Aug 2026

Set 9 is [`docs/22-seoul-busan-emergency-resources-set9.md`](22-seoul-busan-emergency-resources-set9.md).
Same rule: only official sources; failures stay here. New irregularities are numbered IRR-47+.

## 🟡 IRR-47 — MFA apostille deep link `0404.go.kr/consulate/consul_apo.jsp` 404s

- Named on multiple `overseas.mofa.go.kr` apostille pages and in N151’s Embassy FAQ as the how-to.
- Live fetch returned **“요청하신 페이지를 찾을 수 없거나 서버 오류가 발생했습니다.”**
- **0404 homepage loads** (N172). **Do not add a standalone apostille-hours entry** until a live how-to page is re-opened. Phones **02-2002-0251 / 0252** remain quoted from the Embassy FAQ (N151).

## 🔵 IRR-48 — Korean Red Cross education-schedule URL errors; phones not page-read

- `redcross.or.kr/education_safety/education_safety_emergency.do?action=eduSchedule` returned an **error page**.
- Homepage loaded but the extracted body had **no Seoul/Busan branch phones or 1577-8179 hours**. Search-index snippets listed Seoul **02-2181-3104** / Busan **051-801-4036** / **1577-8179** — **not added**. Re-open a live contact page before treating those as verified.

## 🔵 IRR-49 — Hangang “금지행위(과태료)” page body is empty

- `hangang.seoul.go.kr/www/contents/646.do?mid=427` opened with the title only. Fine amounts other than the **₩50,000 illegal-parking** figure on the Nanji page (N166) are **not** in set 9.

## 🟡 IRR-50 — ICN “Consular Service Office” is Korean MFA, not the U.S. Embassy

- ICN English Departure Checklist says a lost/urgent passport can be issued at the **Consular Service Office inside the ICN passenger terminal**.
- That is the **Korean MFA** desk. **A U.S. lost passport is still Embassy Seoul only (N56/N107).** Documented as **N178** so nobody walks there with a U.S. passport.

## 🟡 IRR-51 — Humetro CHS URL is a mixed Chinese/Korean skin

- The page that loaded (`…/homepage/chs/…`) mixes Chinese chrome with the Korean emergency script. The **numbers (119 / 112 / 1544-5005 / 051-640-7447)** are in the Korean body and are what N174 quotes. Prefer the default-Korean path closer to the trip.

## 🟡 IRR-52 — Embassy voting email: SeoulINFOACS@state.gov vs older VoteSeoul@state.gov

- Live Voting page (16 Dec 2024): **SeoulINFOACS@state.gov**.
- A 2022 Embassy message still in the search index: **VoteSeoul@state.gov**.
- **N173 quotes the live page.** The 2022 address is not used.

## 🔵 IRR-53 — Safe Korea CPR how-to URL redirected to the homepage

- `safekorea.go.kr/idsiSFK/neo/sfk/cs/contents/prevent/SDIJK14739.html…` redirected to the **국민안전24** main. AED **how-to steps** are therefore **not** a standalone entry. The **AED map layer** is named on the live 생활안전 map (N176).

## 🟡 IRR-55 — Gwangnaru AED count: English SMG page 1 vs Korean dashboard 3

- N144 (SMG English Hangang Parks): **AED (1)**.
- N167 (hangang.seoul.go.kr dashboard): **자동심장충격기 (3), 부분운영**.
- **N167 quotes the Korean operator dashboard** and flags the English page. Do not memorise either count; call **119**.

## Status after the 9th pass

| ID | Issue | Status |
|---|---|---|
| IRR-47 | 0404 apostille how-to 404 | 🔵 No standalone hours |
| IRR-48 | Red Cross contact page error | 🔵 Not added |
| IRR-49 | Hangang fine-schedule page empty | 🔵 Only ₩50,000 parking is quoted |
| IRR-50 | ICN consular desk ≠ U.S. Embassy | ✅ Documented (N178) |
| IRR-51 | Humetro CHS mixed-language skin | 🟡 Numbers from Korean body |
| IRR-52 | Two Embassy voting emails | 🟡 Use SeoulINFOACS@state.gov |
| IRR-53 | Safe Korea CPR URL redirect | 🔵 How-to not added |
| IRR-55 | Gwangnaru AED 1 vs 3 | 🟡 Quote Korean dashboard |

## Remaining open items (cumulative, after 9th pass)

Previous 1–16, IRR-36–46 still open, plus IRR-47–53 and IRR-55. (IRR-54 unused.)
