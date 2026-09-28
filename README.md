# OLX.ba – Software Testing Project

Seminar project for the course **Formal Methods** at the Faculty of Information Technologies, Džemal Bijedić University of Mostar (academic year 2025/2026).

The project covers the full testing process for the search and filtering features of [OLX.ba](https://olx.ba), the largest online marketplace in Bosnia and Herzegovina. It includes test design with black-box and white-box techniques, manual test cases, defect reporting and automated UI tests with Selenium.

## Team (Group 28)

- Ajla Stranjak
- Amina Fazlić
- Asima Halilagić

Mentor: mr. sc. Ahmet Mulalić

## Project structure

| File / folder | Content |
|---|---|
| `1. Zadatak - Grupa 28.docx` | Test design with formal testing techniques |
| `2. Zadatak - Grupa 28.xlsx` | Manual test cases with a QA tester's log |
| `3. Zadatak - Grupa 28/` | Automated UI tests (Selenium WebDriver + Mocha + Chai) |
| `4. Zadatak - Grupa 28.xlsx` | Defect tracking log |

## 1. Test design techniques

Applied to OLX.ba search, price filter and category/location filters:

- **Equivalence Partitioning:** valid and invalid partitions of search input (length, character types, structure)
- **Boundary Value Analysis:** min/max price filter (negative values, 0, 1, MAX+1, From > To)
- **Decision Table Testing:** combinations of search query and price filter conditions
- **State Transition Testing:** state diagram for search, filtering, filter reset and "no results" states
- **Statement Coverage and Decision Coverage:** control flow graph with test cases achieving 100% coverage
- **Error Guessing:** input validation, illogical filter values, filter persistence after refresh, performance with long input
- **Exploratory Testing:** scenario-based test charters for OLX.ba

## 2. Manual test cases

Seven documented test cases, each with prerequisites, test data, test steps, expected and actual results, and a Pass/Fail status. They cover:

- search with category filter
- numeric, alphanumeric and special-character input
- excessively long input (200+ characters)
- empty search input
- price filter value retention

## 3. Automated tests

Ten end-to-end UI tests written in JavaScript using **Selenium WebDriver**, **Mocha** and **Chai**:

1. Search and URL parameter validation
2. Filtering by the "Automobili" category
3. Page scroll functionality
4. Navigation through categories and back
5. Empty search validation
6. Search field input and clearing
7. Logo click returns to the homepage
8. Multiple consecutive searches
9. Presence of main navigation elements
10. Page metadata (title, URL, search field attributes)

### How to run

Requirements: [Node.js](https://nodejs.org/) and Google Chrome.

```bash
cd "3. Zadatak - Grupa 28"
npm install
npm test
```

> The tests run against the live OLX.ba website, so results can change if the site layout changes.

## 4. Defect reporting

Defects found during testing were logged in a defect tracking log, with steps to reproduce, expected and actual results, priority and status. Examples:

- The "Last 24h" filter hides an ad posted 25 minutes earlier.
- Changing the sort order changes the total number of search results (5995 → 5224), although sorting should only change the order.
- Price filter returns an item priced outside the selected range (24.90 KM with a 500–1500 KM filter).

## Technologies and tools

`JavaScript` · `Node.js` · `Selenium WebDriver` · `Mocha` · `Chai` · `ChromeDriver` · `Microsoft Excel` · `Microsoft Word`
