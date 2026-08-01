# SWIFT/BIC Codes Database

SWIFT/BIC codes for banks and financial institutions worldwide. 232 countries, 112,000+ records.

## What is this?

This repository provides a **ready-to-use database** of swift/bic codes database with **112,887 records** across **232 countries**. Available as SQLite database and SQL dumps — ideal for developers, data analysts, and fintech applications.

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
- Updated: **2026-08-01**

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

## Use Cases

- **International wire transfers** — Look up SWIFT/BIC codes before sending money abroad
- **Payment system integration** — Validate bank codes in fintech and payment applications
- **Banking directory** — Build a searchable bank directory for any country
- **Compliance &amp; KYC** — Verify financial institution identifiers
- **Data enrichment** — Enrich transaction data with bank names and locations

## FAQ

### What is a SWIFT/BIC code?
A SWIFT/BIC code is an 8-11 character identifier used to identify banks and financial institutions globally for international wire transfers. SWIFT stands for Society for Worldwide Interbank Financial Telecommunication.

### How often is this data updated?
The database is updated monthly. Check the [Releases](../../releases) page for the latest version.

### Can I use this data commercially?
Yes. This data is released under the [MIT License](LICENSE) — free to use for any purpose, including commercial applications.

### How do I look up a SWIFT code for a specific bank?
```sql
SELECT * FROM swift_codes WHERE bank LIKE '%KASIKORN%';
```

### How do I get all banks in a specific country?
```sql
SELECT * FROM swift_codes WHERE country_code = 'TH' ORDER BY bank;
```


## Countries (232)

