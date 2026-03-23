# Topic 7: Visual Regression Testing
## Learning Objectives
By the end of this session, participants will be able to:
- Implement visual regression testing with wdio-visual-service
- Create and manage baseline images
- Interpret visual diff results

### Presentation Outline (15-20 minutes)

1.  **Introduction: Visual Testing (3 min)**
    - What is visual regression?
    - When to use visual tests
    - Types of visual testing (pixel-perfect vs perceptual)

2.  **wdio-visual-service Setup (5 min)**
    - Installation and configuration
    - Baseline folder structure
    - Screenshot options (element, viewport, full page)

3.  **Running Visual Tests (5 min)**
    - Creating baselines
    - Comparison workflow
    - Threshold and diff configuration
    - Handling dynamic content

4.  **Demo: Visual Test Implementation (5 min)**
    - Setup wdio-visual-service
    - Create baseline
    - Introduce visual change and observe diff

5.  **Q&A / Wrap-Up (2 min)**

### Demo Script

**Step 1: Install and Configure (2 min)**
```bash
npm install @wdio/visual-service --save-dev
```

```typescript
// wdio.conf.ts
services: [
    ['visual', {
        baselineFolder: path.join(process.cwd(), 'baseline'),
        formatImageName: '{tag}-{logName}-{width}x{height}'
    }]
]
```

**Step 2: Create Visual Test (2 min)**
```typescript
Then(/^the page visually matches "([^"]*)"$/, async (screenshotPath) => {
    await browser.checkFullPageScreen(screenshotPath);
});
```

**Step 3: Run and Observe (1 min)**
- First run creates baseline
- Modify UI slightly
- Second run shows diff

### Resources
- wdio-visual-service docs
- webdriver-image-comparison module docs
