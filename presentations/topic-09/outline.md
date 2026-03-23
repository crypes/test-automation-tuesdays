# Topic 9: Alternative Tooling: Playwright
## Learning Objectives
By the end of this session, participants will be able to:
- Compare Playwright with WebdriverIO
- Understand when to choose each framework
- Recognize trade-offs between tools

### Presentation Outline (15-20 minutes)

1.  **Introduction: Framework Choices (3 min)**
    - Why consider alternatives?
    - Landscape of modern test tools
    - When to evaluate new tools

2.  **Playwright Overview (5 min)**
    - Microsoft's modern automation tool
    - Architecture (native browser APIs)
    - Key features (auto-wait, tracing, codegen)

3.  **Playwright vs WebdriverIO (7 min)**
    - Speed and performance comparison
    - API differences
    - Ecosystem and community
    - When to choose which

4.  **Demo: Playwright Quick Look (3 min)**
    - Show Playwright test syntax
    - Highlight key differences from WebdriverIO

5.  **Q&A / Wrap-Up (2 min)**

### Demo Script

**Step 1: Playwright Syntax (1 min)**
```typescript
import { test, expect } from '@playwright/test';

test('login test', async ({ page }) => {
  await page.goto('https://example.com/login');
  await page.fill('#username', 'user');
  await page.fill('#password', 'pass');
  await page.click('button[type="submit"]');
  await expect(page.locator('#welcome')).toBeVisible();
});
```

**Step 2: Compare with WebdriverIO (1 min)**
```typescript
// WebdriverIO syntax
await browser.url('https://example.com/login');
await $('#username').setValue('user');
await $('#password').setValue('pass');
await $('button[type="submit"]').click();
await expect($('#welcome')).toBeDisplayed();
```

**Step 3: Discuss Trade-offs (1 min)**
- Playwright: Faster, newer, less mature ecosystem
- WebdriverIO: Battle-tested, extensive integrations

### Resources
- Playwright docs
- Comparison articles linked in research.md
