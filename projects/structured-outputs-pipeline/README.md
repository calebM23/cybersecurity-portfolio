# Structured Outputs Pipeline

## EducationPals AI Engineer Intern Take-home

This project demonstrates a schema-validated AI output pipeline with a bounded repair loop. It treats model output as an engineering interface: generated JSON is parsed, validated against a strict contract, repaired at most once when invalid, revalidated, and then either accepted or quarantined.

## Project Goal

Large language models can return useful text while still breaking downstream software through malformed JSON, incorrect data types, missing fields, unsupported enum values, or unexpected keys. This project builds a deterministic boundary between model output and application code.

## Technologies

- Python 3.12
- JSON Schema Draft 2020-12
- `jsonschema==4.26.0`
- Optional OpenAI integration with `openai==3.5.0`
- JSONL output artifacts
- Offline cached-output replay requiring no API key

## Architecture

The project is divided into three progressive lessons:

1. **Contract Gate** — Separates JSON parsing failures from schema-validation failures and accepts only objects satisfying a closed schema.
2. **Bounded Repair** — Converts validation errors into compact repair feedback, performs no more than one repair, and sends the result through the same validator.
3. **Operational Pipeline** — Processes a batch, tracks first-pass and repaired success separately, quarantines terminal failures, and revalidates every accepted artifact.

## Security and Reliability Practices

- Closed schemas use `additionalProperties: false`
- Invalid outputs are never trusted before validation
- Repairs pass through the same validation gate
- Retry behavior is strictly bounded
- Terminal failures are quarantined instead of silently accepted
- Metrics distinguish first-pass quality from recovered quality
- Cached fixtures make results reproducible without network access
- No API key is required for offline replay

## Verified Results

The capstone processed eight fixtures:

| Result | Count |
|---|---:|
| Accepted on first attempt | 2 |
| Accepted after one repair | 5 |
| Rejected and quarantined | 1 |
| Final acceptance rate | 87.5% |
| First-pass acceptance rate | 25% |

The final verification confirmed that all seven accepted records remained schema-valid when reloaded. One intentionally unrepairable fixture reached the quarantine path, proving that the retry limit and terminal-failure handling worked.

## Expected Output Artifacts

- `validated.jsonl` — Accepted schema-valid records
- `quarantine.jsonl` — Terminal failures
- `metrics.json` — First-pass, repaired, rejected, and acceptance-rate metrics

## Skills Demonstrated

- Python application structure
- Defensive validation
- JSON Schema design
- Error classification
- Bounded retry and repair logic
- Batch processing
- Metrics and observability
- Failure isolation and quarantine
- Reproducible offline testing

## Portfolio Relevance

Although created for an AI engineering take-home, the same defensive principles apply directly to cybersecurity and SOC automation: never trust unvalidated input, enforce explicit contracts, isolate failures, limit retries, preserve evidence, and measure pipeline quality.
