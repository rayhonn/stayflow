# Secrets Policy

Local secrets live in ignored `.env` files. CI uses encrypted credentials/identity federation. Production uses AWS Secrets Manager or equivalent. Never expose secrets in client bundles, logs, issues, commits or screenshots.
