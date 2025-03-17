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
Console shows:
```D:\Projects\Playwright\Facebook-Playwright>npm install typescript @playwright/test --save-dev
added 4 packages, and audited 5 packages in 3s
found 0 vulnerabilities

D:\Projects\Playwright\Facebook-Playwright>npx tsc --init
Created a new tsconfig.json with:                                                                                                                TS
  target: es2016
  module: commonjs
  strict: true
  esModuleInterop: true
  skipLibCheck: true
  forceConsistentCasingInFileNames: true
You can learn more at https://aka.ms/tsconfig
```
If you are manually creating your source files, you may use similar commands:
```
mkdir tests
cd tests
mkdir specs utils pages
type nul > pages/facebook-login-page.ts
type nul > specs/facebook-login.spec.ts
type nul > utils/test-utils.ts
```
### 2. Configure tsconfig.json
Uncomment the below lines and append include/exclude section. E.g.
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
### Execute from terminal
```
D:\Projects\Playwright\Facebook-Playwright>npm run test:headed
```
![image](https://github.com/user-attachments/assets/b9cb06ef-9742-4386-9816-191dcd66f1ee)


Because we intentionally did not provide the correct credentials in the login spec file, it should fail after retries.
![image](https://github.com/user-attachments/assets/f244272d-a38b-4377-a93a-a3dc337da3a3)

