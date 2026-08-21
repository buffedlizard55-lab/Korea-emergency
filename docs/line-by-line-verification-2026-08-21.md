# Line-by-line verification pass — 21 Aug 2026

Purpose: reduce unsupported or over-specific claims in the repo and keep only facts that are supported by official/trusted sources or clearly labeled as planning advice.

Scope reviewed line by line:
- Root landing files: `README.md`, `index.html`, `assets/site.css`
- Checklists: all files in `checklists/`
- Docs: all files in `docs/`
- Printable files: `print/emergency-card.html`, `print/emergency-card.pdf`

## Official/trusted sources used

See `docs/sources.md` for source IDs S1–S17. The review relied on official or trusted primary sources for critical claims:

- U.S. State Department / Travel.State.gov for advisory level, visa duration, emergency numbers, embassy emergency number, passport validity, Busan no-consular-services warning, and security guidance.
- U.S. Embassy Korea for Busan no-consular-services wording and medication guidance.
- Korea.net / official ROK website for 1330 Korea Travel Hotline 24-hour service.
- CDC Travelers' Health for vaccine and travel-health recommendations.
- Korean e-Arrival Card official portal for filing window, free cost, and 72-hour validity.
- K-ETA official portal / State Department for U.S. K-ETA exemption through 31 Dec 2026.
- VISITKOREA / Korea Tourism Organization for 2026 public holidays.
- KICE for CSAT schedule and 2027 CSAT date materials.
- KMA / Weather Nuri and AirKorea for weather/air-quality recheck instructions.
- Incheon Airport and AREX for airport transport/timetable recheck instructions.
- ROK Ministry of Foreign Affairs for currency/customs guidance.
- U.S. Trade.gov legacy electric-current table for Korea electrical-current information.

## Claims corrected or downgraded

The following items were changed because they were too exact, stale, or unsupported by the official source available in this review:

1. **e-Arrival Card timing** — changed “old fixed 72-hour submission” wording to “submit during the official pre-arrival window.” The official guide says filing starts 3 days before arrival based on Korea Standard Time and validity is lost 72 hours after submission. This avoids accidentally telling travelers to submit too early.
2. **CSAT English wording** — changed “old full-session listening wording” to “English 13:10–14:20; listening starts at 13:10.” KICE says English is 13:10–14:20 and the listening test starts at 13:10 for about 25 minutes.
3. **CSAT traffic/flight claims** — removed exact claims about flight holds, road radii, universal office opening times, and fixed morning traffic rules. The repo now says to check dated local/airport/airline notices.
4. **Busan Consulate phone** — removed the unverified the old Busan phone number listing. The official Embassy page confirms Busan has no consular services and says after-hours emergency services go through Embassy Seoul.
5. **Embassy email** — removed “old emergency-email wording” wording. The emergency channel is now stated as the 24/7 phone number; non-emergency contact options should be checked on the current Embassy website.
6. **Static hospital lists** — removed named hospital lists from the emergency flow. The guide now directs travelers to 119, 1330, hotel staff, or current local sources for the nearest appropriate facility.
7. **Static AREX/KTX times** — removed or softened exact rail travel/last-train times. Travelers are directed to AREX/Korail/LetsKorail for current schedules and fares.
8. **Weather averages** — removed fixed temperature averages and unsupported city comparison claims. The guide now points to KMA forecasts and AirKorea checks.
9. **COVID / entry-health statement** — removed “no COVID entry requirement currently” from the repository and changed it to re-check official entry-health screening rules.
10. **Power/electrical claim** — added a trusted source for 220/380V and 60Hz, and changed plug wording to advise checking the hotel outlet type and device labels.
11. **Currency declaration** — added ROK Ministry of Foreign Affairs source for the “over USD 10,000” declaration rule.
12. **Internal/source-register stale text** — updated source references from previous source range to S1–S17 and removed stale internal branch/commit clutter.

## Ten-pass audit result

The automated audit was run **10 consecutive times** after cleanup. Every pass returned 10/10 checks passing.

Checks in each pass:

1. File inventory and line count.
2. Relative Markdown/HTML link target check.
3. Source-ID consistency: every referenced `S#` exists in `docs/sources.md`.
4. Trip weekday/date consistency using Python `datetime`.
5. High-risk stale-phrase scan for removed exact claims.
6. Official/trusted source-domain coverage in `docs/sources.md`.
7. HTML parse check using Python stdlib parser.
8. Printable PDF stale-string scan.
9. Whitespace/internal stale-string scan.
10. Disclaimer and re-verification language check.

Final audit output summary:

```text
PASS: 1 file inventory — 25 text/html/css files checked; 2720 lines
PASS: 2 relative links — no broken local Markdown/HTML targets
PASS: 3 source IDs — all referenced source IDs defined: S1-S17
PASS: 4 date weekdays — 31 Oct Sat, 1 Nov Sun, 19 Nov Thu, 22 Nov Sun verified by datetime
PASS: 5 stale/high-risk phrase scan — no stale exact transport/CSAT/email/Busan-phone phrases found
PASS: 6 official/trusted source coverage — major claim domains present in sources.md
PASS: 7 HTML parse — HTML files parse with stdlib parser
PASS: 8 printable PDF stale scan — no stale e-Arrival/Busan-phone/listening-session strings in PDF
PASS: 9 whitespace/internal stale — no trailing spaces and no stale arena branch/commit strings
PASS: 10 disclaimer/reverify labeling — disclaimer and re-verification language present
```

## Remaining conservative limits

This review reduces hallucination risk; it does not make future facts permanent. Anything date-sensitive still must be rechecked near departure: K-ETA/e-Arrival rules, entry-health screening, CSAT-day traffic/flight notices, airport and rail schedules, taxi fare rules, weather, air quality, and medication import procedures.
