# Insider + Congress Overlap Scan — 30 names (2026-07-01)

**Thesis under test:** "insider buying AND congressional buying in the same name = a signal worth a case
file." Ranked best-to-worst by the strength of the signal we could actually verify.

## What we can and cannot verify
- **Insider side: VERIFIED.** Pulled live SEC EDGAR Form 4 data per ticker (open-market buys code P vs
  sells, distinct buyers/sellers, dollar value, cluster-buy flag), 120-day window (back to ~2026-03-03).
- **Congress side: NOT verified by us.** Atlas has no congressional-trade feed (Quiver / Capitol Trades)
  wired in. The congress tiers below are taken as-given from the source list, and flagged as unverified.
- **Caveats:** the 120-day window misses older claims (e.g. an INTC Jan-2026 CFO buy). "0 txns" for the
  mega-caps means our EDGAR parse found no Form 4s in the window; for very large filers that may be a
  parse/window gap rather than true zero, so read those as "no signal found," not "proven zero." Positive
  data (recorded buys/sells) is reliable; absence is weaker.

## The headline finding
The thesis washes out almost completely on the insider side, which is itself the result. Of 30 names,
**exactly one (WD) has a confirmed insider cluster buy**, and the two names claimed as the real
insider+congress intersection (UNH, PLTR) show insider **selling**, not buying, in our data. The overlap
thesis, as a stock-picking edge, is not supported here.

## Verified data (EDGAR Form 4, last 120 days)

| Ticker | Price | Mkt cap | Cluster buy | Insider buys | Insider sells | Read |
|---|---|---|---|---|---|---|
| WD | $54.70 | $1.9B | **YES** | 3 buyers, ~$315k (Freedman/Dir $246k, Schmaltz/Dir $46k) | 0 | **Confirmed buy signal** |
| UNH | $415.63 | $377B | no | 0 | 1 seller, $284k | Claimed cluster buy NOT found; net selling |
| PLTR | $116.67 | $268B | no | 0 | 9 sellers, **$425M** | Claimed Karp buy is backwards; heavy selling (Karp is a structural seller) |
| INTC | $139.63 | $702B | no | 0 | 1 seller, $2.5M | Recent selling; claimed Jan CFO buy is outside our window |
| TSM,NVDA,MSFT,AAPL,AMZN,GOOGL,META,NFLX,AMD,UBER,ABT,IREN,RDDT | (various, all liquid) | large | no | 0 | 0 | No Form 4 signal found in window |
| SMPL,LGIH,HY,DNUT,CBRL,VVV,MSA,LPX,AMER,SLS,IBRX,FCFS | (various) | small/mid | no | 0 | 0 | No signal |
| GNPX | $0.52 | ~$0.85M | no | 0 | tiny (2 director sells, 8 & 10 sh) | Confirmed NO insider buying (documented negative) |

## Ranked best-to-worst (by verified signal, not by company quality)

### A. Verified insider signal (act/research first)
1. **WD (Walker & Dunlop)** — the only name with a confirmed insider **cluster buy**: 3 directors, ~$315k,
   led by Freedman ($246k). Real, recent, multi-insider, code-P. This is the single best data-backed
   candidate on the list. (No congressional claim attached, so it is a strong *insider* signal, not a
   verified overlap.)

### B. Congress-interest, insider-quiet quality names (watch; overlap unconfirmed)
These have strong congressional interest per the source and NO insider selling in our window; the insider
half of the thesis is simply unconfirmed, not contradicted. Ordered by congress-heaviness + liquidity.
2. **TSM** — most-bought congressional name per the list; huge, liquid, quality. No insider signal.
3. **NVDA** · 4. **MSFT** · 5. **AAPL** · 6. **GOOGL** · 7. **AMZN** · 8. **META** — mega-cap congress
   favorites, no Form 4 signal. Fine businesses; the overlap edge is absent.
9. **AMD** · 10. **NFLX** · 11. **UBER** · 12. **ABT** — congress/insider-watch names, no signal our side.
13. **IREN** · 14. **RDDT** — smaller, more speculative congress/insider-watch names, no signal.

### C. Claimed insider buy, but our data shows the opposite (thesis contradicted)
15. **UNH** — the marquee "real overlap." Our data does NOT show the claimed 10-director Apr-1 cluster buy
    (which should be inside the window); it shows a director **sell**. Elite business, but the specific
    signal that put it in Tier 1 does not verify. **Downgraded.**
16. **PLTR** — the other marquee. Claimed Karp ~1.47M buy; our data shows **$425M of insider selling**
    across 9 sellers. Karp sells on a schedule (10b5-1), so this is noise rather than a bearish tell, but
    the "insider *buy*" premise is wrong. **Downgraded.**
17. **INTC** — recent insider **selling** ($2.5M); the claimed Jan-2026 CFO code-P buy predates our
    window, so it is neither confirmed nor denied here. Verify the Jan filing directly.

### D. Thin / speculative, no signal (verify individually or drop)
18. **FCFS** · 19. **MSA** · 20. **LPX** · 21. **VVV** — McCaul-style single-member congress buys, real
    businesses, no insider signal.
22. **LGIH** · 23. **SMPL** · 24. **CBRL** · 25. **DNUT** · 26. **HY** — single-member congress / beaten-down
    names, no insider signal, several distressed (DNUT $3.53, HY $0.62B cap).
27. **IBRX** · 28. **SLS** — speculative small-cap biotech, no signal.
29. **AMER** — micro-cap rare earths, high insider ownership but no recent open-market buy in our data.
30. **GNPX (Genprex)** — the documented negative. Confirmed **no** insider buying (only 2 token director
    sells), ~$0.85M market cap, down ~99% off its high. Congress-buy claim only. Already has a full Atlas
    engine case file (`/casefile?ticker=GNPX`): a binary clinical/cash-runway bet, engine confidence 0.4.

## Bottom line
- **If you act on one thing from this list, it is WD** — the only confirmed insider cluster buy.
- **The "insider + congress overlap = edge" thesis is not supported** by the verifiable half. The two
  names it rested on (UNH, PLTR) show insider *selling*. Log that as the finding: this particular overlap
  screen, as run, did not surface a real edge beyond WD.
- **Congress-only names (Tier B)** may still be worth case files as quality watch-list ideas, but not
  because of an insider overlap that does not exist.
- To make the *congress* half first-class, Atlas would need a congressional-trade feed (Quiver / Capitol
  Trades) ingested as evidence. Until then, this scan can only ever verify the insider leg.

*Method: SEC EDGAR Form 4 via Atlas `insiders.ts`, live FMP quotes, 120-day window, run 2026-07-01.
Congress tiers are from the source list and unverified by Atlas.*
