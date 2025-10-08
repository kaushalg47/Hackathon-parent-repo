# tarGETs VERTEX Tester (AI-powered)

TarGETs is a team-driven project to build an AI-assisted unit tester application. The parent repository serves as a central orchestrator and includes two sources to access the engine via submodules:
- VS Code extension engine: vertex-tester
- Hosted web application: vertex-tester-webapp (hosted on GCP: *https://vertex-test-app-398754751300.asia-south1.run.app/*)

This repository uses Git submodules to include both sources.

## Quick start

Clone with submodules
- git clone --recurse-submodules <your-parent-repo-url>

Initialize and update submodules (if you already cloned without submodules)
- git submodule update --init --recursive

Update submodules to the latest commits on their configured branches
- git submodule update --remote --recursive

## Project structure

- vertex-tester
  - Location: vertex-tester/
  - Purpose: VS Code extension engine for the unit tester. This is the development surface for the AI-powered tests inside VS Code.
- vertex-tester-webapp
  - Location: vertex-tester-webapp/
  - Purpose: Hosted web application engine for the unit tester.

Note: Each submodule has its own README with precise build/run instructions. This parent README provides high-level guidance and how to get started quickly.

## Running the two sources

Vertex-tester (VS Code extension)
- Change to the submodule directory:
  - cd vertex-tester
- Install dependencies:
  - npm install
- Build (if your submodule defines a build step):
  - npm run build
- Run inside VS Code:
  - Open the folder in VS Code
  - Press F5 to run the Extension Development Host (or use any provided Run/Debug configurations)
- Packaging (optional):
  - npm run package (or use the vsce tool as defined in the submodule)

Vertex-tester-webapp (Hosted web app)
- Change to the submodule directory:
  - cd vertex-tester-webapp
- Install dependencies:
  - npm install
- Run the app (typical options):
  - npm start
  - or npm run dev
- Access the running app:
  - The terminal will print the local URL (e.g., http://localhost:3000)

Important: Use the specific commands provided in each submodule’s README, as they may have project-specific scripts or environment requirements.

## How to use together

- The two sources provide complementary access to the engine:
  - VS Code extension for local development, unit tests, and quick iterations inside the editor.
  - Hosted web app for end-to-end or UI-oriented testing scenarios in a browser.
- When updating code, ensure you commit submodule pointer changes in the parent repo:
  - After making changes inside a submodule:
    - git add vertex-tester
    - git commit -m "Update vertex-tester submodule"
  - Then push the updated pointer in the parent repo:
    - git push origin <your-remote>

## Common workflows

Fresh clone with submodules:
- git clone --recurse-submodules <parent-repo-url>

Update all submodules to their latest configured commits:
- git submodule update --remote --recursive

If a submodule changes its own history or you switch branches:
- cd <submodule>
- git pull origin <branch> (or the appropriate workflow for that submodule)
- cd ..
- git add <submodule>
- git commit -m "Sync submodule <name> to latest"
- git push


## Contact and team

- tarGETs team
  - @sivatejaswi27
  - @kaushalg47
  - @monishanand10

---

If you share the exact URLs for your parent repo and the submodules (and any preferred commands or port numbers), I can tailor this README even further with precise steps and a customized checklist.
