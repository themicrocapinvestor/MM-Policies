---
layout: default
title: Filings Search
---

# Filings Search

*Last updated: 11 August 2026*

The Filings Search page is an index of every SEC filing that matters for S&P 500
companies over the last forty five days, with annual reports kept for ninety
days. Each filing carries topic chips, and a text filter narrows the list.
Everything on it is read from public regulatory filings. The page itself is
**[here](https://tracker.themicrocapminute.in/search/)**,
free, and updated every morning.

## Read this part first

**An announcement is not a recommendation.** Nothing on the page is a
suggestion to buy or sell anything. This page tells you what was filed. It
never tells you why, and the why is the part that matters.

**The chips and the text filter group filings by type. They do not judge
importance.** A bankruptcy notice and a routine earnings release can sit side
by side because both were filed. That a filing matches a filter means it is of
that type, nothing more.

**The index covers only filings that name an S&P 500 company.** Events at
smaller companies are absent by design. A small company can sign a big
agreement or change its auditor and produce a perfectly real filing that never
appears here, because the company is not in the index.

## How the index is built

The universe is the S&P 500 as published in the publisher's own data export, a
fixed snapshot rather than a live scrape. Each morning, an automated process
searches the SEC's full-text filing search for the forms listed below over the
previous few days and keeps any filing that names an S&P 500 company. The page
holds the last forty five days; annual reports stay relevant longer and are
kept for ninety days.

The topic of a filing is read from fields the filer itself sets, never guessed
from the text. For 8-K filings, the chip comes from the item numbers the filer
reports:

- Item 2.02: results
- Item 5.02: management changes
- Item 1.01: big agreements
- Item 1.02: agreements ended
- Item 2.01: deals completed
- Items 2.05 and 2.06: costs and impairments
- Items 1.03 and 2.04: bankruptcy and defaults
- Item 3.01: delisting notices
- Items 4.01 and 4.02: auditor changes
- Item 7.01: Regulation FD disclosures
- Item 8.01: other events

For other filings, the chip comes from the form type itself: tender offers
(SC TO), large stakes (Schedule 13D), going-private filings (SC 13E3), merger
vote materials (DEFM14A and PREM14A), offerings (424B5), annual reports
(10-K), and quarterly reports (10-Q).

The process is mechanical: the same filings on the same morning produce the
same index. No filing is added or removed by judgement, and no company named
on the page is contacted or aware of its inclusion.

The inside-text search deserves its own explanation. Each morning the system
also reads the text of that window's 8-K filings, press-release exhibits
included, breaks every document into words, and builds one word-to-filing
index alongside the page. When a reader searches, the page first asks our own
hosted search service, which keeps a copy of that filings text database on our
own server (sit-filing-search.onrender.com) and answers from it; this has
nothing to do with SEC servers. If that service cannot be reached, the page
falls back to downloading the static index a single time and running the
search on the reader's own device. Either way, a reader's searches never touch
SEC servers, and the index contains no opinions, only words and the filings
they appeared in. The annual and quarterly reports are huge reference
documents and are linked for reading, not searched. The shortcut to the SEC's
own full-text search is different in kind: it opens sec.gov in a new tab like
any normal visit, and it covers every US filer, not just the S&P 500.

## Sources

The filings are public records published by the **United States Securities and
Exchange Commission** on EDGAR and are free for anyone to read. The index is
built with the SEC's full-text search, which is free for anyone to use, and
anyone can pull the same documents from EDGAR and check our reading against
the originals.

The SEC is not affiliated with us in any way, and nothing here is published
with its knowledge or approval. No company named on the page has any
connection to this publication. The SEC's own rules on reusing what it
publishes, and how we follow them, are set out in
[SEC Data and Public Filings](sec-data.html).

## And the usual, because it applies here too

This publication is impersonal commentary of general and regular circulation.
It is not investment advice, it is not a recommendation to buy or sell any
security, and it is not tailored to any person or their circumstances. Please
read the full [Disclaimer](disclaimer.html) before relying on anything here.

Questions are welcome at
[hello@themicrocapminute.in](mailto:hello@themicrocapminute.in).
