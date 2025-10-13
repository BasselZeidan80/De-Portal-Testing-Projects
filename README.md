# 🧭 De-Portal-Testing-Frameworks — Folder Structure Overview

This repository provides a unified structure for all **testing frameworks** used in the **De-Portal** ecosystem — including **Cypress**, **Playwright**, and future tools (e.g., Selenium, RestAssured).  
It ensures **scalability**, **reusability**, and **consistent standards** across all test projects.

---

## 📁 Main Structure

```
De-Portal-Testing-Frameworks/
│
├── common/
│   ├── utils/
│   │   ├── generic/           # Shared helpers (logging, API calls, random data)
│   │   ├── cypress/           # Utilities specific to Cypress
│   │   └── playwright/        # Utilities specific to Playwright
│   ├── config/                # Environment configs (URLs, credentials, test users)
│   ├── reporting/             # Shared reporting configs (Allure, Mochawesome, etc.)
│   └── test-data/             # Centralized JSON/CSV test data files
│
├── frameworks/
│   ├── cypress//Projects/
│   │   ├── project-Anubis/    # Example project built with Cypress
│   │   ├── project-B neon/    # Another Cypress-based project
│   │   └── package.json       # Dependencies and plugins for Cypress
│   │
│   ├── playwright//Projects/
│   │   ├── project-tiger/     # Playwright-based project
│   │   ├── project-spark/     # Another Playwright-based project
│   │   ├── project-E/         # Lightweight Playwright project
│   │   └── package.json       # Dependencies and plugins for Playwright
│   │
│   └── (future-frameworks...) # Placeholder for future tools (Selenium, RestAssured)
│
├── ci-cd/
│   ├── github-actions/        # YAML pipelines for CI
│   │   ├── run-cypress.yml
│   │   └── run-playwright.yml
│   └── jenkins/               # Jenkins pipeline scripts
│       ├── run-cypress.groovy
│       └── run-playwright.groovy
│
└── reports/
    └── allure-dashboard/      # Aggregated & merged Allure dashboards
```

---

## ⚙️ Purpose of Each Section

| Section | Description |
|----------|--------------|
| `common/` | Contains shared utilities, configs, and test data used by all frameworks. |
| `frameworks/` | Houses framework-specific projects (Cypress, Playwright, etc.) with modular separation. |
| `ci-cd/` | CI/CD configurations for automated execution in GitHub Actions and Jenkins. |
| `reports/` | Consolidated reporting dashboards, including Allure results and historical trends. |

---

## 🚀 Usage Guidelines

1. **Add new frameworks** under `/frameworks` with the same internal structure.  
2. **Keep shared configs** under `/common/config` to avoid duplication.  
3. **Maintain consistency** in naming (`project-name`) and folder conventions.  
4. **Link reports** from all projects into `/reports/allure-dashboard` for unified tracking.  
5. **Integrate pipelines** using templates in `/ci-cd`.

---

## 🧩 Example Flow

When adding a new Playwright project:
```
/frameworks/playwright/Projects/project-new/
├── tests/
├── fixtures/
├── reports/
└── playwright.config.js
```

Then:
- Reference global utilities from `/common/utils/playwright/`
- Add environment configs from `/common/config/`
- Push results to `/reports/allure-dashboard/`

---

## 🛠️ Future Extensions
- Add `Selenium` and `RestAssured` frameworks under `/frameworks/`
- Integrate centralized dashboard (Grafana or custom) under `/reports/`
- Extend `ci-cd` to include GitLab and Azure DevOps
