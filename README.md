# AI4LIFE — Essay Analysis & Scoring Microservices

[![Build Status](https://img.shields.io/badge/build-unknown-lightgrey)](.) [![Version](https://img.shields.io/badge/version-0.1-blue)](.) [![License](https://img.shields.io/badge/license-see--repo-yellowgreen)](.)

A small collection of services and utilities to preprocess, analyze, and score educational essays. The repository includes a data transformation utility, a model analysis service, a scoring API, and a test/demo frontend.

Quick links
- Analysis service: [analysis_service/](analysis_service/) — see [analysis_service/app.py](analysis_service/app.py), [analysis_service/model.py](analysis_service/model.py), [analysis_service/test_model.py](analysis_service/test_model.py), [analysis_service/readme.md](analysis_service/readme.md)
- Scoring API: [score-service/](score-service/) — see [score-service/app.py](score-service/app.py), [score-service/test_api.py](score-service/test_api.py), [score-service/README.md](score-service/README.md), [score-service/LICENSE](score-service/LICENSE)
- Front-end / demo: [test-service/](test-service/) — see [test-service/package.json](test-service/package.json), [test-service/README.md](test-service/README.md)
- Utilities & data tools: [utils/](utils/) — see [utils/README.md](utils/README.md) and [utils/pivot.py](utils/pivot.py)

What this project does
- Provides a data ingestion and pivot pipeline for essay datasets ([utils/pivot.py](utils/pivot.py), [utils/README.md](utils/README.md))
- Hosts an analysis microservice that loads models and runs local evaluation functions ([analysis_service/app.py](analysis_service/app.py), [analysis_service/model.py](analysis_service/model.py))
- Exposes a scoring API for serving model predictions ([score-service/app.py](score-service/app.py))
- Includes a test/demo frontend with example workflows ([test-service/](test-service/))

Why this project is useful
- Reproducible pipeline for converting raw essay datasets to analysis-ready formats.
- Modular architecture separates preprocessing, model analysis, and serving.
- Test suites and examples for local validation and CI integration: [analysis_service/test_model.py](analysis_service/test_model.py), [score-service/test_api.py](score-service/test_api.py).

Getting started (developer quick-start)
1. Clone
   ```bash
   git clone <repo-url>
   cd AI4LIFE
   ```

2. Analysis service (Python)
   ```bash
   cd analysis_service
   python -m venv .venv
   source .venv/bin/activate  # Windows: .venv\Scripts\activate
   pip install -r requirements.txt
   uvicorn app:app --reload        # start the analysis service
   ```

   Files: [analysis_service/app.py](analysis_service/app.py), [analysis_service/model.py](analysis_service/model.py), [analysis_service/test_model.py](analysis_service/test_model.py), [analysis_service/utils.py](analysis_service/utils.py)

3. Score service (Python API)
   ```bash
   cd ../score-service
   python -m venv .venv
   source .venv/bin/activate # Windows: .venv\Scripts\activate
   pip install -r requirements.txt
   python app.py        # start the scoring API
   pytest -q test_api.py   # run API tests
   ```

   Files: [score-service/app.py](score-service/app.py), [score-service/test_api.py](score-service/test_api.py)

4. Test service (Node / pnpm)
   ```bash
   cd ../test-service
   npm install -g pnpm
   pnpm install
   python -m venv .venv
   source .venv/bin/activate # Windows: .venv\Scripts\activate
   pip install -r requirements.txt
   pnpm run dev          # run app
   ```

   Files: [test-service/package.json](test-service/package.json), [test-service/README.md](test-service/README.md)

5. Utilities / data pipeline
   ```bash
   cd ../utils
   python -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt
   python pivot.py      # run main data pivoting script
   ```
   Files: [utils/pivot.py](utils/pivot.py), [utils/README.md](utils/README.md)

Getting help
- Start with individual service READMEs: [analysis_service/readme.md](analysis_service/readme.md), [score-service/README.md](score-service/README.md), [test-service/README.md](test-service/README.md), [utils/README.md](utils/README.md)
- Run tests in each service to validate environment:
  - [analysis_service/test_model.py](analysis_service/test_model.py)
  - [score-service/test_api.py](score-service/test_api.py)
- Open an issue in this repository for bugs, enhancements, or questions.

Contributing and maintainers
- Maintainable structure: small, service-oriented codebases make contributions simple.
- For contribution guidelines, please follow this repository's CONTRIBUTING policy or open an issue to discuss changes.
- Code owners and primary maintainers are listed in each service folder; see the individual READMEs for contact and ownership:
  - [analysis_service/readme.md](analysis_service/readme.md)
  - [score-service/README.md](score-service/README.md)
  - [test-service/README.md](test-service/README.md)

License
- See service-level LICENSE files: [score-service/LICENSE](score-service/LICENSE), [test-service/LISENCE](test-service/LISENCE)
- Do not copy full license text here — refer to each LICENSE file in the relevant folder.

Notes
- Keep each service isolated in its environment so dependencies don’t conflict.
- Tests included in each service are the fastest way to verify a clean working state.

If you want a shorter onboarding checklist or a CONTRIBUTING.md draft added to the root, say so and a concise template will be provided.