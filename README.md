# 🍽️ Modern Food Blog UI & CI/CD Pipeline

![Build Status](https://img.shields.io/github/actions/workflow/status/bonykoshy/devops_cicd_test/static-site.yaml?style=flat-square&logo=github)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=flat-square&logo=tailwind-css&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)

## 🚀 Project Overview
This repository serves as a live demonstration of modern frontend development coupled with automated DevOps practices. It hosts a fully responsive, premium Food Blog interface featuring advanced UI trends like glassmorphism, fluid CSS grids, and micro-interactions. 

More importantly, this project acts as a sandbox for **Continuous Integration and Continuous Deployment (CI/CD)**. Every push to the `main` branch triggers a strict automated pipeline that validates code quality before deploying to production.

## 🛠️ Tech Stack & Architecture
* **Frontend UI:** HTML5, Tailwind CSS (via CDN for rapid utility-class styling).
* **Typography & Iconography:** Google Fonts (Inter & Playfair Display), FontAwesome 6.
* **DevOps Infrastructure:** GitHub Actions, Ubuntu Linux Runners.
* **Quality Assurance (QA):** HTML Tidy (syntax validation), Linkchecker (broken link detection).

## ⚙️ The CI/CD Deployment Workflow
The deployment lifecycle is governed by the `.github/workflows/static-site.yaml` file. It enforces a 5-stage automated pipeline to ensure zero-defect deployments:

1. **Checkout Code:** Initializes the runner and pulls the latest repository commit.
2. **Static Code Analysis (`tidy`):** Scans the raw HTML to ensure strict W3C syntax compliance and proper tag structure.
3. **Link Integrity Check (`linkchecker`):** Crawls the DOM to verify that all internal routes, external `href` attributes, and `img src` assets resolve successfully (Preventing 404 errors in production).
4. **Artifact Generation:** Compiles the validated source code into a secure `.zip` artifact for auditing and version history.
5. **Automated Release (`peaceiris/actions-gh-pages`):** Safely pushes the validated build directory directly to the live GitHub Pages environment.
