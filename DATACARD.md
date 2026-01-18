# Data Card — Synthetic Gambling Conversations Dataset (v1.0.0)

**Motivation.** Provide a safe, public, synthetic corpus for research on gambling-related behaviors, including risk patterns, emotional signals, and (in the next release) personality-conditioned language.

**Composition.**
- Monologues: 36,001 rows (pre-dedup)
- Threads: 1,718 rows (pre-dedup)
- Language: English (with emojis)
- Domain: Gambling-related scenarios; money mentions are common.

**Collection.** Data are **synthetically generated** using a controlled prompting pipeline. No scraping of real user data.

**Cleaning.**
- Removed/flagged: emails, phones, credit-card-like, IBAN-like sequences (regex-based).
- Duplicates: flagged; `*_dedup.csv` removes normalized duplicates (keep-first).
- Profanity: flagged but not removed (research realism); users may filter.

**Ethical considerations.**
- No real PII; synthetic content only.
- Contains rare profanity and frequent money mentions; content flags provided.
- Not intended to encourage gambling; research/education use only.

**Splits.**
- Not provided to avoid leakage assumptions; users should create stratified splits per task.

**Known limitations.**
- Profanity lexicon is conservative; false positives/negatives possible.
- PII detection uses regex; false positives possible for numbers.
- Threads are stored as flattened text; turn-level parsing may be required for dialogue models.

**Future work.**
- Personality-conditioned generation with Big Five traits.
- Turn-structured JSON format for threads.
- Automatic alignment metrics between assigned traits and detected traits.
