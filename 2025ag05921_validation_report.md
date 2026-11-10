# Data Validation Report (Roll No: 2025ag05921)

| Validation Metric | Count | Status |
|---|---|---|
| Total Raw Review Records | 10004 | Ingested |
| Validated Clean Records | 10000 | Passed -> `data/processed/validated_reviews.csv` |
| Quarantined Corrupt Records | 4 | Isolated -> `data/errors/quarantined_reviews.csv` |
| Missing/Null Key Violations | 1 | Caught & Quarantined |
| Out-of-Range Rating (<1 or >5) | 2 | Caught & Quarantined |
| Foreign Key Integrity Failures | 3 | Caught & Quarantined |
| Malformed Timestamp Violations | 1 | Caught & Quarantined |
