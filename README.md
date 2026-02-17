# Playwright POM Generator - Simplified & Refactored

## 🎯 Overview

A simplified Page Object Model generator for Playwright that creates TypeScript page objects with sample code.

## ✨ What's New

### Landing Page (index.html)
- ✅ Hero section with "Transform Tests into Page Objects"
- ✅ Powerful Features section (6 feature cards)
- ✅ Professional footer with creator information
- ✅ Stats bar (100% TypeScript, Promise Type Safe, etc.)
- ✅ Call-to-action section

### Generator Page (playwright-pom-generator.html)
- ✅ **Simplified Input**: Only requires Page Name and Page URL
- ✅ **No Test Code Required**: Generates sample code automatically
- ✅ **View Each Page File**: Click to view individual page object code
- ✅ **Sample Code**: Generated files include TODO comments for customization
- ✅ **Clean Interface**: Focused on page configuration only

## 📁 File Structure

```
pomtestbuilder/
├── index.html                      # Landing page with features
├── playwright-pom-generator.html   # Simple generator (no test code needed)
└── css/
    └── styles.css                 # Shared styles
```

## 🚀 How It Works

### User Flow:

1. **Landing Page (index.html)**
   - User sees features and benefits
   - Clicks "Launch Generator" button

2. **Generator Page (playwright-pom-generator.html)**
   - Enter application base URL
   - Add pages (name + optional URL)
   - Click "Generate POM"
   - View each generated page file individually
   - Download complete framework as ZIP

### Generated Output:

Each page gets:
- **Page Object** with sample locators and methods
- **Test File** with beforeEach/afterEach hooks
- **TODO Comments** for easy customization

Plus configuration files:
- `playwright.config.ts`
- `package.json`
- `tsconfig.json`
- `README.md` with customization guide
- `.gitignore`

## 🎨 Features on Landing Page

1. **User-Friendly Interface** - Simple, intuitive design
2. **Automated POM Generation** - Sample code generation
3. **Support for Application URLs** - Context-aware configuration
4. **Test Structure** - Before/After hooks included
5. **Downloadable Packages** - Complete ZIP download
6. **Preview Generated Code** - View each file before download

## 💻 Sample Generated Code

### Page Object (LoginPage.ts):
```typescript
import { Page, Locator } from '@playwright/test';

export class LoginPage {
    readonly page: Page;
    
    // TODO: Replace these sample locators
    private usernameInput = '#username';
    private passwordInput = '#password';
    
    constructor(page: Page) {
        this.page = page;
    }
    
    async getUsernameInput(): Promise<Locator> {
        return this.page.locator(this.usernameInput);
    }
    
    async fillUsername(username: string): Promise<void> {
        await (await this.getUsernameInput()).fill(username);
    }
    
    // ... more methods
}
```

### Test File (loginpage.spec.ts):
```typescript
import { test, expect, Page } from '@playwright/test';
import { LoginPage } from '../pages/LoginPage';

test.describe('LoginPage Tests', () => {
    let pageObject: LoginPage;

    test.beforeEach(async ({ page }: { page: Page }) => {
        pageObject = new LoginPage(page);
        await pageObject.navigate();
        await pageObject.waitForPageLoad();
    });

    test.afterEach(async ({ page }: { page: Page }) => {
        console.log('Test completed');
    });

    // TODO: Customize these tests
    test('sample test', async ({ page }: { page: Page }) => {
        await pageObject.fillUsername('testuser');
        // ... your test logic
    });
});
```

## 🔧 Customization Steps

1. **Download** the generated ZIP file
2. **Extract** to your project directory
3. **Install** dependencies: `npm install`
4. **Customize** page objects:
   - Replace sample locators with your actual selectors
   - Add/remove methods as needed
5. **Update** tests with your scenarios
6. **Run** tests: `npm test`

## 📦 What Gets Generated

| File | Description |
|------|-------------|
| `pages/*.ts` | Page Object Models with sample code |
| `tests/*.spec.ts` | Test files with hooks and samples |
| `playwright.config.ts` | Multi-browser configuration |
| `package.json` | NPM scripts and dependencies |
| `tsconfig.json` | TypeScript configuration |
| `README.md` | Customization guide |
| `.gitignore` | Git ignore rules |

## 🎯 Key Improvements

### Before:
- Required test code input
- Complex interface with multiple steps
- No individual file viewing
- Features buried in generator page

### After:
- ✅ No test code needed
- ✅ Simple 2-step process (URL + Pages)
- ✅ View each page file individually
- ✅ Features on landing page
- ✅ Sample code with TODO comments
- ✅ Cleaner, focused generator

## 👨‍💻 Created By

**Hariprasad MS**  
Senior QA Automation Engineer  
SDER Experts Ltd

Portfolio: https://hariprasadms.github.io/

## 📄 License

MIT License - Free to use and modify

---

**Crafted with ❤️ for automation testers, by automation testers**
