# BestStock Investment Skill Project

BestStock is an investment-skill project for value investing research. Its purpose is to distill the wisdom left by classic investment masters into a highly complete, executable, and reusable investment analysis skill; the generation process primarily uses GPT-5.5 xhigh mode.

The project is not designed to replace human judgment. Its intended system is human-led and screening-assisted: use public stock market interfaces and annual report data to quickly identify companies worth attention, then use the skill to examine those companies deeply from the perspectives of great investors.

## Vision

This project serves two related goals:

1. Company screening: use public market data, financial data, annual reports, and structured investment frameworks to narrow a large universe of companies into a smaller watchlist.
2. Judgment training: help users internalize value investing principles by reading and using skills distilled from primary investment materials.

The final system should behave as an investment research assistant, not an investment decision machine. It should expand the user's field of view, improve research efficiency, provide better questions, and expose risk blind spots. Final investment judgment remains human.

## Current Progress

The original source-material collection stage has been completed. The project is currently producing the first batch of initial skills, driven primarily by GPT-5.5 xhigh, to extract early-stage methodology from the organized source materials. Each close-reading batch keeps the requested page range at around 35 pages to maintain output quality.

## Core Idea

The core method is: read completely first, then compress into methodology.

To help the generation process, which primarily uses GPT-5.5 xhigh mode, understand the original materials accurately, the source documents are split into smaller batches. Most long-form materials are divided into groups of about 35 pages. Some materials are split by their original structure, year, meeting session, or shorter page ranges, such as Berkshire annual letters, Berkshire annual meeting morning and afternoon sessions, and a few 25-page groups.

Each batch follows these principles:

1. The model must fully read the source material instead of summarizing fragments.
2. The model should compress only after full understanding.
3. The output should be a Chinese skill, preserving key judgment standards, checklists, counterexamples, boundaries, and risk reminders.
4. The first pass creates local skills from each source batch.
5. The second pass merges multiple local skills, preserving differences while removing duplication.
6. The final result can become one comprehensive investment skill, or several specialized skills by topic, source, or analysis stage.

## Expected Capabilities

The finished investment skill is expected to support:

- Company screening: filter companies by fundamentals, valuation, earnings quality, asset quality, return on capital, and other public data.
- Annual report reading: analyze business model, moat, financial quality, management behavior, capital allocation, and disclosed risks.
- Master-investor analysis: integrate frameworks from Benjamin Graham, Warren Buffett, Charlie Munger, Philip Fisher, Peter Lynch, Joel Greenblatt, Howard Marks, Seth Klarman, Nick Sleep, and others.
- Risk detection: identify leverage, cyclicality, incentive problems, excessive valuation, poor accounting quality, industry change, and weakening competition.
- Valuation and margin of safety: build discipline around conservative assumptions, long-term cash flows, reinvestment ability, return on capital, and market psychology.
- Investment memos: produce structured research conclusions with bullish arguments, bearish arguments, key variables, tracking indicators, and buy-condition assumptions.

## Workflow

The project can proceed through the following workflow:

1. Organize source materials  
   Place classic investment materials under `origindata/`, grouped by source, author, book title, or year.

2. Read by batch and distill  
   Use prompts that emphasize "read completely before compression" so the model first understands each source batch, then extracts methods, standards, and insights.

3. Generate local skills  
   Create local skills by book, shareholder letter, meeting transcript, memo collection, or fund letter collection.

4. Merge multiple skills  
   Merge local skills by removing repeated ideas, preserving source-specific insights, deleting vague summaries, and increasing methodological density.

5. Apply to company research  
   Feed public stock data and annual report data into the skill. First screen companies in bulk, then conduct deeper research on shortlisted candidates.

6. Human review and decision  
   The user remains responsible for understanding the business, checking facts, reviewing assumptions, identifying model omissions, and making the final decision.

## Project Structure

