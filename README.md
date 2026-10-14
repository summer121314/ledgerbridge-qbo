# LedgerBridge Lab

Independent, local-first QuickBooks CSV preparation beta.

## Supported
- CSV parsing with quotes and embedded newlines
- Mapping date, description, signed amount or credit/debit columns
- Checking dates, amounts, missing cells, duplicate-looking rows
- Standard CSV export and QuickBooks three/four-column export
- QuickBooks CSV export capped at 350 KB
- Synthetic-only experimental QBO structure demonstration

## Important limitations
- Not affiliated with Intuit. No live QuickBooks import certification has been performed.
- Browser-only data processing; do not use real financial identifiers for synthetic QBO tests.
- This is a CSV formatter, not a bank Web Connect QBO conversion service.
- Some locale-specific amount formats and bank exports are unsupported.
- Review amounts, credit/debit direction and dates manually before any import.

## Manual regression scenarios
1. Clean sample: 3 valid, 0 errors, 0 warnings; three-column CSV downloads.
2. Duplicate sample: 4 valid, one warning; QuickBooks CSV disabled.
3. Four-column mapping: select Debit and Credit; confirm direction before export.
4. Ambiguous date 01/02/2026: Auto rejects; explicit MDY/DMY validates.
5. CSV quoted comma and newline: preserved in description.
6. Wrong row length or malformed quote: load error or row error.
7. Zero amount and missing date: flagged as invalid.
8. Switch mapping/layout after validation: export disabled until revalidation.
9. CSV output above 350KB: export blocked.

## Publication status
Vercel serves the beta, but acceptance by QuickBooks Online must still be confirmed with an authorized sandbox account and synthetic data.
