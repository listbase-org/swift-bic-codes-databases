# SWIFT/BIC Codes Database

SWIFT/BIC codes for banks and financial institutions worldwide. 232 countries, 112,000+ records.

## Downloads

| Format | Description | Link |
|---|---|---|
| **SQLite** | Single database file, ready to query | [Releases](../../releases) |
| **SQL** | SQL dump, import into MySQL/PostgreSQL/etc. | [Releases](../../releases) |
| **Excel / CSV / PDF** | Formatted spreadsheets | [listbase.org](https://listbase.org/en/finance/) |

## Database Schema

```sql
CREATE TABLE swift_codes (
  country_code TEXT NOT NULL,
  swift_code TEXT NOT NULL,
  bank TEXT,
  city TEXT,
  branch TEXT
);
CREATE INDEX idx_swift_codes_country_code ON swift_codes (country_code);
CREATE INDEX idx_swift_codes_swift_code ON swift_codes (swift_code);
```

## Stats

- **112,887** records
- **232** countries
- Updated: **2026-07-26**

## Preview

| country_code | swift_code | bank | city | branch |
| --- | --- | --- | --- | --- |
| AD | BACAADAD | ANDORRA BANC AGRICOL REIG S.A. | LES ESCALDES |  |
| AD | AAMAADAD | ANDORRA GESTIO AGRICOL REIG SAU | ESCALDES-ENGORDANY |  |
| AD | BSANADAD | BANC SABADELL D&#39;ANDORRA S.A. | ANDORRA LA VELLA |  |
| AD | CASBADAD | BANCA PRIVADA D&#39;ANDORRA S.A. | LES ESCALDES |  |
| AD | CRDAADAD | CREDIT ANDORRA,S.A. | ANDORRA LA VELLA |  |
| AD | BINAADAD | MORA BANC GRUP SA | ANDORRA LA VELLA |  |
| AD | BINAADB1 | MORA BANC SAU | LES ESCALDES |  |
| AD | RINSADA1 | RESULT INTERNACIONAL SA | ANDORRA LA VELLA |  |
| AD | VALBADAD | VALL BANC | ESCALDES-ENGORDANY |  |
| AE | ABNAAEAAIPC | ABN AMRO BANK N.V. UNITED ARAB EMIRATES  | DUBAI | (INTERNATIONAL PRIVATE CLIENTS DEPARTMEN |
| AE | ABNAAEAA | ABN AMRO BANK N.V. UNITED ARAB EMIRATES  | DUBAI |  |
| AE | ABPPAEA1 | ABRAAJ CAPITAL LIMITED | DUBAI |  |
| AE | ADCBAEAACMD | ABU DHABI COMMERCIAL BANK | ABU DHABI | (CASH MANAGEMENT DEPARTMENT) |
| AE | ADCBAEAAFIN | ABU DHABI COMMERCIAL BANK | ABU DHABI | (FINANCE  DEPARTEMENT) |
| AE | ADCBAEAAREM | ABU DHABI COMMERCIAL BANK | ABU DHABI | (RBS) |
| ... | ... | ... | ... | ... |

*Showing 15 of 112,887 records*

## Release Files

| File | Records | Description |
|---|---|---|
| `swift-bic-codes.db` | 112,887 | SQLite database (all data) |
| `swift-bic-codes-part1.sql` | 1-50,000 | SQL dump (part 1) |
| `swift-bic-codes-part2.sql` | 50,001-100,000 | SQL dump (part 2) |
| `swift-bic-codes-part3.sql` | 100,001-112,887 | SQL dump (part 3) |

> SQL files are split into parts of 50,000 records each. Import all parts in order.

## Usage

### SQLite
```bash
sqlite3 swift-bic-codes.db "SELECT * FROM swift_codes WHERE country_code = 'US' LIMIT 10;"
```

### Import SQL (MySQL)
```bash
mysql -u root -p your_database < swift-bic-codes-part1.sql
```

### Import SQL (PostgreSQL)
```bash
psql -U postgres -d your_database -f swift-bic-codes-part1.sql
```

## Browse Online

Explore and download individual country datasets at **[listbase.org](https://listbase.org/en/finance/)**:

- [United Arab Emirates — SWIFT/BIC Codes](https://listbase.org/en/finance/ae-swift-codes/)
- [Argentina — SWIFT/BIC Codes](https://listbase.org/en/finance/ar-swift-codes/)
- [Albania — SWIFT/BIC Codes](https://listbase.org/en/finance/al-swift-codes/)
- [Angola — SWIFT/BIC Codes](https://listbase.org/en/finance/ao-swift-codes/)
- [Afghanistan — SWIFT/BIC Codes](https://listbase.org/en/finance/af-swift-codes/)
- [Armenia — SWIFT/BIC Codes](https://listbase.org/en/finance/am-swift-codes/)
- [Antigua and Barbuda — SWIFT/BIC Codes](https://listbase.org/en/finance/ag-swift-codes/)
- [Andorra — SWIFT/BIC Codes](https://listbase.org/en/finance/ad-swift-codes/)
- [Anguilla — SWIFT/BIC Codes](https://listbase.org/en/finance/ai-swift-codes/)
- [American Samoa — SWIFT/BIC Codes](https://listbase.org/en/finance/as-swift-codes/)

## License

[MIT](LICENSE) — Free to use for any purpose.

## Source

SWIFT via public registries

---

Made with data from [ListBase.org](https://listbase.org/en/finance/) — Free Reference Tables & Lists
