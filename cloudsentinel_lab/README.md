# CloudSentinel controlled public test fixture

Marker: `sentinel_lab_v1`.

All values in this directory are synthetic and nonfunctional. They are not issued by a cloud provider, OAuth service, or database. They grant no access. The database hostname uses the reserved `.invalid` domain. Never put real credentials into this repository.

This directory supports an authorized defensive detector acceptance test:

- `cloud.json` contains one simulated AK/SK pair, one simulated OAuth secret, and one simulated database URI.
- `mirror.env` repeats the same simulated AK/SK to check entity correlation across files.
- `negative.yaml` separates AK and SK into different objects, and includes a placeholder API key. Neither case should generate an alert.

Phase 1 expects three independent credential entities and four exposure events. In phase 2, only the simulated SK in `cloud.json` changes. That adds one entity and three content-version exposure events; the unchanged OAuth/database components remain associated with their existing entities.

Public index availability and Git commit timestamps are not treated as the exact credential publication time. These are controlled test results, not real leaked credentials or proof of Internet-wide detection performance.
