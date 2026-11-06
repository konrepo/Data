# Blocker Data

Public database distribution for Blocker iOS.

## Files

### Spam Identification Database

- `us-spam.json` — US suspected spam caller identification database.
- `manifest.json` — Database version, update timestamp, entry count, file size, and SHA-256 checksum.

### US Curated Blocklist

- `us-blocklist.json` — Curated US phone numbers intended for automatic blocking.
- `blocklist-manifest.json` — Database version, update timestamp, entry count, file size, and SHA-256 checksum.

## Data Sources

### FCC Spam Identification Database

Generated from public FCC consumer complaint records.

- Only complaints categorized as **Phone / Unwanted Calls** are considered.
- Phone numbers must have at least two reports within the collection window.
- Database updates are generated and validated through GitHub Actions.

### US Curated Blocklist

Contains 355 US phone numbers collected from user-provided.

These numbers are manually curated and are not independently verified by the FCC.

## How Blocker Uses the Databases

| Database | Action |
|---|---|
| `us-spam.json` | Identifies callers as Suspected Spam |
| `us-blocklist.json` | Blocks listed phone numbers |

The two databases serve different purposes and are maintained separately.

## Important Limitations

- FCC complaint records are unverified.
- Caller ID numbers can be spoofed.
- A complaint does not prove that a number is malicious.
- Presence in the FCC database does not automatically block a caller.
- Curated blocklist entries are based on user-provided reports and may contain errors.

## Privacy

This repository contains downloadable phone-number databases only. It does not contain the Blocker iOS application source code or personal user information.

## Updates

Database files and their corresponding manifests are versioned separately.

Blocker verifies downloaded database files using SHA-256 checksums before accepting updates.