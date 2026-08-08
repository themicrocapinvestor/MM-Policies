---
layout: default
title: Methodology
---

# Methodology

*Last updated: 9 August 2026*

How **The Microcap Minute Global** decides what appears in an issue, written out so a
reader can check the work rather than take it on trust.

There are two steps and **only one of them is mechanical.** That distinction runs through
everything below, so it is worth stating first: the tests applied to a company are fixed
and repeatable, and the choice of what goes into those tests is a human reading of a chart.

---

## What is being measured

One thing: **how a sector, a fund or a company is moving against the S&P 500.**

Not whether it is cheap. Not whether the business is good. Not what it will do next. A
company can appear in an issue while losing money, and several have.

Everything else in an issue, the margins, the returns on capital, the growth, is reported
so a reader can judge the business for themselves. It plays no part in selection.

## Three layers

An issue works downward: the eleven US sectors, then the industry funds inside them, then
the companies.

### 1. Sectors

Every week we read a Relative Rotation Graph of the **eleven Select Sector SPDR funds**
against the S&P 500, on charts from StockCharts.com.

#### How a rotation graph is read

A rotation graph places two measurements on one picture.

**Across** is strength against the benchmark. **Up** is whether that strength is building
or fading. Both are centred on 100, which means behaving exactly like the index. So the
picture divides into four:

| | strength building | strength fading |
|---|---|---|
| **stronger than the index** | Leading | Weakening |
| **weaker than the index** | Improving | Lagging |

Things tend to travel clockwise through those four over time, though nothing obliges them
to, and plenty stall or reverse halfway.

**A tail is the path over recent weeks, and the arrowhead is the only thing telling you
which end is now.** Without it a tail is ambiguous in both directions, and reading one
backwards turns a name rotating out of Leading into an apparent leader.

Four principles, each learned by getting it wrong first:

- **Direction beats position.** A name sitting in Leading with its tail turning down is
  rotating out of it, not leading. The quadrant label alone is not the signal.
- **Distance from the centre is not quality.** For something on the weak side, a bigger
  gap mostly means it sits further left, which is further from Leading, not better. Sorting
  by how far a thing has travelled rewards the wrong thing.
- **A short tail says nothing.** Something sitting near the centre is behaving like the
  index, and length is what separates a real rotation from noise.
- **The benchmark must be the same everywhere.** Measured against a sector fund instead of
  the index, the same companies on the same day can read Leading or Weakening. Every graph
  we read is against the S&P 500, without exception.

**It is a screener, not a timing tool.** It says where attention is going, not when to act,
and nothing in an issue is an instruction to do anything.

#### The rule we read it by

> On every ticker we look for a long tail. Trajectory matters more than position, so we
> favour names moving north east, in the Leading or Improving quadrant.

**A name already leading but turning down is not a candidate.** That exclusion matters as
much as the rule itself.

### 2. Industry funds

Beneath the sectors sit **thirty two industry funds**, each holding one line of business:
semiconductors, regional banks, biotechnology, airlines, gold miners and so on.

They are read the same way, on the same graph, against the same benchmark. **They are
judged on their own record, not on whether the sector containing them was chosen**, because
a line of business can gain ground while the sector around it loses it.

Up to nine appear in an issue. Every one is then put through the same ten tests the
companies face.

**No company in an issue is taken from these funds.** They are a reading in their own
right, not a route to a name.

### 3. Companies

Inside each chosen sector we read the graph again on the companies themselves, and note
the ones turning up against the index.

Only companies that already pass the ten tests below are plotted, so the chart carries
around twenty readable names rather than eighty that could not be used anyway.

The names that survive are then sorted into the businesses they are actually in, and **the
strongest of each is kept**. Without that step a list can run five regional banks and three
laboratory companies, which is one story told eight times rather than eight companies.

---

## The ten tests

Every company and every fund must clear all ten. No score, no weighting, no exceptions.

```python
keep = all([
    price       >  ma_50,             # above the 50 day average
    ma_50       >  ma_150,            # the 50 above the 150
    ma_150      >  ma_200,            # the 150 above the 200
    rsi_weekly  >= 50,
    rsi_monthly >= 50,
    rsi_daily   <= 85,                # not already overbought
    price       >= low_52w  * 1.25,   # 25% off the one year low
    price       >= high_52w * 0.85,   # within 15% of the high
    change_3m - spy_3m > 0,           # ahead of the S&P 500
    dollar_volume >= 10_000_000,      # $10m a day
])
```

Given the same figures these return the same answer every time. **The same threshold
applies to a fund as to a company**, including the liquidity bar, which has kept funds out
of issues.

Each issue also reports the stage of a chart in Stan Weinstein's sense: Stage 1 a base,
Stage 2 an advance, Stage 3 a top, Stage 4 a decline. It is worked out from how far price
sits above each moving average. **A stage says where a chart is, not what to do about it.**

## What is judgement, and what is not

| Step | |
|---|---|
| Reading the graphs, choosing sectors, funds and candidate companies | **judgement**, by eye |
| The ten tests | mechanical |
| Grouping by business and keeping the strongest of each | mechanical |
| Every figure reported | taken from the data, not chosen |

Another reader looking at the same graphs could reasonably reach a different list. That is
a property of the method, not a defect in it, and it is why nothing here is presented as a
rule that produces a right answer.

## What we deliberately do not use

All of these are available in the data and none of them appears in an issue:

- **Analyst ratings, price targets and target upside**
- **Every forward estimate**, including next quarter revenue and earnings growth. A PEG
  ratio is suppressed for the same reason when a company has no trailing P/E, because the
  published one is built on forecasts
- **Any score, whether ours or anyone else's.** No conviction measure, no ranking, and no
  third-party quality scores such as Piotroski or Altman Z, all of which are in the data.
  The shortlist is the output of tests, not a rating, and a nine point quality score
  printed beside that claim invites a reader to treat it as one. The companies are not
  ordered by preference

The next scheduled results date is printed, because a date is a fact rather than a forecast.

## Sources

**StockCharts.com** provides the Relative Rotation Graphs. They are read there on a paid
subscription, captured by hand, and reproduced under their [reprint permission policy](https://help.stockcharts.com/learning-more/policies-and-limitations/reprint-permission-policies).

**StockAnalysis.com** provides every figure we print. Two exports are downloaded by hand
each week, one covering US stocks and one covering funds.

**Nothing is read out of a chart into our text, tables or cards.** The graphs decide what
we look at, not what we print about it.

## Known limits

Stated plainly, because a method described without them is a sales pitch.

- **The thresholds are chosen, not proven.** Twenty five per cent above the one year low,
  fifteen per cent below the high, ten million dollars a day: each is a judgement about
  what counts as an advance rather than a bounce. None has been validated against a future.
- **Relative strength describes what has already happened.** It is not a forecast and does
  not predict returns.
- **Reading a graph by eye is fallible**, most of all near the diagonals where a tail's
  direction is genuinely hard to call.
- **One data provider, unverified.** Figures are not checked against companies' own
  filings, and an error upstream carries straight into an issue.
- **A chart is a moment.** Everything in an issue can be undone by a single earnings
  report, which is why the next results date is printed beside each company.

---

**Relative Rotation Graph** and **RRG** are registered trademarks of RRG Research, used
with permission. The graphs are published by StockCharts.com and are read there on a paid
subscription. Neither is affiliated with this publication and neither has reviewed or
endorsed anything in it.

The full [Disclaimer](disclaimer.html) applies to every issue.
