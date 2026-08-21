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

**Action taken:** I did **not** rewrite the itinerary files, because changing 380 lines of day plan
silently would bury the discrepancy. I have flagged it here and corrected the trip-window framing in
the new files. **Decision needed from you:** confirm the Seoul/Busan/Seoul split and I will rebuild
`docs/10-itinerary-day-plan.md` around it in one pass.

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

## 🟡 IRR-6 — "Currency on entry and exit: no declaration needed" vs the repo's USD 10,000 rule

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
| "No Korean national public holidays 1–22 Nov 2026" (S9) | **Unverified this pass** — the VISITKOREA holiday URL returned a 400 error. The claim is plausible (no statutory ROK holiday falls in that window in a normal year) but it is stated as fact in five files on one unreachable source. Re-check before departure. |
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

## Recommended next actions

1. **Confirm the itinerary** (IRR-1) so `docs/10` can be rebuilt for Seoul→Busan→Seoul with CSAT
   placed in Seoul.
2. **Re-check the holiday claim** (IRR-9) on a working VISITKOREA/government calendar page.
3. **Resolve the currency-declaration conflict** (IRR-6) against Korea Customs Service directly.
4. Update `docs/sources.md` KMA links to `kma.go.kr/neng` (done in the register as S18).

*Reviewed 21 Aug 2026. No claim in this file is asserted without a link that was opened, or an
explicit "unverified" label.*