```text
BestStock/
├── README.md
├── readme-en.md
└── origindata/
    ├── _AIPrompt模板.txt
    ├── 伯克希尔股东大会全集-巴菲特、芒格(Berkshire Annual Meeting Transcripts - Buffett and Munger)/
    ├── 巴菲特股东信全集-伯克希尔官网(Berkshire Hathaway Shareholder Letters - Official Berkshire Website)/
    ├── 证券分析-本杰明·格雷厄姆(Security Analysis - Benjamin Graham)/
    ├── 聪明的投资者-格雷厄姆(The Intelligent Investor - Benjamin Graham)/
    ├── 穷查理宝典-芒格(Poor Charlie's Almanack - Charlie Munger)/
    ├── 怎样选择成长股-费雪(Common Stocks and Uncommon Profits - Philip Fisher)/
    ├── 彼得·林奇的成功投资-彼得·林奇(One Up On Wall Street - Peter Lynch)/
    ├── 战胜华尔街-彼得·林奇(Beating the Street - Peter Lynch)/
    ├── 股市稳赚-乔尔·格林布拉特(The Little Book That Still Beats the Market - Joel Greenblatt)/
    ├── 股市天才：发现股市利润的秘密隐藏之地-乔尔·格林布拉特(You Can Be a Stock Market Genius - Joel Greenblatt)/
    ├── 安全边际：有思想投资者规避风险的价值投资策略-塞思·卡拉曼(Margin of Safety - Seth Klarman)/
    ├── 橡树资本备忘录全集-霍华德·马克斯(Oaktree Capital Memos - Howard Marks)/
    ├── 游牧人基金信函全集-尼克·斯利普、凯伊斯·扎卡里亚(Nomad Investment Partnership Letters - Nick Sleep and Qais Zakaria)/
    ├── 利息理论-费雪(The Theory of Interest - Irving Fisher)/
    ├── 巴菲特关于过去、现在和未来的特别来信 2014-伯克希尔官网.pdf.pdf
    └── 查理关于过去、现在和未来的特别来信 2014-伯克希尔官网.pdf
```

Note: source folders in `origindata/` now keep the original Chinese title and append an English translation in parentheses.

## Source Folder Table For `origindata/`

`origindata/` is the most important source-material directory in this project. It currently contains 397 files: 222 PDF files, 149 Markdown files, and 26 TXT files.

