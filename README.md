# goAML XML Generator

A browser-based tool for generating goAML 5.x compliant XML reports, pre-configured for the **Luxembourg CRF** (Cellule de Renseignement Financier).

Supports **English / Français / 中文**.

---

## Usage

Open `goaml-xml-generator_en_fr_cn.html` directly in any modern browser — no installation or server required.

1. Fill in the Report Header fields
2. Add one or more Transactions
3. Select applicable Indicators
4. Copy or export the generated XML as a `.txt` file

---

## Scope & Regional Compatibility

### Core XML schema — universal

This tool generates XML based on the **standard goAML 5.x schema** developed by UNODC (United Nations Office on Drugs and Crime). The schema is used by Financial Intelligence Units (FIUs) in many countries, including South Africa, UAE, Uganda, Cyprus, Mauritius, and others. The generated XML structure (`<report>`, `<transaction>`, `<t_from_my_client>`, etc.) is fully compatible with any goAML 5.x installation.

### Pre-configured for Luxembourg CRF

The following elements are specific to Luxembourg and must be adapted for other jurisdictions:

| Element | Notes |
|---|---|
| **Report Indicators (1–25)** | Defined by Luxembourg CRF. Each FIU publishes its own indicator list with different numbering and descriptions. |
| **Sample data** | Uses `CRFLLULL` (Luxembourg CRF SWIFT code) as placeholder. |
| **Currency options** | Limited to EUR, USD, GBP, CHF. Other regions may require additional currencies. |
| **Header badge** | Displays "Luxembourg CRF · goAML 5.x". |

### Adapting for other countries

To use this tool for a different goAML-adopting jurisdiction:

1. Replace the `INDICATORS` array (lines ~367–393 in the HTML file) with the indicator list published by the target FIU.
2. Add any required currencies to the `<select id="currency_code_local">` dropdown.
3. Update placeholder values and the header badge to reflect the target institution.

The XML generation logic itself requires no changes.

---

## Files

| File | Description |
|---|---|
| `goaml-xml-generator_en_fr_cn.html` | Main tool — trilingual (EN / FR / ZH) |
| `goaml-xml-generator (1).html` | Earlier version |
| `goAML_User_Manual.docx` | User manual (English) |
| `goAML_用户手册.docx` | User manual (Chinese) |

---

## Compatibility

- **goAML version:** 5.x
- **Browser:** Any modern browser (Chrome, Firefox, Edge, Safari)
- **Dependencies:** None — fully self-contained single-file application

---

## References

### Luxembourg CRF (Cellule de Renseignement Financier)
- Official website: [crf.public.lu](https://crf.public.lu/en.html)
- Suspicious Operations Report guideline (EN, 2026): [Guideline v2.2](https://financialcrime.lu/assets/pdfs/articles/2026/01/20260106%20EN%20Suspicious%20Operations%20Report%20%C2%A6%20Guideline%20applicable%20from%2006-01-2026%20(version%202-2)_%5BMD5_9F355B1BC852B4F840C52C1455EA978F%5D.pdf)

### UNODC goAML
- Official goAML page: [unodc.org — goAML](https://www.unodc.org/unodc/en/global-it-products/goaml.html)
- goAML is deployed in approximately 60 countries. Each country's FIU defines its own indicator list, report codes, and submission rules — consult your local FIU documentation before adapting this tool.
