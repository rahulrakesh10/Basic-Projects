# FlyRank ML Research Capstone

**Ranking Signal Analysis** — A research project on safe content signals associated with search visibility and engagement.

## 📋 Project Overview

This capstone analyzes which public-safe content and technical signals correlate with search visibility, clicks, engagement, and movement in FlyRank search results. Using Gradient Boosting regression on FlyRank's data warehouse, we ranked signals by importance and generated evidence-backed recommendations.

- **Lane:** Ranking Signal Analysis
- **Timeline:** 8 weeks (self-paced)
- **Status:** Complete
- **Deployed Paper:** [https://rahulrakesh10.github.io/Flyrank_research/](https://rahulrakesh10.github.io/Flyrank_research/)

## 🎯 Key Findings

| Rank | Signal | Importance | Category |
|------|--------|-----------|----------|
| 1 | Mobile Friendliness | 18.7% | Technical SEO |
| 2 | Schema Markup | 15.6% | Technical SEO |
| 3 | Content Freshness | 12.3% | Freshness |
| 4 | Indexability Score | 11.2% | Technical SEO |
| 5 | Meta Descriptions | 8.9% | Technical SEO |

**Model Performance:**
- Signal-aware model R² = 0.68 (+36% vs position-only baseline)
- Cross-validation R² = 0.65 (robust, not overfit)

## 📂 Repository Structure

```
Flyrank_research/
├── work/
│   ├── 01_first_look_and_discovery.ipynb       # Week 1-2 EDA
│   ├── 02_your_first_readable_model.ipynb      # Week 3-4 Baseline model
│   └── 03_ranking_signal_analysis_capstone.ipynb # Week 5-8 Full analysis
├── docs/
│   └── index.html                               # Deployed research paper
├── submission/
│   └── paper_url.txt                            # Paper URL (required)
├── README.md                                    # This file
└── .gitignore
```

## 🚀 Getting Started

### Prerequisites
- Python 3.9+
- Jupyter Notebook
- HuggingFace account (free tier)
- ~30 min setup time

### 1. Clone Repository
```bash
git clone https://github.com/rahulrakesh10/Flyrank_research.git
cd Flyrank_research
```

### 2. Install Dependencies
```bash
pip install duckdb pandas scikit-learn matplotlib seaborn numpy
```

### 3. Get Data Access
1. Create free account: [https://huggingface.co](https://huggingface.co)
2. Request access (gated, ~2 min): [FlyRank Dataset](https://huggingface.co/datasets/flyrank-ai/search_intelligence_warehouse)
3. Generate read token: [HF Settings > Tokens](https://huggingface.co/settings/tokens)
4. Add token to notebook cell 1.2

### 4. Run Capstone Notebook
```bash
jupyter notebook work/03_ranking_signal_analysis_capstone.ipynb
```

Run all cells in order. Results are deterministic (`random_state=42`).

## 📊 Analysis Details

### Research Question
Which safe content/search signals are most strongly associated with visibility, clicks, engagement, and movement in FlyRank search results?

### Methodology
- **Data:** FlyRank warehouse, 1.2M search impressions (2025)
- **Features:** 35 signals across 5 categories (content, technical, freshness, engagement, domain)
- **Model:** Gradient Boosting with temporal train-test split
- **Validation:** 5-fold cross-validation on held-out test period (Oct-Dec 2025)

### Key Insights
1. **Technical SEO dominates (58% importance):** Mobile, schema, indexability, meta descriptions matter most
2. **Freshness signals (12%):** Recent updates correlate with higher visibility
3. **Engagement validates quality (7%):** High time-on-page suggests relevant search result
4. **Content depth weak signal (8%):** Structure matters more than raw word count
5. **Domain signals minimal (6%):** Quality content on newer domains can overcome domain age

## 📖 Read the Paper

**[Deployed Research Paper](https://rahulrakesh10.github.io/Flyrank_research/)**

Paper includes:
- Abstract (5-sentence summary)
- Introduction & problem statement
- Data scope & exclusions
- Methodology & validation design
- Full results with visualizations
- Limitations & honest framing
- Ranked recommendations (action playbook)
- Reproducibility instructions

## 🎬 Recommendations

### Immediate Actions (High ROI, Low Effort)
1. **Implement schema markup** (15.6% importance)
   - Add JSON-LD for content type (Article, FAQ, BreadcrumbList)
   - Validate with Google Rich Results Test
   - Timeline: 1-2 weeks

2. **Write strong meta descriptions** (8.9% importance)
   - 150-160 chars, unique per page, include CTA
   - Timeline: 1-2 weeks

### Short-term (Medium Effort, High Impact)
3. **Mobile optimization** (18.7% importance)
   - Audit Core Web Vitals (LCP < 2.5s, CLS < 0.1)
   - Fix touch-friendly issues
   - Timeline: 2-4 weeks

4. **Content refresh cycle** (12.3% importance)
   - Update top-100 pages every 30-90 days
   - Focus on freshness + factual accuracy
   - Timeline: Ongoing monthly

5. **Indexability audit** (11.2% importance)
   - Check robots.txt, noindex directives
   - Ensure CSS/JS resources crawlable
   - Timeline: 3-5 days

## 🔬 Methodology Highlights

### Leakage Prevention ✓
- All signal features from page content only (no behavioral leakage)
- Position not used as a feature (prevents circularity)
- Temporal train-test split (Sept vs Oct-Dec 2025)
- Scaler fit on train data only

### Honest Framing ✓
- **Observational, not causal:** Signals correlate with visibility, not proven to cause it
- **Position confounding:** Selection bias exists; high-ranking pages may have high-quality signals *because* they rank high
- **No algorithm claims:** All signals are public-safe; no proprietary Google/Bing internals
- **Directional language:** "Associated with" not "will cause"

## 📚 Additional Resources

- **Starter Notebook (Provided):** `02_your_first_readable_model.ipynb` — DuckDB basics + sklearn intro
- **FlyRank Website:** [https://flyrank.ai](https://flyrank.ai)
- **Data Source:** [HuggingFace Datasets](https://huggingface.co/datasets/flyrank-ai/search_intelligence_warehouse)

## 📝 Citation

If you build on this research, please cite:

```
Rahul Rakesh (2026). Ranking Signal Analysis: Content Signals Associated with Search Visibility. 
FlyRank ML Internship Research Capstone.
https://rahulrakesh10.github.io/Flyrank_research/
```

## 🔓 License & Public Safety

This analysis follows public-safe research guidelines:
- ✓ No client names, domains, URLs
- ✓ No private query text or user behavior
- ✓ No claims about Google algorithm or causal impact
- ✓ Only public-safe content attributes analyzed

## 🤝 Contributing

Found an issue or want to extend this analysis? 

1. Fork the repo
2. Create feature branch: `git checkout -b feature/analysis-extension`
3. Commit changes: `git commit -m "Add XYZ signal analysis"`
4. Push & open PR

## ❓ Questions?

- **GitHub Issues:** [Open an issue](https://github.com/rahulrakesh10/Flyrank_research/issues)
- **Direct Contact:** [GitHub Profile](https://github.com/rahulrakesh10)

---

**Built on the FlyRank ML Internship dataset.**  
Data credit: [https://flyrank.ai](https://flyrank.ai)
