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
