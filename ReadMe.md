# Monorepo Starter (WIP)

[![Airbnb-standard-style](https://img.shields.io/badge/code%20style-airbnb-brightgreen.svg)](https://github.com/airbnb/javascript) [![MIT License](https://img.shields.io/badge/license-mit-brightgreen.svg)](https://github.com/barlowm/mono_repo_template/blob/master/LICENSE) [![Monorepo Maintained With Lerna](https://img.shields.io/badge/maintained%20by-lerna-99424f.svg)](https://lerna.js.org) [![tested with mocha](https://img.shields.io/badge/tested_with-mocha-99424f.svg)](https://mochajs.org) 


## Description

Template for creating a [Mono Repository](https://en.wikipedia.org/wiki/Monorepo) using [Lerna](https://lerna.js.org), (a tool for managing JavaScript projects with multiple packages/applications/components).
This template was originally created for a project that I was working on that consisted of a graphical user interface (GUI) and several interconnected node js microservices
Rather than put everything into a single application path I created a repository that had each component in it's own "package".
This way each microservice could be developed independently as could the GUI.

## Uses Lerna to manage the mono repository
To start a new project clone this repo then do a 
```
npm install
```

Then, to create a new package, use "lerna"

```
npx lerna create <Package Name>
```

Add package specific scripts to the root package.json file:

```
"test_pkg1": "npx lerna run test --scope pkg1",
"lint_pkg1": "npx lerna run lint --scope pkg1"
```

Add matching scripts to individual package package.json files:

```
"test": "npx mocha \"__tests__/*.test.js\" --reporter mochawesome --reporter-options reportDir=reports,reportFilename=test_report,reportTitle=\"test_report\",reportPageTitle=\"Test-Report\"",
"lint": "eslint lib/*.js -f html -o 'reports/lint_report.html"
```

Include an `env_template.env` as a sample for any `.env` file needed. The template should only show what variables are needed not any specific data.