| Source folder or file | File count | Purpose |
| --- | ---: | --- |
| 伯克希尔股东大会全集-巴菲特、芒格(Berkshire Annual Meeting Transcripts - Buffett and Munger) | 149 | Extract practical business analysis, capital allocation, market psychology, and long-term investing principles from Berkshire Q&A sessions. |
| 巴菲特股东信全集-伯克希尔官网(Berkshire Hathaway Shareholder Letters - Official Berkshire Website) | 55 | Distill Buffett's annual operating, capital allocation, ownership, and business-quality principles. |
| 橡树资本备忘录全集-霍华德·马克斯(Oaktree Capital Memos - Howard Marks) | 47 | Build frameworks for cycles, risk control, second-level thinking, market psychology, and defensive investing. |
| 利息理论-费雪(The Theory of Interest - Irving Fisher) | 25 | Support deeper thinking about discount rates, time value, capital, and interest-rate logic. |
| 证券分析-本杰明·格雷厄姆(Security Analysis - Benjamin Graham) | 24 | Build a rigorous foundation for balance-sheet analysis, earning power, asset value, and margin of safety. |
| 聪明的投资者-格雷厄姆(The Intelligent Investor - Benjamin Graham) | 19 | Extract investor temperament, defensive investing, Mr. Market, and safety-first principles. |
| 穷查理宝典-芒格(Poor Charlie's Almanack - Charlie Munger) | 18 | Capture multidisciplinary thinking, incentives, mental models, and judgment discipline. |
| 彼得·林奇的成功投资-彼得·林奇(One Up On Wall Street - Peter Lynch) | 10 | Develop practical company observation, growth classification, and individual-investor research methods. |
| 怎样选择成长股-费雪(Common Stocks and Uncommon Profits - Philip Fisher) | 10 | Extract scuttlebutt research, qualitative business quality, management evaluation, and long-term growth principles. |
| 战胜华尔街-彼得·林奇(Beating the Street - Peter Lynch) | 10 | Add portfolio examples, company categorization, and applied stock-picking discipline. |
| 股市天才：发现股市利润的秘密隐藏之地-乔尔·格林布拉特(You Can Be a Stock Market Genius - Joel Greenblatt) | 9 | Study special situations, spin-offs, restructurings, and market inefficiencies. |
| 游牧人基金信函全集-尼克·斯利普、凯伊斯·扎卡里亚(Nomad Investment Partnership Letters - Nick Sleep and Qais Zakaria) | 7 | Learn scale economies shared, long-duration compounding, business culture, and patient ownership. |
| 股市稳赚-乔尔·格林布拉特(The Little Book That Still Beats the Market - Joel Greenblatt) | 6 | Extract simple quantitative ranking logic around quality and cheapness. |
| 安全边际：有思想投资者规避风险的价值投资策略-塞思·卡拉曼(Margin of Safety - Seth Klarman) | 5 | Build downside-first thinking, risk avoidance, market inefficiency, and value-investing discipline. |
| Warren Buffett's 2014 Special Letter on the Past, Present, and Future | 1 | Provide Buffett's long-term reflection on Berkshire, ownership, and institutional design. |
| Charlie Munger's 2014 Special Letter on the Past, Present, and Future | 1 | Provide Munger's complementary view of Berkshire's system, culture, and decision architecture. |
| AI Prompt Template | 1 | Records the project's prompting pattern for complete reading, compression, and skill generation. |

## Source Material Categories

1. Classic value investing books  
   The source library includes *Security Analysis*, *The Intelligent Investor*, *Margin of Safety*, *Poor Charlie's Almanack*, *Common Stocks and Uncommon Profits*, *One Up On Wall Street*, *Beating the Street*, *The Little Book That Still Beats the Market*, *You Can Be a Stock Market Genius*, and *The Theory of Interest*. Most of these files are split by page range, such as `001-035.pdf` and `036-070.pdf`.

2. Buffett and Berkshire materials  
   This group includes Berkshire shareholder letters, Berkshire annual meeting transcripts, and the 2014 special letters by Warren Buffett and Charlie Munger. The shareholder letters cover early combined files and annual materials through 2024. The annual meeting transcripts are split by year and by session, making them easier to read, compress, and merge.

3. Modern value investing and cycle-thinking materials  
   This group includes Oaktree memos and Nomad Investment Partnership letters. These sources are useful for risk control, cycle judgment, long-term ownership, business quality, and contrarian thinking.

4. Prompt template  
   `_AIPrompt模板.txt` captures the project's prompt pattern. Its central requirement is to analyze the referenced files completely, distill company-analysis methods and core investment ideas, and compress them into methodology only after full reading.

## Usage Suggestions

When generating a skill, each run should clearly state:

- Which source files are being used.
- The model must read completely before compression.
- The output should be executable methodology, not a generic book summary.
- The author's distinct ideas should be preserved, along with conditions, limitations, and counterexamples.
- When merging skills, remove duplication, preserve source-specific insights, and keep key risk lists.

For company research, use a two-stage process:

1. Screening stage: use data interfaces to identify companies worth further study.
2. Deep research stage: use the comprehensive skill to read annual reports, analyze the business model, evaluate valuation and risk, and produce an investment memo.

## Notes

This project is for investment research, learning, and methodology building only. It is not investment advice. Stock investing can result in permanent loss of capital. All model outputs must be fact-checked, reviewed by humans, and judged independently.

The original materials may be subject to copyright. Use them only within lawful authorization, personal study, or research contexts. Confirm copyright requirements before redistribution, training, publication, or commercial use.

## Acknowledgements

Special thanks to [wuxiaoda/BRK-Annual-Meeting](https://github.com/wuxiaoda/BRK-Annual-Meeting) for its valuable materials.
