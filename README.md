# Playwright-Basics
Learn Playwright as a Project

What is Playwright?
Playwright is a powerful browser automation tool (like Selenium in Java or Python's Playwright equivalent) that allows you to write scripts to control Chromium, Firefox, and WebKit browsers. It’s great for testing, scraping, or automating web tasks. 

TypeScript adds static typing to JavaScript, making it feel closer to Java’s structure while retaining JavaScript’s flexibility.

I'll organize this into a professional Playwright project structure with TypeScript, including a test that attempts to log into Facebook with your specified credentials (email and password "123"), and handles the failed login scenario. Here's the setup:

```playwright-facebook/
├── node_modules/              # Dependencies (auto-generated)
├── tests/                     # Test files
│   ├── pages/                # Page Object Models
│   │   └── facebook-login-page.ts
│   ├── specs/                # Test specs
│   │   └── facebook-login.spec.ts
│   └── utils/                # Helper utilities
│       └── test-utils.ts
├── playwright.config.ts       # Playwright configuration
├── package.json              # Node.js dependencies
├── tsconfig.json             # TypeScript configuration
└── README.md                 # Project documentation
```

## Step-by-Step Setup
### 1. Initialize the Project
Run these commands in your terminal:
```
mkdir playwright-facebook
cd playwright-facebook
npm init -y
npm install typescript @playwright/test --save-dev
npx tsc --init
npx playwright install  # Installs browser binaries
```
### 2. Configure tsconfig.json
```
{
  "compilerOptions": {
    "target": "es6",
    "module": "commonjs",
    "strict": true,
    "rootDir": "./tests",
    "outDir": "./dist",
    "sourceMap": true,
    "esModuleInterop": true
  },
  "include": ["tests/**/*"],
  "exclude": ["node_modules"]
}
```