| Country | Code | Records | Details |
|---|---|---|---|
| Italy | IT | 26,259 | [View](countries/IT/) |
| United Kingdom of Great Britain and Northern Ireland | GB | 20,757 | [View](countries/GB/) |
| Germany | DE | 8,518 | [View](countries/DE/) |
| United States of America | US | 5,781 | [View](countries/US/) |
| France | FR | 4,924 | [View](countries/FR/) |
| India | IN | 4,272 | [View](countries/IN/) |
| China | CN | 2,652 | [View](countries/CN/) |
| Switzerland | CH | 1,904 | [View](countries/CH/) |
| Taiwan, Province of China | TW | 1,889 | [View](countries/TW/) |
| Netherlands, Kingdom of the | NL | 1,714 | [View](countries/NL/) |
| Russian Federation | RU | 1,646 | [View](countries/RU/) |
| Türkiye | TR | 1,459 | [View](countries/TR/) |
| Hong Kong | HK | 1,362 | [View](countries/HK/) |
| Egypt | EG | 1,276 | [View](countries/EG/) |
| Austria | AT | 1,191 | [View](countries/AT/) |
| Ireland | IE | 1,087 | [View](countries/IE/) |
| Australia | AU | 1,063 | [View](countries/AU/) |
| Luxembourg | LU | 1,051 | [View](countries/LU/) |
| Bangladesh | BD | 993 | [View](countries/BD/) |
| Spain | ES | 933 | [View](countries/ES/) |
| Iran, Islamic Republic of | IR | 902 | [View](countries/IR/) |
| Singapore | SG | 880 | [View](countries/SG/) |
| Indonesia | ID | 772 | [View](countries/ID/) |
| Norway | NO | 731 | [View](countries/NO/) |
| Japan | JP | 712 | [View](countries/JP/) |
| Viet Nam | VN | 701 | [View](countries/VN/) |
| Belgium | BE | 651 | [View](countries/BE/) |
| Canada | CA | 613 | [View](countries/CA/) |
| Ecuador | EC | 612 | [View](countries/EC/) |
| Denmark | DK | 611 | [View](countries/DK/) |
| Finland | FI | 602 | [View](countries/FI/) |
| Sweden | SE | 523 | [View](countries/SE/) |
| South Africa | ZA | 471 | [View](countries/ZA/) |
| Pakistan | PK | 468 | [View](countries/PK/) |
| Philippines | PH | 456 | [View](countries/PH/) |
| United Arab Emirates | AE | 438 | [View](countries/AE/) |
| Malaysia | MY | 413 | [View](countries/MY/) |
| Brazil | BR | 410 | [View](countries/BR/) |
| Poland | PL | 398 | [View](countries/PL/) |
| Ukraine | UA | 296 | [View](countries/UA/) |
| Thailand | TH | 282 | [View](countries/TH/) |
| Korea, Republic of | KR | 272 | [View](countries/KR/) |
| Romania | RO | 263 | [View](countries/RO/) |
| Portugal | PT | 253 | [View](countries/PT/) |
| Jersey | JE | 246 | [View](countries/JE/) |
| Libya | LY | 222 | [View](countries/LY/) |
| Greece | GR | 221 | [View](countries/GR/) |
| New Zealand | NZ | 209 | [View](countries/NZ/) |
| Cyprus | CY | 205 | [View](countries/CY/) |
| Colombia | CO | 199 | [View](countries/CO/) |
| Dominican Republic | DO | 198 | [View](countries/DO/) |
| Nigeria | NG | 196 | [View](countries/NG/) |
| Cayman Islands | KY | 194 | [View](countries/KY/) |
| Argentina | AR | 184 | [View](countries/AR/) |
| Mexico | MX | 177 | [View](countries/MX/) |
| Jordan | JO | 168 | [View](countries/JO/) |
| Bahrain | BH | 167 | [View](countries/BH/) |
| Kenya | KE | 166 | [View](countries/KE/) |
| Hungary | HU | 160 | [View](countries/HU/) |
| Lithuania | LT | 150 | [View](countries/LT/) |
| Czechia | CZ | 148 | [View](countries/CZ/) |
| Kuwait | KW | 145 | [View](countries/KW/) |
| Bulgaria | BG | 132 | [View](countries/BG/) |
| Lebanon | LB | 126 | [View](countries/LB/) |
| Panama | PA | 123 | [View](countries/PA/) |
| Saudi Arabia | SA | 123 | [View](countries/SA/) |
| Slovakia | SK | 122 | [View](countries/SK/) |
| Algeria | DZ | 119 | [View](countries/DZ/) |
| Chile | CL | 114 | [View](countries/CL/) |
| Belarus | BY | 113 | [View](countries/BY/) |
| Malta | MT | 106 | [View](countries/MT/) |
| Bahamas | BS | 104 | [View](countries/BS/) |
| Morocco | MA | 101 | [View](countries/MA/) |
| Ghana | GH | 97 | [View](countries/GH/) |
| Tanzania, United Republic of | TZ | 97 | [View](countries/TZ/) |
| Venezuela, Bolivarian Republic of | VE | 95 | [View](countries/VE/) |
| Iraq | IQ | 94 | [View](countries/IQ/) |
| Syrian Arab Republic | SY | 85 | [View](countries/SY/) |
| Côte d&#39;Ivoire | CI | 84 | [View](countries/CI/) |
| Kazakhstan | KZ | 82 | [View](countries/KZ/) |
| Sri Lanka | LK | 82 | [View](countries/LK/) |
| Qatar | QA | 82 | [View](countries/QA/) |
| Sudan | SD | 81 | [View](countries/SD/) |
| Guernsey | GG | 80 | [View](countries/GG/) |
| Israel | IL | 79 | [View](countries/IL/) |
| Serbia | RS | 79 | [View](countries/RS/) |
| Tunisia | TN | 79 | [View](countries/TN/) |
| Croatia | HR | 78 | [View](countries/HR/) |
| Isle of Man | IM | 78 | [View](countries/IM/) |
| Yemen | YE | 69 | [View](countries/YE/) |
| Latvia | LV | 68 | [View](countries/LV/) |
| Monaco | MC | 68 | [View](countries/MC/) |
| Uruguay | UY | 66 | [View](countries/UY/) |
| Georgia | GE | 65 | [View](countries/GE/) |
| Jamaica | JM | 65 | [View](countries/JM/) |
| Oman | OM | 65 | [View](countries/OM/) |
| Uzbekistan | UZ | 65 | [View](countries/UZ/) |
| Slovenia | SI | 64 | [View](countries/SI/) |
| Zimbabwe | ZW | 64 | [View](countries/ZW/) |
| Guatemala | GT | 61 | [View](countries/GT/) |
| Mauritius | MU | 60 | [View](countries/MU/) |
| Bolivia, Plurinational State of | BO | 59 | [View](countries/BO/) |
| Bermuda | BM | 58 | [View](countries/BM/) |
| Palestine, State of | PS | 57 | [View](countries/PS/) |
| Honduras | HN | 53 | [View](countries/HN/) |
| Zambia | ZM | 53 | [View](countries/ZM/) |
| Azerbaijan | AZ | 52 | [View](countries/AZ/) |
| San Marino | SM | 52 | [View](countries/SM/) |
| Cambodia | KH | 51 | [View](countries/KH/) |
| Uganda | UG | 51 | [View](countries/UG/) |
| Curaçao | CW | 48 | [View](countries/CW/) |
| North Macedonia | MK | 48 | [View](countries/MK/) |
| Botswana | BW | 46 | [View](countries/BW/) |
| Albania | AL | 45 | [View](countries/AL/) |
| Cameroon | CM | 45 | [View](countries/CM/) |
| Estonia | EE | 44 | [View](countries/EE/) |
| Paraguay | PY | 44 | [View](countries/PY/) |
| Liechtenstein | LI | 42 | [View](countries/LI/) |
| Myanmar | MM | 42 | [View](countries/MM/) |
| Angola | AO | 41 | [View](countries/AO/) |
| Trinidad and Tobago | TT | 40 | [View](countries/TT/) |
| Lao People&#39;s Democratic Republic | LA | 39 | [View](countries/LA/) |
| Peru | PE | 39 | [View](countries/PE/) |
| Costa Rica | CR | 38 | [View](countries/CR/) |
| Iceland | IS | 36 | [View](countries/IS/) |
| Nepal | NP | 36 | [View](countries/NP/) |
| Senegal | SN | 36 | [View](countries/SN/) |
| XK | XK | 34 | [View](countries/XK/) |
| Bosnia and Herzegovina | BA | 33 | [View](countries/BA/) |
| Macao | MO | 33 | [View](countries/MO/) |
| Mozambique | MZ | 33 | [View](countries/MZ/) |
| Puerto Rico | PR | 33 | [View](countries/PR/) |
| Congo, Democratic Republic of the | CD | 31 | [View](countries/CD/) |
| Gibraltar | GI | 31 | [View](countries/GI/) |
| Malawi | MW | 31 | [View](countries/MW/) |
| Tajikistan | TJ | 31 | [View](countries/TJ/) |
| Barbados | BB | 29 | [View](countries/BB/) |
| Moldova, Republic of | MD | 28 | [View](countries/MD/) |
| Togo | TG | 28 | [View](countries/TG/) |
| Virgin Islands (British) | VG | 28 | [View](countries/VG/) |
| Ethiopia | ET | 27 | [View](countries/ET/) |
| El Salvador | SV | 27 | [View](countries/SV/) |
| Kyrgyzstan | KG | 26 | [View](countries/KG/) |
| South Sudan | SS | 25 | [View](countries/SS/) |
| Gabon | GA | 24 | [View](countries/GA/) |
| Gambia | GM | 24 | [View](countries/GM/) |
| Rwanda | RW | 24 | [View](countries/RW/) |
| Namibia | NA | 22 | [View](countries/NA/) |
| Mauritania | MR | 21 | [View](countries/MR/) |
| Afghanistan | AF | 20 | [View](countries/AF/) |
| Armenia | AM | 20 | [View](countries/AM/) |
| Burkina Faso | BF | 20 | [View](countries/BF/) |
| Mali | ML | 20 | [View](countries/ML/) |
| Nicaragua | NI | 20 | [View](countries/NI/) |
| Benin | BJ | 19 | [View](countries/BJ/) |
| Belize | BZ | 19 | [View](countries/BZ/) |
| Congo | CG | 19 | [View](countries/CG/) |
| Guinea | GN | 19 | [View](countries/GN/) |
| Niger | NE | 19 | [View](countries/NE/) |
| Montenegro | ME | 18 | [View](countries/ME/) |
| Mongolia | MN | 18 | [View](countries/MN/) |
| Sierra Leone | SL | 18 | [View](countries/SL/) |
| Vanuatu | VU | 18 | [View](countries/VU/) |
| Antigua and Barbuda | AG | 17 | [View](countries/AG/) |
| Burundi | BI | 17 | [View](countries/BI/) |
| Saint Kitts and Nevis | KN | 17 | [View](countries/KN/) |
| Liberia | LR | 17 | [View](countries/LR/) |
| New Caledonia | NC | 17 | [View](countries/NC/) |
| Comoros | KM | 16 | [View](countries/KM/) |
| Madagascar | MG | 16 | [View](countries/MG/) |
| Brunei Darussalam | BN | 15 | [View](countries/BN/) |
| Guadeloupe | GP | 15 | [View](countries/GP/) |
| Seychelles | SC | 15 | [View](countries/SC/) |
| Cuba | CU | 14 | [View](countries/CU/) |
| Haiti | HT | 14 | [View](countries/HT/) |
| Saint Lucia | LC | 14 | [View](countries/LC/) |
| Cabo Verde | CV | 13 | [View](countries/CV/) |
| Djibouti | DJ | 13 | [View](countries/DJ/) |
| Dominica | DM | 13 | [View](countries/DM/) |
| Suriname | SR | 13 | [View](countries/SR/) |
| Korea, Democratic People&#39;s Republic of | KP | 12 | [View](countries/KP/) |
| Martinique | MQ | 12 | [View](countries/MQ/) |
| Chad | TD | 12 | [View](countries/TD/) |
| Turkmenistan | TM | 12 | [View](countries/TM/) |
| Saint Vincent and the Grenadines | VC | 12 | [View](countries/VC/) |
| Equatorial Guinea | GQ | 11 | [View](countries/GQ/) |
| French Polynesia | PF | 11 | [View](countries/PF/) |
| Réunion | RE | 11 | [View](countries/RE/) |
| Fiji | FJ | 10 | [View](countries/FJ/) |
| Andorra | AD | 9 | [View](countries/AD/) |
| Aruba | AW | 9 | [View](countries/AW/) |
| Guyana | GY | 9 | [View](countries/GY/) |
| Maldives | MV | 9 | [View](countries/MV/) |
| Bonaire, Sint Eustatius and Saba | BQ | 8 | [View](countries/BQ/) |
| Bhutan | BT | 8 | [View](countries/BT/) |
| Sao Tome and Principe | ST | 8 | [View](countries/ST/) |
| Sint Maarten (Dutch part) | SX | 8 | [View](countries/SX/) |
| Samoa | WS | 8 | [View](countries/WS/) |
| Grenada | GD | 7 | [View](countries/GD/) |
| Papua New Guinea | PG | 7 | [View](countries/PG/) |
| Somalia | SO | 7 | [View](countries/SO/) |
| Eswatini | SZ | 7 | [View](countries/SZ/) |
| Cook Islands | CK | 6 | [View](countries/CK/) |
| Faroe Islands | FO | 6 | [View](countries/FO/) |
| French Guiana | GF | 6 | [View](countries/GF/) |
| Guinea-Bissau | GW | 6 | [View](countries/GW/) |
| Lesotho | LS | 6 | [View](countries/LS/) |
| Solomon Islands | SB | 6 | [View](countries/SB/) |
| Turks and Caicos Islands | TC | 6 | [View](countries/TC/) |
| Tonga | TO | 6 | [View](countries/TO/) |
| Virgin Islands (U.S.) | VI | 6 | [View](countries/VI/) |
| Central African Republic | CF | 5 | [View](countries/CF/) |
| Timor-Leste | TL | 5 | [View](countries/TL/) |
| Anguilla | AI | 4 | [View](countries/AI/) |
| Guam | GU | 4 | [View](countries/GU/) |
| Marshall Islands | MH | 4 | [View](countries/MH/) |
| Northern Mariana Islands | MP | 4 | [View](countries/MP/) |
| Montserrat | MS | 4 | [View](countries/MS/) |
| Wallis and Futuna | WF | 4 | [View](countries/WF/) |
| Eritrea | ER | 3 | [View](countries/ER/) |
| Holy See | VA | 3 | [View](countries/VA/) |
| American Samoa | AS | 2 | [View](countries/AS/) |
| Nauru | NR | 2 | [View](countries/NR/) |
| Saint Pierre and Miquelon | PM | 2 | [View](countries/PM/) |
| Falkland Islands (Malvinas) | FK | 1 | [View](countries/FK/) |
| Micronesia, Federated States of | FM | 1 | [View](countries/FM/) |
| Greenland | GL | 1 | [View](countries/GL/) |
| Kiribati | KI | 1 | [View](countries/KI/) |
| Palau | PW | 1 | [View](countries/PW/) |
| Saint Helena, Ascension and Tristan da Cunha | SH | 1 | [View](countries/SH/) |
| Tuvalu | TV | 1 | [View](countries/TV/) |
| Mayotte | YT | 1 | [View](countries/YT/) |


## Browse Online

Explore and download individual datasets at **[listbase.org](https://listbase.org/en/finance/)**.

## License

[MIT](LICENSE) — Free to use for any purpose.

## Source

SWIFT via public registries

---

Made with data from [ListBase.org](https://listbase.org/en/finance/) — Free Reference Tables & Lists
